---
version: alpha
name: Fieldnote
description: A quiet log for birders, used mostly on a phone in the field and sometimes on a laptop at home. The marketing surface reads as a calm editorial spread on a **near-black, faintly green** canvas (`#161A17`) holding white display type over full-bleed dawn-light bird photography. The app inverts that — a **white** working canvas for the sightings table, because it is read outdoors in daylight. The single brand colour is **Fieldnote Green** (`#2F6B4F`), used scarcely on primary actions, the wordmark, and the lifer highlight (a species seen for the first time). Type runs **Inter** at modest weights (display 500, body 400) with tabular figures for counts and times. Spacing follows an explicit 8px token ladder (`xxxs` 4px through `super` 128px).

colors:
  primary: "#2F6B4F"
  primary-hover: "#24513C"
  primary-active: "#214C38"
  ink: "#ffffff"
  body: "#A3A3A3"
  body-strong: "#ffffff"
  body-on-light: "#161A17"
  muted: "#858585"
  muted-on-light: "#5F6661"
  muted-soft: "#5C5C5C"
  hairline: "#2D332F"
  hairline-on-light: "#D2D6D3"
  hairline-soft: "#EBEDEB"
  canvas: "#161A17"
  canvas-elevated: "#2D332F"
  canvas-light: "#ffffff"
  surface-card: "#2D332F"
  surface-soft-light: "#F6F7F6"
  surface-strong-light: "#EBEDEB"
  on-primary: "#ffffff"
  on-dark: "#ffffff"
  on-light: "#161A17"
  focus-ring: "#2F6B4F"
  focus-ring-on-dark: "#6FBF95"
  semantic-info: "#367599"
  semantic-success: "#2F6B4F"
  semantic-error: "#B3261E"

typography:
  display-mega:
    fontFamily: "'Inter', -apple-system, system-ui, sans-serif"
    fontSize: 80px
    fontWeight: 500
    lineHeight: 1.05
    letterSpacing: -1.6px
  display-xl:
    fontFamily: "'Inter', sans-serif"
    fontSize: 56px
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: -1.12px
  display-lg:
    fontFamily: "'Inter', sans-serif"
    fontSize: 36px
    fontWeight: 500
    lineHeight: 1.2
    letterSpacing: -0.36px
  display-md:
    fontFamily: "'Inter', sans-serif"
    fontSize: 26px
    fontWeight: 500
    lineHeight: 1.5
    letterSpacing: 0.195px
  title-md:
    fontFamily: "'Inter', sans-serif"
    fontSize: 18px
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0
  title-sm:
    fontFamily: "'Inter', sans-serif"
    fontSize: 16px
    fontWeight: 500
    lineHeight: 1.4
    letterSpacing: 0.08px
  body-lg:
    fontFamily: "'Inter', sans-serif"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  body-md:
    fontFamily: "'Inter', sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  body-sm:
    fontFamily: "'Inter', sans-serif"
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  caption:
    fontFamily: "'Inter', sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: 0
  caption-uppercase:
    fontFamily: "'Inter', sans-serif"
    fontSize: 11px
    fontWeight: 600
    lineHeight: 1.4
    letterSpacing: 1.1px
    textTransform: uppercase
  button:
    fontFamily: "'Inter', sans-serif"
    fontSize: 14px
    fontWeight: 700
    lineHeight: 1.0
    letterSpacing: 1.4px
    textTransform: uppercase
  nav-link:
    fontFamily: "'Inter', sans-serif"
    fontSize: 13px
    fontWeight: 600
    lineHeight: 1.4
    letterSpacing: 0.65px
    textTransform: uppercase
  number-display:
    fontFamily: "'Inter', sans-serif"
    fontSize: 80px
    fontWeight: 700
    lineHeight: 1.0
    letterSpacing: -1.6px
    fontFeatureSettings: "'tnum'"
  number-table:
    fontFamily: "'Inter', sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
    fontFeatureSettings: "'tnum'"

rounded:
  none: 0px
  xs: 2px
  sm: 4px
  md: 6px
  lg: 8px
  xl: 12px
  full: 9999px

spacing:
  xxxs: 4px
  xxs: 8px
  xs: 16px
  sm: 24px
  md: 32px
  lg: 48px
  xl: 64px
  xxl: 96px
  super: 128px

