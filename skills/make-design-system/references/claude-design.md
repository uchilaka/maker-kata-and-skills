# Claude Design and DESIGN.md

Condensed from [VoltAgent/awesome-claude-design](https://github.com/VoltAgent/awesome-claude-design)
at `8f746b5` (MIT — see `UPSTREAM-LICENSE`), plus what was observed in the files themselves.
Where the two disagree, this file says so.

## What the pieces are

**`DESIGN.md`** is one markdown file describing a visual language so an agent can act on
it. It keeps **token, rule and rationale in one place**: specific enough to drive the next
decision, with enough *why* to stay on-system in a case the file never covered. The
format came from Google Stitch.

| File | Read by | Defines |
| ---- | ------- | ------- |
| `AGENTS.md` | Coding agents | How to build the project |
| `DESIGN.md` | Design agents (Claude Design, Stitch) | How the project looks and feels |

**[Claude Design](https://claude.ai/design)** holds a persistent design system per
project. Fed a `DESIGN.md`, it scaffolds the whole starter package in one pass:

- `README.md` — brand context, voice, visual foundations
- `colors_and_type.css` — CSS variables, type scale, utility classes
- Google Fonts substitutes where the brand font is proprietary
- `preview/` cards for colors, type, spacing, components, brand
- a working UI kit (`index.html` + components) applied to a real marketing page
- `SKILL.md` — a portable skill that re-summons the aesthetic in later projects

## Handing a DESIGN.md to Claude Design

**Option A — start from a design system.** Go to `claude.ai/design/#org`, choose
**Create new design system**, and upload the `DESIGN.md` under **Add assets** on the
*Set up your design system* screen.

**Option B — start from a prototype.** Create a new prototype from the dashboard, attach
the `DESIGN.md` in chat, and send: *"Create a design system from this DESIGN.md"*.

## The file's shape

Upstream's README describes nine sections:

| # | Section | What Claude reads it for |
| - | ------- | ------------------------ |
| 1 | Visual Theme & Atmosphere | Tone, density, mood of the scaffold |
| 2 | Color Palette & Roles | CSS variables with semantic names + hex |
| 3 | Typography Rules | Type scale and Google Fonts fallbacks |
| 4 | Component Stylings | Buttons, inputs, cards, nav, with states |
| 5 | Layout Principles | Spacing scale, grid, whitespace rhythm |
| 6 | Depth & Elevation | Shadow tokens and surface hierarchy |
| 7 | Do's and Don'ts | Guardrails for new screens |
| 8 | Responsive Behavior | Breakpoints, touch targets, collapse behavior |
| 9 | Agent Prompt Guide | Reusable prompts carried into the generated `SKILL.md` |

**The files themselves use different headings.** Checked 2026-09-24 against nine of them:
a YAML front matter block defines the tokens (`colors`, `typography`, `rounded`,
`spacing`, `components`, …), then the prose runs *Overview · Colors · Typography ·
Layout · Elevation & Depth · Shapes · Components · Do's and Don'ts* in every file, then some
or none of *Responsive Behavior · Iteration Guide · Known Gaps* (Vercel and WIRED stop at
Do's and Don'ts). Prose cites tokens as `{group.token}` rather than repeating hex values.

Follow the file you adapted from, not the README's table, and **write all eleven** in the
output even when the source skipped some. The concepts map one-to-one except that
*Shapes* is extra, *Agent Prompt Guide* became *Iteration Guide*, and *Known Gaps* is new:
it records what the analysis could not see, which is worth keeping.

## Getting better output

- **Start in a fresh project.** The system anchors to the project it was scaffolded in;
  mixing brands mid-project muddles the tokens.
- **Keep asking for screens.** "Now build a pricing page" or "add an empty state" stays
  on-brand once the system exists.
- **Ask for variants.** Light/dark, compact/comfortable, marketing/app all branch cleanly
  from the base tokens.
- **Export the generated `SKILL.md`** into your skills folder to reuse the aesthetic
  without re-uploading.

## Brand and licensing

The catalog's files are *inspired by publicly observable design patterns*. They are not
official design systems, and nothing is affiliated with or endorsed by the named
companies. Trademarks, logos and proprietary typefaces stay with their owners.
Downstream use is on you: **use one as inspiration for an original system, not a 1:1
clone.** That is the reason `/make-design-system` adapts a file rather than copying it.
