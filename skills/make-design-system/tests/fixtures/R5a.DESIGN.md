---
version: alpha
name: Fieldnote
description: The design language for Fieldnote, a quiet sighting log for hobbyist birders. A near-monochrome system of green-black ink on warm paper-white, with one forest green reserved for the action that matters on each screen, a neutral sans for everything narrative and a monospaced face for the field data itself — counts, times, places. Built to be read on a phone in daylight first and on a laptop second.

colors:
  primary: "#2F6B4F"
  primary-deep: "#2A5F46"
  primary-soft: "#DEE8E3"
  on-primary: "#FFFFFF"
  ink: "#1A1F1C"
  body: "#4A514D"
  mute: "#636A65"
  hairline: "#E8E9E4"
  hairline-strong: "#A3A79F"
  canvas: "#FFFFFF"
  canvas-soft: "#FAFAF7"
  canvas-soft-2: "#F3F4EF"
  inverse: "#1A1F1C"
  on-inverse: "#FFFFFF"
  link: "#2F6B4F"
  link-deep: "#2A5F46"
  success: "#2F6B4F"
  success-soft: "#DEE8E3"
  error: "#B42318"
  error-soft: "#FBE4E1"
  error-deep: "#8F1C13"
  warning: "#E0A030"
  warning-soft: "#FBEFD5"
  warning-deep: "#8A5208"
  selection-bg: "#1A1F1C"
  selection-fg: "#F3F4EF"

typography:
  display-xl:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 48px
    fontWeight: 600
    lineHeight: 48px
    letterSpacing: -2.4px
  display-lg:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 32px
    fontWeight: 600
    lineHeight: 40px
    letterSpacing: -1.28px
  display-md:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 24px
    fontWeight: 600
    lineHeight: 32px
    letterSpacing: -0.96px
  display-sm:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 20px
    fontWeight: 600
    lineHeight: 28px
    letterSpacing: -0.6px
  body-lg:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 18px
    fontWeight: 400
    lineHeight: 28px
    letterSpacing: 0px
  body-md:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 16px
    fontWeight: 400
    lineHeight: 24px
  body-md-strong:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 16px
    fontWeight: 500
    lineHeight: 24px
  body-sm:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 14px
    fontWeight: 400
    lineHeight: 20px
    letterSpacing: -0.28px
  body-sm-strong:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 14px
    fontWeight: 500
    lineHeight: 20px
    letterSpacing: -0.28px
  caption:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 12px
    fontWeight: 400
    lineHeight: 16px
  caption-mono:
    fontFamily: IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace
    fontSize: 12px
    fontWeight: 400
    lineHeight: 16px
  data-mono:
    fontFamily: IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace
    fontSize: 13px
    fontWeight: 400
    lineHeight: 20px
  button-md:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 14px
    fontWeight: 500
    lineHeight: 20px
  button-lg:
    fontFamily: Inter, system-ui, -apple-system, sans-serif
    fontSize: 16px
    fontWeight: 500
    lineHeight: 24px

rounded:
  none: 0px
  xs: 4px
  sm: 6px
  md: 8px
  lg: 12px
  xl: 16px
  pill: 100px
  full: 9999px

spacing:
  xxs: 4px
  xs: 8px
  sm: 12px
  md: 16px
  lg: 24px
  xl: 32px
  2xl: 40px
  3xl: 48px
  4xl: 64px
  5xl: 96px
  6xl: 128px
  section: 192px