components:
  top-nav-on-dark:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.nav-link}"
    height: 64px
  top-nav-on-light:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.nav-link}"
    height: 64px
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button}"
    rounded: "{rounded.none}"
    padding: 14px 32px
    height: 48px
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.none}"
  button-primary-active:
    backgroundColor: "{colors.primary-active}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.none}"
  button-outline-on-dark:
    backgroundColor: transparent
    textColor: "{colors.ink}"
    typography: "{typography.button}"
    rounded: "{rounded.none}"
    padding: 13px 31px
    height: 48px
  button-outline-on-light:
    backgroundColor: transparent
    textColor: "{colors.body-on-light}"
    typography: "{typography.button}"
    rounded: "{rounded.none}"
    padding: 13px 31px
    height: 48px
  button-tertiary-text:
    backgroundColor: transparent
    textColor: "{colors.ink}"
    typography: "{typography.button}"
  hero-band-photo:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.display-mega}"
    padding: 0
  hero-band-light:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.display-xl}"
    padding: 96px
  feature-card-photo:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.title-md}"
    rounded: "{rounded.none}"
    padding: 0
  feature-card-light:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.title-md}"
    rounded: "{rounded.none}"
    padding: 32px
  accent-band:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.display-lg}"
    padding: 96px
  pricing-card:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.body-md}"
    rounded: "{rounded.none}"
    padding: 24px
  stat-cell:
    backgroundColor: transparent
    textColor: "{colors.ink}"
    typography: "{typography.number-display}"
    padding: 24px 0
  lifer-cell:
    backgroundColor: transparent
    textColor: "{colors.primary}"
    typography: "{typography.number-display}"
  species-card:
    backgroundColor: "{colors.canvas-elevated}"
    textColor: "{colors.ink}"
    typography: "{typography.title-md}"
    rounded: "{rounded.none}"
    padding: 24px
  filter-bar:
    backgroundColor: "{colors.surface-soft-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.body-md}"
    rounded: "{rounded.none}"
    padding: 16px
  sightings-table-header:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.muted-on-light}"
    typography: "{typography.caption-uppercase}"
    padding: 8px 16px
  sightings-table-row:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.number-table}"
    padding: 12px 16px
    height: 48px
  sighting-row-stacked:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.body-md}"
    padding: 16px 0
  empty-state:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.display-md}"
    padding: 64px 24px
  text-input-on-dark:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-lg}"
    rounded: "{rounded.sm}"
    padding: 12px 16px
    height: 48px
  text-input-on-light:
    backgroundColor: "{colors.canvas-light}"
    textColor: "{colors.body-on-light}"
    typography: "{typography.body-lg}"
    rounded: "{rounded.sm}"
    padding: 12px 16px
    height: 48px
  badge-pill:
    backgroundColor: "{colors.surface-strong-light}"
    textColor: "{colors.primary}"
    typography: "{typography.caption-uppercase}"
    rounded: "{rounded.full}"
    padding: 4px 12px
  cta-band-dark:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.display-lg}"
    padding: 96px
  footer-dark:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.body}"
    typography: "{typography.body-sm}"
    padding: 64px 48px
  footer-link:
    backgroundColor: transparent
    textColor: "{colors.body}"
    typography: "{typography.body-sm}"
---

## Overview

