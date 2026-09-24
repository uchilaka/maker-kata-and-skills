---
name: kata-today
description: Tee off today's kata practice — find what's due (unfinished catch-ups first, then today), and run a menu that launches each block: opens the track's reading or feeds in the browser, opens the journal or voice app, opens the log entry, and starts the block timer. Blocks done elsewhere (a voice memo on the iPhone) can be checked off with a one-liner. Use when the user says "/kata-today", "tee me off", "start my kata", "what's my practice today", "run today's kata", or wants to catch up a missed practice day.
---

# /kata-today — tee off the practice

`bin/kata` renders and commits an entry. This skill sits between those two steps and
runs the session itself: one block at a time, each launched from a menu, with every link
and timer ready so the 45 minutes go to practice and not to setup.

**All facts come from the helper.** Don't parse log entries, tracks or the OPML by hand.
If you need a fact the helper doesn't expose, add it to the helper.

```sh
H=skills/kata-today/bin/kata-today     # run from the repo root
$H status               # journal config, catch-ups, missing days, today's blocks
$H status ENTRY         # one entry's shape, track, mode, per-block state, next block
```

## 1 · First run: set up the notes surfaces

If `status` prints `journal: unset — run setup`, ask about setup **before** showing the
menu, using one AskUserQuestion call:

Check what's installed first (`ls /Applications ~/Applications /System/Applications`),
and only offer apps that are present.

- **Journaling app.** Offer from Apple Journal, Notion, Obsidian, Day One, Apple Notes,
  and *None, just the log entry in my editor*. Each can be launched as follows:
  - **Apple Journal** (macOS 26+): an app open works. It has no public URL route to a
    new entry. Its `moments://` scheme exposes nothing usable.
  - **Notion**: `notion://www.notion.so/PAGE_ID` opens one fixed page. It can't create
    a page per day.
  - **Obsidian**: `obsidian://new?vault=VAULT&file=kata/{date}`.
  - **Day One**: `dayone://post?journal=Kata`.

  `{date}` and `{shape}` in a URL get filled from the entry.
- **Which blocks open it.** A multi-select of scan, depth, artifact and signal. The
  default is all four.
- **Voice.** For Apple Journal, recommend a one-action Shortcut. Journal's *record audio
  entry* App Intent opens straight into recording, with transcription and iPhone sync,
  and no URL can reach it. The other offers are Voice Memos, Just Press Record, Day One
  (audio), and *None*.

Then save the answers:

```sh
$H config journal_app "Journal"                 # or: none
$H config journal_url "notion://www.notion.so/…"  # only if a deep link applies
$H config journal_blocks scan depth artifact signal
$H config voice_shortcut "Kata Voice"           # a Shortcut wins over voice_url/voice_app
$H config voice_app "Journal"
```

**For the Shortcut,** walk the user through making it; you can't create it for them.
In Shortcuts.app: **+**, name it exactly as configured, add Journal's audio-entry
action, and save. Confirm with `shortcuts list | grep -x "Kata Voice"`. Until it exists,
`launch --voice` says so and opens nothing.

Settings are per machine, in `config/kata-today.local.yml`, which is gitignored. The work
laptop doesn't have to match the personal one. If the user picks *None* for the journal,
still set `journal_app none`. Otherwise every later run will ask again.

## 2 · Pick the entry

In order:

1. **Any `catchup:` lines** are entries from the last 7 days whose Artifact or Signal
   block is still empty. Offer them first, oldest first, alongside today. Catching up is
   a first-class path here, not a skip. When the user resumes an old entry, add a
   `note:    caught up on YYYY-MM-DD, not skipped` line under its header fields if the
   entry doesn't already have one.
2. **Any `missing:` lines** are past weekdays with no entry at all. Mention them in one
   line. `bin/kata` can only render today's entry. If the user wants to catch one up,
   write its header by hand in the same shape `bin/kata` uses, following the rotation
   in `config/default.yml` (`# YYYY-MM-DD · ddd · shape` plus the shape's fields, then
   the four `##` blocks).
