---
name: kata-init
description: Interview a new adopter and generate their own kata practice — their track rotation, their kata library, their communities, their constraints. Use when someone says "/kata-init", "set up my practice", "help me start a kata practice", "adopt this repo", or has cloned maker-kata-and-skills and wants to make it theirs rather than run someone else's. Produces a filled config/, their own practice/tracks/, a starter sources/, and a first log entry.
---

# /kata-init — set up *your* practice

The defaults in this repo are one person's. Copying them wholesale produces a practice
about someone else's career. This interviews you and writes yours.

**Interview first, generate second.** Do not scaffold anything before the questions are
answered — a half-filled config is harder to correct than an empty one.

## Before anything: is a public repo safe for you?

Ask this first, plainly, and take the answer at face value.

> This repo is public by default. That means anyone can see that you practise, when, and
> roughly how much — filenames, sizes and commit timestamps stay readable even when the
> contents are encrypted. Is a public practice log safe for you where you work?

**This is not rhetorical.** For someone early in their career, on a visa, in a hostile
team, or in a place where an identity-linked practice log could be read against them,
publishing is a real risk and not a virtue. If the answer is no or unsure:

- Offer the private-repo path. Everything works identically; only the remote changes.
- Say that the encryption does not solve this — ciphertext in a public repo is
  permanently harvestable, and metadata leaks regardless.
- Do not argue for openness. It is not the point of the practice.

## The five questions

**1. What are you trying to be in eighteen months?**
Work backwards from the answer to the track rotation. Do not ask what they want to learn;
that produces a reading list. Ask what they want to *be able to do*, then name the tracks
that build it.

**2. What do you already own, and what do you depend on?**
The kata library needs real subjects. `read-a-subsystem` is worthless without a system
they can actually open.

**3. Which communities are you already in, which have you bounced off, and what kind of
support do you want to give?**
All three parts matter. The bounced-off ones tell you what not to suggest again. And the
giving question is the one people answer vaguely, which is exactly why the *supporting*
mode gets skipped later — pin it to something concrete now.

**4. What metro are you in, and do you want local or remote?**
Emit a starter list. **Mark what you verified against what you are guessing.** Three
confirmed groups beat twelve plausible ones, and a wrong meetup link costs them an evening.

**5. How many minutes, and is a work machine in the picture?**
Under 30 minutes, cut Depth before cutting Artifact or Signal — the output blocks are the
point. If a work machine is involved, walk the tier model and the MDM question: a
work-managed Mac with DLP or a backup agent means decrypted personal notes sit on
monitored hardware, and the encryption buys nothing against the party most likely to read
them.

## The identity track is parameterized, not copied

The three modes — **navigating**, **structural**, **supporting** — generalize across
marginalized groups in tech. The sources and communities do not.

So: keep the structure, replace the contents from answers to Q3 and Q4. Ask which
dimension of their experience this track is for; do not assume from anything you think you
know about them. Someone may want it for disability, caregiving, being the only
career-changer on the team, or nothing at all.

If they want no identity track, replace the Wednesday slot and do not editorialize.

## What to generate

Only after the interview:

| Path | From |
| ---- | ---- |
| `config/default.yml` | Q5 — block minutes, schedule, rotation |
| `config/profiles/*.yml` | Q5 — one per machine |
| `practice/tracks/*.md` | Q1 — one per study slot, each with 3–5 prompts |
| `practice/katas/*.md` | Q2 — **one** kata, the one they can run tomorrow |
| `practice/katas/CANDIDATES.md` | the rest, unpromoted |
| `sources/reading-list.md` | Q1, capped at ~15 |
| `sources/private/communities.md` | Q3, Q4 — tier 1, with verified/unverified marked |
| `log/<today>.md` | a real first entry, so day one is not a blank file |

**One kata, not five.** The rule in this repo is that a kata is only added after it has
been run twice informally. Generating a full library on day one breaks that rule
immediately and makes the rep counts meaningless. Everything else goes in `CANDIDATES.md`.

## Then

Walk them through `bin/doctor` and let it tell them what is missing. Do not pre-empt it —
the doctor is how they will diagnose this in six months, so the first run should be theirs.

End by saying what the practice will feel like in week three, honestly: the Friday re-rep
block feels like repeating yourself, because it is, and it is the only block that can show
improvement rather than accumulation. People drop it first.