Fieldnote is a sighting log that tries to get out of the way. Its landing page reads like
a quiet nature-magazine spread: a **near-black, faintly green** canvas (`{colors.canvas}`
— #161A17) holding white display type, opened by a full-bleed photograph of a bird in
early light. The app is the opposite pole: a **white** working canvas
(`{colors.canvas-light}`) for the sightings table, because birders read it on a phone,
outdoors, often in full sun, where a dark screen washes out.

That split — dark for the story, light for the work — is the system's backbone. Pricing
and the app are "light bands"; everything that sells the feeling of a dawn walk is dark.

The single brand colour is **Fieldnote Green** (`{colors.primary}` — #2F6B4F). It marks
the one thing to do on a screen (Start your list, Filter, Save sighting), the wordmark,
and the **lifer** — the first time a birder logs a species, the product's one moment of
celebration. Everything else is greyscale.

Type is **Inter** as a single family at modest weights — display 500, body 400. Labels on
buttons and nav are uppercase with wide tracking, which keeps actions legible at arm's
length without making them loud. Counts and times use tabular figures so a column of
sightings lines up.

**Key Characteristics:**
- Single accent: `{colors.primary}` for primary actions, the wordmark, lifer highlights. Used scarcely.
- Dark canvas for marketing, white canvas for the app. Never pure black.
- Single sans family: Inter across every role, with `tnum` for numbers.
- Display weight stays at 500 — never bold.
- Button and nav labels uppercase with tracked letter-spacing.
- Sharp `{rounded.none}` corners on buttons, cards and bands; pills only for badges.
- Photography carries the depth on marketing pages; hairlines carry it in the app.
- 48px minimum for anything tappable — the field is cold hands and gloves.

## Colors

### Brand & Accent
- **Fieldnote Green** (`{colors.primary}` — #2F6B4F): The existing brand colour, kept as-is. Primary action fill, wordmark, lifer highlight. White text on it is 6.3:1.
- **Green Hover** (`{colors.primary-hover}` — #24513C): Pointer hover on laptop. Derived at 0.76× the base's HSL lightness.
- **Green Active** (`{colors.primary-active}` — #214C38): Press state. 0.71× the base's lightness — one step deeper than hover.
- **Focus Ring** (`{colors.focus-ring}` — #2F6B4F) on light surfaces, **Focus Ring On Dark** (`{colors.focus-ring-on-dark}` — #6FBF95) on dark ones. The base green is only 2.8:1 against the dark canvas, so dark surfaces get a lifted green (8.0:1).

### Surface
- **Canvas** (`{colors.canvas}` — #161A17): Near-black marketing floor with a trace of green, so the dark pages feel like dusk in a wood rather than a screen turned off.
- **Canvas Elevated** (`{colors.canvas-elevated}` — #2D332F): Cards and panels on dark.
- **Canvas Light** (`{colors.canvas-light}` — #ffffff): The app floor, and pricing on the landing page.
- **Surface Card** (`{colors.surface-card}` — #2D332F): Alias of canvas-elevated for species cards.
- **Surface Soft Light** (`{colors.surface-soft-light}` — #F6F7F6): Filter bar, alternating bands.
- **Surface Strong Light** (`{colors.surface-strong-light}` — #EBEDEB): Badge fills, selected rows.

### Hairlines
- **Hairline** (`{colors.hairline}` — #2D332F): 1px divider on dark.
- **Hairline On Light** (`{colors.hairline-on-light}` — #D2D6D3): Row dividers in the sightings table.
- **Hairline Soft** (`{colors.hairline-soft}` — #EBEDEB): Lighter divider inside cards.

### Text
- **Ink** (`{colors.ink}` — #ffffff): Display and emphasis on dark.
- **Body** (`{colors.body}` — #A3A3A3): Running text on dark. 7.0:1 on canvas, 5.1:1 on canvas-elevated.
- **Body Strong** (`{colors.body-strong}` — #ffffff): Alias of ink.
- **Body On Light** (`{colors.body-on-light}` — #161A17): Running text in the app.
- **Muted** (`{colors.muted}` — #858585): Captions on dark. 4.8:1 — lifted from a darker grey so captions pass AA.
- **Muted On Light** (`{colors.muted-on-light}` — #5F6661): Table headers, timestamps, secondary text in the app. 5.9:1.
- **Muted Soft** (`{colors.muted-soft}` — #5C5C5C): Disabled text on dark only.
- **On Primary** (`{colors.on-primary}` — #ffffff): Text on Fieldnote Green.

### Semantic
- **Info** (`{colors.semantic-info}` — #367599): Sync status, tips. 5.1:1 on white.
- **Success** (`{colors.semantic-success}` — #2F6B4F): Deliberately the brand green — one green in the system, not two competing ones. Always paired with a text label.
- **Error** (`{colors.semantic-error}` — #B3261E): Validation ("Count must be a number"). 6.5:1 on white.

## Typography

### Font Family
**Inter** (Google Fonts) across every role. Fallback: `-apple-system, system-ui, sans-serif`. No display/body split. Inter is chosen over a more characterful face for one product reason: its tabular figures (`tnum`) keep counts and times aligned in a dense table.

### Hierarchy

| Token | Size | Weight | Line Height | Letter Spacing | Use |
|---|---|---|---|---|---|
| `{typography.display-mega}` | 80px | 500 | 1.05 | -1.6px | Landing hero h1 |
| `{typography.display-xl}` | 56px | 500 | 1.1 | -1.12px | Secondary heroes |
| `{typography.display-lg}` | 36px | 500 | 1.2 | -0.36px | Section heads, accent band |
| `{typography.display-md}` | 26px | 500 | 1.5 | 0.195px | App page title, empty-state heading |
| `{typography.title-md}` | 18px | 700 | 1.2 | 0 | Card and pricing-tier titles |
| `{typography.title-sm}` | 16px | 500 | 1.4 | 0.08px | Species name in stacked rows |
| `{typography.body-lg}` | 16px | 400 | 1.5 | 0 | Form inputs, marketing body |
| `{typography.body-md}` | 14px | 400 | 1.5 | 0 | Default app body |
| `{typography.body-sm}` | 13px | 400 | 1.5 | 0 | Footer |
| `{typography.caption}` | 12px | 400 | 1.4 | 0 | Photo credits, notes |
| `{typography.caption-uppercase}` | 11px | 600 | 1.4 | 1.1px | Table headers, badges |
| `{typography.button}` | 14px | 700 | 1.0 | 1.4px (uppercase) | Button labels |
| `{typography.nav-link}` | 13px | 600 | 1.4 | 0.65px (uppercase) | Nav items |
| `{typography.number-display}` | 80px | 700 | 1.0 | -1.6px (tnum) | Life-list total, lifer count |
| `{typography.number-table}` | 14px | 400 | 1.5 | 0 (tnum) | Count and time columns |

### Principles
- **Display weight stays at 500.** The photograph and the birds do the talking; type stays calm.
- **Button and nav labels are uppercase and tracked.** Readable at a glance, at arm's length, without raising the volume.
- **Inputs are 16px.** Smaller inputs make iOS Safari zoom the page on focus, which is maddening one-handed in the field.
- **Negative tracking on display only.** Body stays at 0.
- **Numbers are tabular.** Any column of counts or times uses `{typography.number-table}`.

## Layout

### Spacing System
- **Base unit:** 4px.
- **Tokens:** `{spacing.xxxs}` 4px · `{spacing.xxs}` 8px · `{spacing.xs}` 16px · `{spacing.sm}` 24px · `{spacing.md}` 32px · `{spacing.lg}` 48px · `{spacing.xl}` 64px · `{spacing.xxl}` 96px · `{spacing.super}` 128px.
- **Marketing sections:** `{spacing.xxl}` between bands; `{spacing.super}` reserved for the hero.
- **App:** `{spacing.xs}` page gutter on mobile, `{spacing.md}` on desktop; `{spacing.sm}` between filter bar and table.

### Grid & Container
- Landing: max content width ~1280px; hero photography goes full-bleed. Features 3-up, pricing 2-up.
- App: max width ~1080px — a table wider than that is harder to scan, not easier.
- Footer: a single row on the landing page; there is little to link to yet.

### Whitespace Philosophy
Two densities. Marketing pages breathe — generous bands, one idea per screen. The app is dense on purpose: as many sightings as fit, divided by hairlines rather than boxes, so a birder tidying the day's list can see it whole.

## Elevation & Depth

Depth comes from **photography and brightness steps**, not shadows.

| Level | Treatment | Use |
|---|---|---|
| Flat (dark) | `{colors.canvas}` | Marketing bands, footer |
| Card (dark) | `{colors.canvas-elevated}` | Species cards |
| Flat (light) | `{colors.canvas-light}` | App, pricing |
| Recessed (light) | `{colors.surface-soft-light}` | Filter bar |
| Hairline | 1px `{colors.hairline}` or `{colors.hairline-on-light}` | Dividers, card outlines |
| Soft drop | `0 4px 8px rgba(0,0,0,0.1)` | Menus and popovers only — the one shadow |
| Photographic | Full-bleed bird photography | Landing hero, feature cards |

### Decorative Depth
- **Hero scrim** (`linear-gradient(180deg, transparent, rgba(22,26,23,0.85) 64%)`): darkens the bottom of the hero photo so the headline stays legible over a bright sky.
- No brand-colour gradients. The green appears flat or not at all.

## Shapes

### Border Radius Scale

| Token | Value | Use |
|---|---|---|
| `{rounded.none}` | 0px | Buttons, cards, bands, table — the default |
| `{rounded.xs}` | 2px | Checkbox corners |
| `{rounded.sm}` | 4px | Text inputs, selects |
| `{rounded.md}` | 6px | Menus, popovers |
| `{rounded.lg}` | 8px | Bottom sheet on mobile (top corners only) |
| `{rounded.xl}` | 12px | Dialogs (rare) |
| `{rounded.full}` | 9999px | Badges, avatar |

Sharp by default. The square edges read as a notebook and a ruler — precise, unfussy. Inputs get a slight radius so they read as fields, not buttons. Pills are for badges only.

## Components

### Top Navigation

**`top-nav-on-dark`** — Landing nav over the hero. Background `{colors.canvas}`, text `{colors.ink}`, type `{typography.nav-link}`, 64px tall. Wordmark left; Features / Pricing middle; "Open the app" right as `button-outline-on-dark`.

**`top-nav-on-light`** — App nav. Background `{colors.canvas-light}`, text `{colors.body-on-light}`, 1px `{colors.hairline-on-light}` bottom border. Current page carries a 2px `{colors.primary}` underline.

### Buttons

**`button-primary`** — The one action per screen. Background `{colors.primary}`, text `{colors.on-primary}`, type `{typography.button}`, 14px × 32px padding, 48px tall, `{rounded.none}`.

**`button-primary-hover`** — Background `{colors.primary-hover}`. Documented because the app is used on laptops at home.

**`button-primary-active`** — Background `{colors.primary-active}`.

**`button-outline-on-dark`** / **`button-outline-on-light`** — Transparent, 1px border in the text colour, same geometry. Secondary actions ("Clear filters", "Open the app").

**`button-tertiary-text`** — Inline text action, uppercase and tracked.

All buttons take a 2px focus outline offset 2px, in `{colors.focus-ring}` on light and `{colors.focus-ring-on-dark}` on dark.

### Hero Bands

**`hero-band-photo`** — Full-bleed photograph of a bird in early light. Headline in `{typography.display-mega}` sits over the hero scrim at the bottom of the photo. One `button-primary` ("Start your list"), nothing else competing.

**`hero-band-light`** — White variant for secondary pages (help, changelog). 96px padding.

### Cards

**`feature-card-photo`** — Photo-first feature card on dark. Image edge-to-edge on top; title in `{typography.title-md}` and one line of `{colors.body}` beneath.

**`feature-card-light`** — White variant, 32px padding.

**`species-card`** — A species on the life list. Background `{colors.canvas-elevated}`, 24px padding: photo, common name, first-seen date and place.

**`pricing-card`** — Free and Flock tiers. Background `{colors.canvas-light}`, `{rounded.none}`, 24px padding, 1px `{colors.hairline-on-light}` border. Tier name in `{typography.title-md}`, price in `{typography.display-lg}`. Only the paid tier's button is `button-primary`.

### Editorial Surfaces

**`accent-band`** — A full-width green band, background `{colors.primary}`, text `{colors.on-primary}`, `{typography.display-lg}`. At most once per page — usually the line just before pricing.

**`cta-band-dark`** — Pre-footer band on `{colors.canvas}`, centred `{typography.display-lg}` headline, one `button-primary`.

### Counts

**`stat-cell`** — A big number with a label: life-list total, species this year. Value in `{typography.number-display}`, label below in `{typography.caption-uppercase}`.

**`lifer-cell`** — Same geometry, value in `{colors.primary}`. Used for the lifer count, and nowhere else at this size.

### App: Sightings

**`filter-bar`** — Background `{colors.surface-soft-light}`, 16px padding. Search, place select, "Lifers only" checkbox and the Filter button on one row at desktop; stacked on mobile.

**`sightings-table-header`** — `{typography.caption-uppercase}` in `{colors.muted-on-light}`, 1px `{colors.hairline-on-light}` bottom border.

**`sightings-table-row`** — 48px minimum height, 1px `{colors.hairline-on-light}` divider, no zebra striping. Count and When columns use `{typography.number-table}`, right-aligned for Count. A lifer row carries a `badge-pill` reading "Lifer" in the Note column.

**`sighting-row-stacked`** — The mobile form of a table row: species in `{typography.title-sm}`, then count · place · time in `{typography.body-md}` / `{colors.muted-on-light}`, hairline-divided.

**`empty-state`** — Heading in `{typography.display-md}`, one sentence of help, one `button-outline-on-light`.

### Forms & Tags

**`text-input-on-light`** — Background `{colors.canvas-light}`, 1px `{colors.hairline-on-light}` border, `{rounded.sm}`, 48px tall, `{typography.body-lg}`. Error state: border and message in `{colors.semantic-error}`, message below the field, never colour alone.

**`text-input-on-dark`** — Same geometry on `{colors.canvas}` with a `{colors.hairline}` border.

**`badge-pill`** — Background `{colors.surface-strong-light}`, text `{colors.primary}`, `{typography.caption-uppercase}`, `{rounded.full}`. "Lifer", "Synced", "Flock".

### Footer

**`footer-dark`** — Background `{colors.canvas}`, text `{colors.body}`, 64px × 48px padding.

**`footer-link`** — `{typography.body-sm}` in `{colors.body}`, underline on hover.

## Do's and Don'ts

### Do
- Reserve `{colors.primary}` for the one primary action per screen, the wordmark, and lifers.
- Keep marketing dark and the app light. The app is read outdoors.
- Use `{typography.number-table}` for every count and time column.
- Make every tappable thing at least 48px tall.
- Use the 8px spacing ladder rather than ad-hoc values.
- Keep display weight at 500.

### Don't
- Don't add a second saturated colour. Success is the brand green; info and error are the only other hues, and only for status.
- Don't round buttons or cards. Pills are for badges.
- Don't put a dark mode in the app by inverting the landing palette without checking it in daylight first.
- Don't use pure black. The canvas is `{colors.canvas}`.
- Don't add shadow tiers. One soft drop, for menus and popovers.
- Don't use zebra striping in the table — hairlines only. Striping fights with the selected-row fill.
- Don't add a feed, likes, or counters that compare one birder with another. "Quiet by design" is a product promise, and the visuals keep it.

## Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
|---|---|---|
| Mobile | < 640px | Hero h1 80→36px; features 1-up; pricing 1-up; sightings table becomes `sighting-row-stacked`; filter bar stacks. |
| Tablet | 640–1024px | Hero h1 56px; features 2-up; table shows Species / Count / When, hides Place and Note behind row tap. |
| Desktop | 1024–1280px | Full hero; features 3-up; full table. |
| Wide | > 1280px | Landing caps at 1280px, app at 1080px; hero photo stays full-bleed. |

### Touch Targets
- Buttons, inputs and table rows are 48px tall — above WCAG's 44px, and sized for gloves.
- The "Lifers only" checkbox has a 48px label hit area, not just the 16px box.

### Collapsing Strategy
- Mobile is the primary app surface. Design the stacked row first; the desktop table is the expansion.
- Top nav stays visible on mobile in the app (three items fit); the landing nav collapses below 768px.
- The hero photo is art-directed per breakpoint — wide on desktop, cropped to the bird on mobile.

## Iteration Guide

1. Work one component at a time, starting from the mobile app surfaces.
2. Buttons and cards default to `{rounded.none}`; badges are the only pills.
3. Add variants as separate entries under `components:`.
4. Cite `{token.refs}` everywhere — no inline hex in prose or components.
5. Hover is documented for primary buttons and links; other hover states inherit a brightness step.
6. Inter 500 for display, 400/700 for body; uppercase and tracking on buttons and nav.
7. Keep the green scarce. If a screen has two green things, one of them is wrong.
8. Check every new screen outdoors-bright: light canvas, ≥ 4.5:1 text.

## Known Gaps

- **App dark mode** is not decided. Dawn and dusk birding argue for one; daylight readability argues against making it the default. The landing palette is not automatically valid for it.
- **Photography direction** (species, light, crop, credit placement) is described in one line, not specified. It carries most of the marketing page's feel.
- **Logo/wordmark** does not exist yet; the nav uses the name set in `{typography.nav-link}`.
- **Motion** (row insert after logging, lifer moment) is out of scope.
- **Offline and sync states** — the badge exists, but the full pending/failed/synced pattern is not designed.
- **Log-a-sighting flow** (the three-tap entry) is not covered; only the table and filters are.
