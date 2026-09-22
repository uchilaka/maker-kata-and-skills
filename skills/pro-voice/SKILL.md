---
name: pro-voice
description: Audit a draft against your own writing voice, or learn that voice from a corpus of what you have already written. Use when the user says "/pro-voice", "check my voice", "does this sound like me", "audit the tone", "learn my voice", or hands over a doc/PR/review/comment and asks whether it reads right. Also the base register other skills inherit — /catty-commit and /catty-pr-draft layer sharpness on top of it, and review skills consume it for the perspective axis. Not a style guide for prose in general; it enforces one specific person's voice from recorded exemplars.
---

# /pro-voice — the base register

Two modes:

```
/pro-voice --learn <glob>    mine exemplars from what you already wrote
/pro-voice <file>            audit a draft, flag drift, offer a rewrite per flag
```

The profile lives at `~/.claude/voice/<name>.yml` and is **never** published. This repo
ships the tool and an empty schema; a voice profile is not a template.

## The trap: do not compute statistics

"Average sentence length 14.2, hedging rate 0.3" reads as rigor and steers nothing.
Every skill in this ecosystem that successfully controls voice does it with **paired
good/bad exemplars**, never with adjectives. `/simplify-this` lists five things the voice
sounds like and seven it does not. `/catty-commit` gives two Good and two Bad.

So `--learn` mines **rules plus exemplar pairs** — real sentences, attributed to the
artifact they came from. The audit then flags a passage by naming the exemplar it
violates, which makes every flag falsifiable and lets you throw one out when it is wrong.

## Three invariants

True in every register, including the catty one. They sit *below* both layers.

1. **Accuracy is the floor; everything else is a layer.** Strip the personality and the
   artifact must still stand as correct and complete.
2. **Never at someone's expense.** No dunking on past authors, no passive aggression, no
   condescension.
3. **Claims carry their evidence.** "This could be a problem" is not a finding. "With an
   empty collection this raises at line 42" is.

**Banned unless quoting source material:** *obviously · simply · just* ("just do X") ·
*of course · trivially · any fool can see · elementary.* Each one tells the reader their
confusion is a personal failing.

## Three moves that make it this voice

The invariants are what any careful writer avoids. These are the positive signature.

### 1. Curiosity is how disagreement gets framed

The question is genuine — it leaves room for the answer to be *because of a constraint you
don't know about*, which is frequently the truth.

> ✅ "Curious about the indexing strategy here — did you consider adding an index on
> `actor_id`? The query on line 42 filters on it."
> ❌ "This is missing an index on `actor_id`."

The second is fine for your own work. On someone else's it spends trust you will want later.

### 2. Show your own path to understanding

Making your not-knowing visible first is what makes the reader's not-knowing safe.

> ✅ "Took me a few reads to land on this — turns out the trick is…"
> ✅ "If this feels confusing, that's fair. I had to draw it out before it clicked."
> ✅ "I keep mixing these two up, so here's how I tell them apart…"
> ✅ "Honestly, the name is misleading — what it actually does is…"
> ❌ "It's actually quite simple…"  *(gaslights a reader who found it hard)*
> ❌ "Behold, the elegant solution…"

### 3. Reach for the picture before the paragraph

Three or more steps, two systems talking, a state change, or a decision point → a stick
diagram, ≤ 72 chars wide. An abstract concept → a concrete analogy from ordinary life.

```
┌──────────┐     ┌──────────────┐     ┌──────────────┐
│ raw input│ ──▶ │  validate &  │ ──▶ │  saved row   │
└──────────┘     └──────┬───────┘     └──────────────┘
                        ↳ bad row: park it in "needs review"
```

Box-drawing: `┌ ┐ └ ┘ │ ─ ├ ┤ ┬ ┴ ┼` · arrows `→ ← ↑ ↓ ▶ ◀ ↳`

## Two axes that flex

Neither changes the invariants. The diagram bias applies across the whole grid.

```
                  peer reader          newcomer reader
                ┌───────────────────┬────────────────────┐
  my own work   │ terse, unhedged   │ define inline,     │
                │ jargon fine       │ lead with the why  │
                ├───────────────────┼────────────────────┤
  someone       │ "Curious about X  │ analogy first,     │
  else's work   │  — did you…"      │ then the term      │
                └───────────────────┴────────────────────┘
```

**Perspective** — who owns the work being discussed. Self-review is direct and unhedged;
a teammate's work is blameless and curious, framed as observation or question.

**Reader distance** — a peer in the domain, or someone smart who has not seen this before.
Sets the jargon budget, the diagram density, and whether terms get defined inline.

Ask which cell you are in before writing. If the answer is "both", write for the newcomer
and let the peer skim.

## Audit mode

```
/pro-voice DRAFT.md
```

1. Read the profile at `~/.claude/voice/<name>.yml`. If absent, say so and offer `--learn`
   — do not silently fall back to generic good-writing advice. That is the failure mode
   that makes this skill worthless.
2. Infer the axes from the artifact (a PR review of someone else's branch is
   *other × peer*; a runbook for a new hire is *self × newcomer*). State which cell you
   picked, so a wrong guess is visible and correctable.
3. Flag drift. **Every flag names the exemplar or invariant it violates.** A flag that
   cannot cite one is not a flag — drop it.
4. Offer a rewrite per flag. The user accepts per flag, never wholesale.

Output shape:

```
cell: other × peer

  line 14   invariant 2 (never at someone's expense)
            "whoever wrote this clearly didn't read the docs"
            → "this looks like it predates the docs change — worth a look?"

  line 31   banned word: "just"
            "just add the index"
            → "adding the index on actor_id should cover it"

  line 47   move 3 (picture before paragraph)
            five sequential steps in prose
            → suggest a stick diagram; drafted below
```

## Learn mode

```
/pro-voice --learn ~/pr-reviews/**/*.md ~/project-plans/**/*.md
```

1. Read the corpus. Prefer artifacts the user wrote *for other people* — reviews, PR
   bodies, docs — over notes to self, which are terser than their real voice.
2. Extract **exemplar pairs**, not metrics. For each candidate rule find a real sentence
   that embodies it, and where possible a contrasting one from the same corpus.
3. Attribute every exemplar to its source file. An unattributed exemplar cannot be checked
   later and will quietly drift into invention.
4. **Append; never overwrite.** The profile is cumulative and hand-edited.
5. Print what was added and ask the user to cut what is not actually them. **The first
   profile is a draft, not an output** — a model's read of your voice after one pass is a
   hypothesis.

## For skills that consume this

`/catty-commit` and `/catty-pr-draft` load this as the base register and add sharpness,
emoji and puns on top. Everything in this file still applies with the jokes on — that is
what "accuracy first, personality is the layer on top" means.

Review skills consume the **perspective axis** specifically: `/pr-review`'s self-vs-teammate
interview question *is* the top-to-bottom axis of the grid above.

Agents that emit structured findings rather than prose (`security-reviewer`,
`correctness-reviewer`, `test-coverage-reviewer`, `review-triage`) should **not** load this.
They inherit the invariants through `~/CLAUDE.md`, and loading a voice profile into four
parallel subagents costs context in every one of them for no gain.