components:
  nav-bar:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-sm}"
    height: 64px
    padding: "{spacing.sm} {spacing.lg}"
  nav-link:
    textColor: "{colors.body}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.full}"
    padding: "{spacing.xs} {spacing.sm}"
  nav-cta:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.body-sm-strong}"
    rounded: "{rounded.pill}"
    padding: "0px {spacing.sm}"
    height: 36px
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button-lg}"
    rounded: "{rounded.pill}"
    padding: "0px {spacing.lg}"
    height: 48px
  button-secondary:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    borderColor: "{colors.hairline}"
    typography: "{typography.button-lg}"
    rounded: "{rounded.pill}"
    padding: "0px {spacing.lg}"
    height: 48px
  app-button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button-md}"
    rounded: "{rounded.sm}"
    padding: "0px {spacing.sm}"
    height: 44px
  app-button-secondary:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    borderColor: "{colors.hairline}"
    typography: "{typography.button-md}"
    rounded: "{rounded.sm}"
    padding: "0px {spacing.sm}"
    height: 44px
  card-feature:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  card-soft:
    backgroundColor: "{colors.canvas-soft-2}"
    textColor: "{colors.ink}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  pricing-card:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-md}"
    rounded: "{rounded.lg}"
    padding: "{spacing.xl}"
  pricing-card-featured:
    backgroundColor: "{colors.inverse}"
    textColor: "{colors.on-inverse}"
    typography: "{typography.body-md}"
    rounded: "{rounded.lg}"
    padding: "{spacing.xl}"
  form-input:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    borderColor: "{colors.hairline-strong}"
    typography: "{typography.body-md}"
    rounded: "{rounded.sm}"
    padding: "0px {spacing.sm}"
    height: 44px
  form-input-sm:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    borderColor: "{colors.hairline-strong}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.sm}"
    padding: "0px {spacing.sm}"
    height: 36px
  checkbox:
    backgroundColor: "{colors.canvas}"
    borderColor: "{colors.hairline-strong}"
    checkedColor: "{colors.primary}"
    rounded: "{rounded.xs}"
    size: 20px
  data-table:
    headerBackground: "{colors.canvas-soft}"
    headerTextColor: "{colors.mute}"
    headerTypography: "{typography.caption-mono}"
    bodyTypography: "{typography.body-sm}"
    numericTypography: "{typography.data-mono}"
    cellPadding: "{spacing.sm} {spacing.sm}"
    rowBorder: "{colors.hairline}"
    rowMinHeight: 44px
  badge-lifer:
    backgroundColor: "{colors.primary-soft}"
    textColor: "{colors.primary-deep}"
    typography: "{typography.caption}"
    rounded: "{rounded.full}"
    padding: "0px {spacing.xs}"
  badge-neutral:
    backgroundColor: "{colors.canvas-soft-2}"
    textColor: "{colors.body}"
    typography: "{typography.caption}"
    rounded: "{rounded.full}"
    padding: "0px {spacing.xs}"
  sync-status:
    pendingBackground: "{colors.warning-soft}"
    pendingText: "{colors.warning-deep}"
    syncedText: "{colors.mute}"
    typography: "{typography.caption-mono}"
  empty-state:
    backgroundColor: "{colors.canvas-soft}"
    textColor: "{colors.body}"
    rounded: "{rounded.lg}"
    padding: "{spacing.3xl}"
    typography: "{typography.body-md}"
  hero-band:
    backgroundColor: "{colors.canvas-soft}"
    textColor: "{colors.ink}"
    typography: "{typography.display-xl}"
    padding: "{spacing.5xl} {spacing.lg}"
  section-band:
    backgroundColor: "{colors.canvas-soft}"
    textColor: "{colors.ink}"
    typography: "{typography.display-lg}"
    padding: "{spacing.4xl} {spacing.lg}"
  footer:
    backgroundColor: "{colors.canvas-soft}"
    textColor: "{colors.body}"
    typography: "{typography.body-sm}"
    padding: "{spacing.4xl} {spacing.lg}"
  link-inline:
    textColor: "{colors.link}"
    typography: "{typography.body-md}"
  toast:
    backgroundColor: "{colors.inverse}"
    textColor: "{colors.on-inverse}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.md}"
    padding: "{spacing.sm} {spacing.md}"
  focus-ring:
    color: "{colors.primary}"
    inverseColor: "{colors.on-inverse}"
    width: 2px
    offset: 2px

---

## Overview

Fieldnote is a sighting log for hobbyist birders, and its whole promise is that it gets out of the way. Someone standing on a marsh boardwalk with one hand on their binoculars should be able to log a Cedar Waxwing in three taps and put the phone back in their pocket. Later, at a laptop, they tidy the day's list in a dense table. The design system serves both moments with the same small vocabulary.

The surface is near-monochrome: green-black `{colors.ink}` text on warm paper-white `{colors.canvas-soft}`, with a gray ladder that gives every divider, border and secondary label its own step. Colour appears in exactly one place per screen — forest green `{colors.primary}`, Fieldnote's existing brand colour, marks the action that matters (log a sighting, start your list, filter) and the one thing a birder is proud of (a lifer). Everything else is ink and paper. There is no decorative system; whitespace and type do the work, which is the visual form of "no feed, no likes."