3. **Today.** If `today_entry` is missing, run `$H prepare`. It needs `KATA_PROFILE`.

## 3 · Before the first block

- **Study day with `mode: —` and non-empty `modes_with_links`:** ask which mode to use
  (navigating, structural or supporting), then run `$H set-mode ENTRY MODE`. The track
  file says not to let *supporting* be the one that quietly gets skipped. If the log
  shows it hasn't been done recently, say so.
- **Kata day with an empty `subject:`:** ask what the rep is on, and write it into the
  entry. The form's subject-selection rule is in the kata file.

## 4 · The run menu

Run `$H status ENTRY`, then show one AskUserQuestion call with two questions.

**Step** (single-select). The `next:` block is the first option, marked
*(Recommended)*, with its minutes. The other not-done blocks follow in order. Label each
option with what it will open, for example:

- *Scan, 10 min: opens Kapor, Project Include, NCWIT*
- *Depth, 20 min: opens Tech Leavers + your journal*

**Notes** (single-select):

| Option | Runs |
| ------ | ---- |
| Type (Recommended) | `$H launch BLOCK ENTRY` opens inputs, journal app and entry, then starts the timer |
| Voice journal | `$H launch BLOCK ENTRY --voice` opens inputs and starts the timer only. When time's up, a dialog asks to record; **Record** runs the voice Shortcut |
| Already done on iPhone | ask for a one-line gist, then run `$H check BLOCK ENTRY --via iphone --kind voice\|text GIST` |
| Wrap up | skip to §5 |

**If `status` shows `voice_pending: BLOCK ENTRY`,** a voice block ended without being
checked off. Before the normal menu, ask about that block:

- *Record now*: run `$H record`.
- *Recorded, check it off*: ask for the gist, then run `$H check`.
- *Type instead*: run `$H launch BLOCK ENTRY`.

Recording is the reflection on the activity, so it comes **after** the block, never at
launch.

Rules for the menu:

- **Kata-day Scan** needs feed categories. Ask one multi-select from `$H feeds` (there
  are four, which fits), and pass them after the entry, e.g.
  `$H launch scan ENTRY "Systems" "Ruby / Rails"`.
- **A check-off always needs its gist.** The helper refuses without one, because
  `--review` compiles Artifact and Signal from these lines. Ask *text or voice?* only if
  it isn't obvious from what they said.
- **After a launch,** report the one-line `timer:` result and what opened, then stop and
  wait. Don't narrate the block. When the user comes back ("done", "next", or `/kata-today`
  again), re-read the status and show the menu for the next block.
- **Starting a new block replaces the running timer.** Checking a block off stops it. If
  the user bails mid-block, run `$H stop`.
- **If the helper prints `open: nothing — add ...`,** the track has no links for that
  block. Say which line to add, and keep going. Don't invent URLs.

## 5 · Wrap up

When `next: complete` shows, or the user picks *Wrap up*:

1. Show the entry's Artifact and Signal as written. If a claim in a study-day Artifact
   has no source attached, point that out once. On this track, being citable is the
   point of the block.
2. Commit **only the entry**, with the same message `bin/kata` uses and the **entry's**
   date, not today's:

   ```sh
   git add ENTRY && git commit -m "log: YYYY-MM-DD"
   ```

   Keep the message plain. Commit messages are **not** encrypted, and the repo is
   public. Push if `KATA_PROFILE` is `personal` or `work`, as `bin/kata` does.
3. If this was a catch-up and today's entry is still open, offer to go straight into it.

## Refuse when

- `status` dies with **repo is LOCKED**. Tier-1 files are ciphertext, so writing over
  them destroys the real content. Tell the user the unlock command from `bin/kata` and
  stop.
- Asked to store audio in the repo. Voice notes stay in the voice app. The log gets the
  gist line. Audio in git is heavy, and a git-crypt key grant can't be revoked later.