Type has two voices. A neutral sans (Inter) carries everything narrative. A monospaced face (IBM Plex Mono) carries the *field data*: counts, timestamps, place captions, table headers. That split is borrowed from field notebooks, where the observation is prose and the tally is a column of figures.

**Key Characteristics:**

- One accent, used scarcely: `{colors.primary}` for the primary action, focus, links and the lifer badge. Never for decoration, never for large fills outside a button.
- Mono is for data, never for sentences. A count of 14 and "Sep 23, 17:05" are mono; "Wading, north pond" is sans.
- Light-first, because the main use is a phone in daylight. All text clears 4.5:1, including the lowest-priority `{colors.mute}`, which the field context makes non-negotiable.
- Touch targets are 44 px in the app, everywhere, because gloves and cold fingers are part of the brief.
- Elevation is quiet: stacked hairline shadows, never a heavy drop. The one strong depth cue is a polarity flip to `{colors.inverse}`, used for the featured pricing tier and for toasts.

## Colors

### Brand & Accent

- **Forest** (`{colors.primary}` — `#2F6B4F`): Fieldnote's brand colour and the only accent. Primary buttons, the nav CTA, focus rings, inline links, checked checkboxes. White text on it is 6.3:1.
- **Forest Deep** (`{colors.primary-deep}` — `#2A5F46`): Hover and pressed state for anything in `{colors.primary}`. Derived at the same lightness step (×0.89 in HSL lightness) that the source system used between its base and pressed link colours. White on it is 7.4:1.
- **Forest Soft** (`{colors.primary-soft}` — `#DEE8E3`): The lifer badge fill and the selected-row tint. `{colors.primary-deep}` text on it is 5.9:1.

### Surface

- **Canvas Soft** (`{colors.canvas-soft}` — `#FAFAF7`): The default page background. A warm 98 % white, so the page reads as paper rather than a screen.
- **Canvas** (`{colors.canvas}` — `#FFFFFF`): Cards, inputs, table bodies — anything that should sit slightly forward of the page.
- **Canvas Soft 2** (`{colors.canvas-soft-2}` — `#F3F4EF`): Inset regions, neutral badges, row hover.
- **Inverse** (`{colors.inverse}` — `#1A1F1C`): The polarity-flipped surface. Featured pricing tier and toasts only.
- **Hairline** (`{colors.hairline}` — `#E8E9E4`): 1 px dividers between table rows and around cards.
- **Hairline Strong** (`{colors.hairline-strong}` — `#A3A79F`): Input and checkbox borders. At 2.5:1 on white it is a boundary, not text; never set copy in it.

### Text

- **Ink** (`{colors.ink}` — `#1A1F1C`): Headings, body, table cells. A near-black nudged toward green so it sits with the brand colour rather than against it. 16:1 on the page.
- **Body** (`{colors.body}` — `#4A514D`): Secondary text, nav links, notes column, footer.
- **Mute** (`{colors.mute}` — `#636A65`): Placeholders, table headers, "synced" status, fine print. Deliberately darker than a typical placeholder gray: 5.0:1 even on `{colors.canvas-soft-2}`, so it survives sunlight.
- **On Primary** / **On Inverse** (`{colors.on-primary}`, `{colors.on-inverse}` — `#FFFFFF`): Text on forest and on inverse surfaces.

### Semantic

- **Success** (`{colors.success}` — `#2F6B4F`) / **Success Soft** (`{colors.success-soft}`): Reuses the brand green, so "saved" and "synced" confirmations don't introduce a second green.
- **Warning** (`{colors.warning}` — `#E0A030`): An ochre dot for "pending sync" — the offline-first state. Indicator only, never text.
- **Warning Soft** (`{colors.warning-soft}`) / **Warning Deep** (`{colors.warning-deep}` — `#8A5208`): The pending-sync chip; deep-on-soft is 5.6:1.
- **Error** (`{colors.error}` — `#B42318`) / **Error Soft** (`{colors.error-soft}`) / **Error Deep** (`{colors.error-deep}`): Validation and destructive actions. A brick red rather than a pure red, so an error stays legible without shouting in a quiet interface.
- **Selection** (`{colors.selection-bg}` / `{colors.selection-fg}`): Text selection inverts to ink on paper.

## Typography

### Font Family

1. **Inter** (Google Fonts, 400 / 500 / 600) for every heading, paragraph, button and label. Enable `font-feature-settings: "tnum"` wherever numbers line up in columns. Weight 600 is the ceiling.
2. **IBM Plex Mono** (Google Fonts, 400) at 12–13 px for field data: counts, timestamps, coordinates, table headers, sync status. Plex Mono's softer, slightly humanist shapes keep the data column from reading as code.

### Hierarchy

| Token | Size | Weight | Line Height | Letter Spacing | Use |
|---|---|---|---|---|---|
| `{typography.display-xl}` | 48px | 600 | 48px | -2.4px | Landing hero ("Every bird you've seen, in one quiet place."). |
| `{typography.display-lg}` | 32px | 600 | 40px | -1.28px | Landing section headlines; app page title on desktop. |
| `{typography.display-md}` | 24px | 600 | 32px | -0.96px | Pricing tier names, app page title on mobile, empty-state title. |
| `{typography.display-sm}` | 20px | 600 | 28px | -0.6px | Feature-card titles. |
| `{typography.body-lg}` | 18px | 400 | 28px | 0 | Hero lead paragraph. |
| `{typography.body-md}` | 16px | 400 | 24px | 0 | Default body, form inputs on mobile. |
| `{typography.body-md-strong}` | 16px | 500 | 24px | 0 | Inline emphasis, species name in a mobile list. |
| `{typography.body-sm}` | 14px | 400 | 20px | -0.28px | Table cells, nav links, secondary copy. |
| `{typography.body-sm-strong}` | 14px | 500 | 20px | -0.28px | Species column in the table, nav CTA. |
| `{typography.caption}` | 12px | 400 | 16px | 0 | Badges, footer fine print. |
| `{typography.caption-mono}` | 12px | 400 | 16px | 0 | Table headers (uppercase, +0.04em), sync status, eyebrows. |
| `{typography.data-mono}` | 13px | 400 | 20px | 0 | Counts, timestamps, prices. |
| `{typography.button-md}` | 14px | 500 | 20px | 0 | App buttons. |
| `{typography.button-lg}` | 16px | 500 | 24px | 0 | Landing CTAs. |

### Principles

- **Tight tracking at display sizes is the voice.** The negative tracking makes a short headline feel composed and calm rather than loud. Keep it.
- **Sentence case, period-terminated headlines.** "Built for the field." The full stop is part of the quiet tone; it reads as a statement, not a slogan.
- **Mono is the tally column.** If it's a number, a time or a place-as-metadata, it's mono. If it's a sentence, it isn't.
- **Uppercase only in mono table headers and eyebrows**, with slight positive tracking. Sans text is never uppercase.
- **16 px minimum for inputs on mobile**, which also prevents iOS from zooming on focus.

## Layout

### Spacing System

- **Base unit:** 4 px. Every value is a multiple.
- **Tokens:** `{spacing.xxs}` 4 · `{spacing.xs}` 8 · `{spacing.sm}` 12 · `{spacing.md}` 16 · `{spacing.lg}` 24 · `{spacing.xl}` 32 · `{spacing.2xl}` 40 · `{spacing.3xl}` 48 · `{spacing.4xl}` 64 · `{spacing.5xl}` 96 · `{spacing.6xl}` 128 · `{spacing.section}` 192.
- **Landing bands:** `{spacing.4xl}` to `{spacing.5xl}` top and bottom. The hero gets `{spacing.5xl}`; with no decorative backdrop it doesn't need `{spacing.section}`, which is reserved for a future illustrated hero.
- **App density:** table cells at `{spacing.sm}`, filter controls gapped at `{spacing.sm}`, page gutter `{spacing.md}` on mobile and `{spacing.lg}` on desktop.
- **Card interiors:** `{spacing.lg}` for feature cards, `{spacing.xl}` for pricing cards.

### Grid & Container

- **Landing max width:** 1120 px, centred. Narrower than a typical marketing page because the content is short; a wide container would make three features look sparse.
- **App max width:** 1280 px, so the five-column sightings table fits without horizontal scroll on a laptop.
- **Column patterns:** features 3-up; pricing 2-up (Free and Flock, Flock featured on the right); filters as a single wrapping row above the table.

### Whitespace Philosophy

Large gaps between bands, tight stacks inside them. A card's heading and paragraph sit `{spacing.xs}` apart, then a wider gap before its action. In the app the same rule shrinks: the filter row and the table are one unit, with the caption ("12 sightings this week") bridging them. Whitespace is Fieldnote's only decoration, so it is never filled for the sake of it.

## Elevation & Depth

| Level | Treatment | Use |
|---|---|---|
| Level 0 — Flat | No shadow, no border. | Page bands, the table on mobile. |
| Level 1 — Inset Hairline | `0 0 0 1px #1A1F1C14` inset. | Default card and table container chrome. |
| Level 2 — Subtle Drop | `0px 1px 1px #1A1F1C05, 0px 2px 2px #1A1F1C0A` plus inset hairline. | Feature cards, pricing cards. |
| Level 3 — Float | `0px 2px 2px #1A1F1C0A, 0px 8px 16px -4px #1A1F1C0A` plus inset hairline. | Dropdowns (the place select), popovers. |
| Level 4 — Modal | `0px 1px 1px #1A1F1C05, 0px 8px 16px -4px #1A1F1C0A, 0px 24px 32px -8px #1A1F1C0F` plus inset hairline. | Log-a-sighting sheet, dialogs. |

Shadows are stacked small offsets tinted with `{colors.ink}` rather than pure black, so they sit on the warm paper instead of greying it. The ring is always present so an edge stays crisp in glare, where a soft shadow alone would disappear.

The strongest depth cue is not a shadow but polarity: `{colors.inverse}` on the featured pricing tier and on toasts. Use it sparingly, or it stops meaning "this one."

## Shapes

### Border Radius Scale

| Token | Value | Use |
|---|---|---|
| `{rounded.none}` | 0px | Full-bleed bands, the table on mobile. |
| `{rounded.xs}` | 4px | Checkboxes. |
| `{rounded.sm}` | 6px | App buttons, inputs, selects — the base in-app radius. |
| `{rounded.md}` | 8px | Feature cards, table container, toasts. |
| `{rounded.lg}` | 12px | Pricing cards, empty state, the log-a-sighting sheet. |
| `{rounded.xl}` | 16px | Reserved for future photo cards. |
| `{rounded.pill}` | 100px | Landing CTAs and the nav CTA. |
| `{rounded.full}` | 9999px | Badges, nav-link hover pill, icon buttons. |

**The two button shapes split by surface, not by importance.** The landing page uses `{rounded.pill}`; the app uses `{rounded.sm}`. A pill reads as an invitation, a 6 px rectangle as a tool. The nav CTA ("Open the app") is a pill because it lives on the landing page. Never mix the two shapes within one surface.

## Components

### Buttons

**`button-primary`** — the landing CTA ("Start your list", "Go Flock"). `{colors.primary}` fill, `{colors.on-primary}` label in `{typography.button-lg}`, `{rounded.pill}`, 48 px tall. Hover and pressed to `{colors.primary-deep}`.

**`button-secondary`** — its partner. `{colors.canvas}` fill, `{colors.ink}` label, 1 px `{colors.hairline}` border, same shape. Used for "Get started" on the Free tier so it doesn't compete with the featured Flock card next to it.

**`app-button-primary`** — "Filter", "Save sighting". `{colors.primary}` fill, `{typography.button-md}`, `{rounded.sm}`, 44 px tall. One per view.

**`app-button-secondary`** — "Clear filters", "Cancel". `{colors.canvas}` with a `{colors.hairline}` border.

**`focus-ring`** — every interactive element: 2 px `{colors.primary}` outline at 2 px offset. On `{colors.inverse}` surfaces the ring switches to `{colors.on-inverse}`. Focus is always visible; it is never removed for mouse users without a `:focus-visible` replacement.

### Navigation

**`nav-bar`** — 64 px, `{colors.canvas}`, wordmark left in `{typography.body-sm-strong}`, links in `{typography.body-sm}` `{colors.body}`. On the landing page the right slot holds **`nav-cta`** ("Open the app", `{colors.primary}` pill, 36 px with a 44 px hit area). In the app the right slot is empty and the current page carries `aria-current` with `{colors.ink}` text and a `{colors.canvas-soft-2}` pill.

**`nav-link`** — ghost pill; `{rounded.full}` background appears only on hover or current page.

### Cards & Containers

**`card-feature`** — the three "Built for the field" cards. `{colors.canvas}`, `{spacing.lg}` padding, `{rounded.md}`, Level 2. Title in `{typography.display-sm}`, copy in `{typography.body-md}` `{colors.body}`.

**`card-soft`** — an inset grouping on `{colors.canvas-soft-2}` with no shadow.

**`pricing-card`** — the Free tier. `{colors.canvas}`, `{spacing.xl}` padding, `{rounded.lg}`, Level 2. Tier name in `{typography.display-md}`, price in `{typography.display-xl}` with the "/ month" in `{typography.data-mono}` `{colors.mute}`, feature list in `{typography.body-md}`.

**`pricing-card-featured`** — Flock. Polarity-flipped to `{colors.inverse}` with `{colors.on-inverse}` text. Its CTA inverts to a `{colors.on-inverse}` pill with `{colors.ink}` label. Forest green on the inverse card is only 2.7:1, too faint for a button edge, and the flipped card already marks this as the tier that matters.

### Inputs & Forms

**`form-input`** — 44 px, `{colors.canvas}`, 1 px `{colors.hairline-strong}` border (stronger than the source's hairline so the field edge holds in sunlight), `{typography.body-md}`, `{rounded.sm}`. Placeholder in `{colors.mute}`. Error state: `{colors.error}` border and a `{typography.caption}` message below in `{colors.error}`.

**`form-input-sm`** — 36 px, `{typography.body-sm}`. Desktop filter row only; never on touch layouts.

**`checkbox`** — 20 px box in a 44 px hit area (the whole label is clickable), `{rounded.xs}`, checked fill `{colors.primary}`.

Labels sit above or before their control in `{typography.body-sm}` `{colors.body}`. Every control has a visible label; placeholders are hints, not labels.

### Data

**`data-table`** — the sightings table. Container at Level 1 with `{rounded.md}`. Header row on `{colors.canvas-soft}` in `{typography.caption-mono}` uppercase `{colors.mute}`. Body cells in `{typography.body-sm}`; the Species column in `{typography.body-sm-strong}`; Count and When in `{typography.data-mono}` with tabular figures, Count right-aligned. Rows are separated by `{colors.hairline}`, at least 44 px tall, with `{colors.canvas-soft-2}` on hover. The `<caption>` sits above the table, left-aligned, in `{typography.body-sm}` `{colors.body}`.

**`badge-lifer`** — "Lifer" in `{colors.primary-deep}` on `{colors.primary-soft}`, `{rounded.full}`. The only place colour appears in a table row, so a lifer is findable at a glance.

**`badge-neutral`** — any other tag, on `{colors.canvas-soft-2}` in `{colors.body}`.

**`sync-status`** — sits by the page title. "Pending · 3" as a `{colors.warning-soft}` chip with `{colors.warning-deep}` text and a `{colors.warning}` dot; "Synced 07:12" as plain `{colors.mute}` text. Both in `{typography.caption-mono}`. Offline is a normal state, not an error, so it never uses red.

**`empty-state`** — "No sightings match". `{colors.canvas-soft}`, `{rounded.lg}`, `{spacing.3xl}` padding, title in `{typography.display-md}`, copy in `{typography.body-md}` `{colors.body}`, one `app-button-secondary` ("Clear filters").

### Feedback

**`toast`** — "Sighting saved". `{colors.inverse}` with `{colors.on-inverse}` text, `{rounded.md}`, Level 3, bottom-centre on mobile above the safe area. Announced through an `aria-live="polite"` region.

### Bands

**`hero-band`** — `{colors.canvas-soft}`, headline in `{typography.display-xl}`, lead in `{typography.body-lg}` `{colors.body}`, one `button-primary`. Left-aligned on desktop, so it reads like the first line of a notebook page rather than a billboard.

**`section-band`** — features and pricing. Headline in `{typography.display-lg}`.

**`footer`** — `{colors.canvas-soft}` with a top `{colors.hairline}`, copy in `{typography.body-sm}` `{colors.body}`.

**`link-inline`** — `{colors.link}`, underlined always (not just on hover), `{colors.link-deep}` when pressed. The underline is what tells a link from a heading in a near-monochrome system.

## Do's and Don'ts

### Do

- Keep `{colors.primary}` for one primary action per view, plus focus, links and lifers.
- Set every count, time and price in `{typography.data-mono}` with tabular figures.
- Use `{rounded.pill}` on the landing page and `{rounded.sm}` in the app.
- Keep every text colour at 4.5:1 or better on the surface it sits on, including `{colors.mute}`.
- Make every touch target at least 44 × 44 px in the app.
- Use the polarity flip to `{colors.inverse}` as the one strong emphasis.
- Write headlines in sentence case, ending with a full stop.

### Don't

- Don't add a second accent. If something needs to stand out and it isn't the primary action or a lifer, it probably doesn't need to stand out.
- Don't add decoration — gradients, textures, bird silhouettes as wallpaper. Quiet is the product.
- Don't set prose in mono or data in sans.
- Don't show offline or pending sync in red. It's expected, not broken.
- Don't use weight 700 or above.
- Don't drop a single heavy shadow on a card; use the stacked levels.
- Don't use `form-input-sm` or `{typography.caption}`-sized controls on touch layouts.
- Don't mix pill and 6 px buttons on the same surface.

## Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
|---|---|---|
| Mobile | < 600px | Primary target. Features 1-up, pricing stacks with Flock first. Sightings table becomes a list: species and count on line one, place and time in `{typography.data-mono}` `{colors.mute}` on line two, note below. Filters collapse behind a "Filter" button into a bottom sheet. |
| Tablet | 600–959px | Features 2-up then 1, pricing 2-up. Table shows Species, Count, Place, When; Note moves into an expandable row. |
| Desktop | 960–1279px | Full table, filter row inline with `form-input-sm`. |
| Wide | ≥ 1280px | Containers cap; bands stretch edge to edge in colour only. |

### Touch Targets

44 px minimum in the app at every breakpoint: buttons, inputs, checkboxes (via their label), table rows when tappable. The landing nav CTA is 36 px visually with padding extending the hit area to 44 px.

### Collapsing Strategy

- **Nav:** on mobile, the landing nav keeps the wordmark and "Open the app"; Features and Pricing move into a menu. The app nav keeps all three items; there are only three.
- **Display type:** `{typography.display-xl}` steps down to `{typography.display-lg}` below 600 px, keeping its tracking ratio.
- **Log a sighting:** on mobile, a fixed bottom `app-button-primary` spans the width above the safe area, because that is the three-tap path.

## Iteration Guide

Prompts to carry into Claude Design and the generated `SKILL.md`. Cite tokens as `{token.refs}`, not hex values.

- "Build the log-a-sighting sheet for mobile: species search, count stepper, place (defaulting to current location), time defaulting to now, optional note. One primary action. Level 4, `{rounded.lg}` top corners."
- "Build the Life list page: total count as a large `{typography.data-mono}` figure, then a grouped list by year, with lifers marked by `badge-lifer`."
- "Show the sightings table in its pending-sync state, with three rows not yet synced."
- "Make a compact variant of the sightings table for desktop power users: 36 px rows, `form-input-sm` filters."
- "Draft a dark variant for dawn and dusk use: invert the surface ladder, keep `{colors.primary}`, recheck every contrast pair."

When adding a component, decide first whether it lives on the landing surface or in the app; that settles its radius, height and button scale.

## Known Gaps

- **Dark mode is undecided.** Light-first is a deliberate default for daylight use, but birders are often out at dawn and dusk. A dark ladder needs its own contrast pass, and `{colors.primary}` will likely need a lighter companion for text on dark.
- **No imagery direction.** Whether birds appear at all (photography, line illustration, none) is open. `{rounded.xl}` and `{spacing.section}` are held in reserve for it.
- **No icon set chosen.** Needed at least for count stepper, location, sync and menu.
- **Wordmark not designed.** The nav uses the product name in type until there is one.
- **Map and location surfaces are unspecified**, though "where" is half of every sighting.
- **Data visualisation is not covered.** Life-list growth by year will want a chart palette that respects the single-accent rule.
- **Motion is unspecified** beyond toasts appearing; the bottom sheet needs a transition and a reduced-motion fallback.
- **The tokens are not yet wired into `styles/tokens.css`**, which still holds only `--brand`.
