---
name: Game-key fulfilment platform · Case study
description: Enterprise customer-story page told through failure modes; monochrome with one signal-blue accent, white and black themes.
colors:
  ground-light: "#ffffff"
  ground-dark: "#000000"
  subtle-light: "#f7f7f8"
  subtle-dark: "#09090b"
  surface-light: "#ffffff"
  surface-dark: "#0f0f11"
  ink-light: "#0b0b0c"
  ink-dark: "#f4f4f5"
  body-light: "#2f2f35"
  body-dark: "#d4d4d8"
  muted-light: "#5c5c66"
  muted-dark: "#a1a1aa"
  line-light: "#e7e7ea"
  line-dark: "#232327"
  line-strong-light: "#d2d2d7"
  line-strong-dark: "#34343a"
  signal-blue-light: "#1d4ed8"
  signal-blue-dark: "#7c9dff"
  signal-blue-strong-light: "#1e40af"
  signal-blue-strong-dark: "#a5bcff"
  signal-blue-soft-light: "#eef2ff"
  signal-blue-soft-dark: "#0f1830"
  inverse-body-light: "#d4d4d8"
  inverse-body-dark: "#3f3f46"
  inverse-muted-light: "#a1a1aa"
  inverse-muted-dark: "#52525b"
  diagram-stroke-light: "#a1a1aa"
  diagram-stroke-dark: "#52525b"
  diagram-edge-light: "#52525b"
  diagram-edge-dark: "#a1a1aa"
typography:
  display:
    fontFamily: "Schibsted Grotesk, system-ui, sans-serif"
    fontSize: "clamp(2.3rem, 5.4vw, 4rem)"
    fontWeight: 750
    lineHeight: 1.02
    letterSpacing: "-0.035em"
  headline:
    fontFamily: "Schibsted Grotesk, system-ui, sans-serif"
    fontSize: "clamp(1.7rem, 3.2vw, 2.35rem)"
    fontWeight: 720
    lineHeight: 1.15
    letterSpacing: "-0.025em"
  title:
    fontFamily: "Schibsted Grotesk, system-ui, sans-serif"
    fontSize: "1.12rem"
    fontWeight: 650
    lineHeight: 1.3
  body:
    fontFamily: "Schibsted Grotesk, system-ui, sans-serif"
    fontSize: "17px"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Schibsted Grotesk, system-ui, sans-serif"
    fontSize: "0.78rem"
    fontWeight: 650
    letterSpacing: "0.06em"
  code:
    fontFamily: "JetBrains Mono, ui-monospace, monospace"
    fontSize: "0.82em"
    fontWeight: 500
rounded:
  xs: "6px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  pill: "999px"
spacing:
  card: "24px"
  section: "clamp(3rem, 7vw, 5rem)"
  gutter: "clamp(1.25rem, 4vw, 2.5rem)"
components:
  button-primary:
    backgroundColor: "{colors.signal-blue-light}"
    textColor: "{colors.ground-light}"
    rounded: "{rounded.pill}"
    height: "44px"
  button-secondary:
    backgroundColor: "{colors.surface-light}"
    textColor: "{colors.ink-light}"
    rounded: "{rounded.pill}"
    height: "44px"
  card:
    backgroundColor: "{colors.surface-light}"
    rounded: "{rounded.md}"
    padding: "24px"
---

# Design system

## Overview

North star (documenter's call, not user-confirmed): **the failure-first case file**. An enterprise customer-story page
(Stripe / Linear / Vercel craft level) for a Read-mode surface: a calm reading column inside a frame that commits to
monochrome and one signal blue. The blue marks only what matters: links, the active section, primary actions, the
money-critical paths in diagrams, tier labels and summary headings.

Themes: one token set written with `light-dark()`. `color-scheme: light dark` follows the system; `<html data-theme>`
pins a choice saved in `localStorage`. `data-resolved` mirrors the effective theme for icon swaps.

## Colors

Restrained strategy: neutrals plus exactly one accent. Pairs are light / dark.

- Ground `#ffffff` / `#000000`; subtle `#f7f7f8` / `#09090b`; surface `#ffffff` / `#0f0f11`.
- Ink (headings, strong) `#0b0b0c` / `#f4f4f5`; body `#2f2f35` / `#d4d4d8`; muted `#5c5c66` / `#a1a1aa`.
- Lines `#e7e7ea` / `#232327`, strong lines `#d2d2d7` / `#34343a`.
- Signal blue `#1d4ed8` / `#7c9dff`, strong `#1e40af` / `#a5bcff`, soft fill `#eef2ff` / `#0f1830`.
- Inverse blocks (business-needs card, contact band) use ink as ground and ground as text.

## Typography

Schibsted Grotesk (variable 400-900, self-hosted, OFL) for everything; JetBrains Mono 500 only for code and state names
(`PENDING`, `PROCESSING`). Display 4rem max at -0.035em; section headlines ~2.35rem; titles 1.12rem/650; body 17px/1.65
(16px under 560px); uppercase tracked labels only inside cards and table heads, never above headings. Prose capped at
68ch, captions 62ch, source notes 60ch. `text-wrap: balance` on headings, `pretty` on body.

## Layout

- Container 1360px max with fluid gutters; hero full width, then a 200px sticky "On this page" rail beside the article.
- Under 1024px the rail becomes a collapsible "On this page" panel at the top of the article.
- Grids: 3-up (summary, personas, roadmap), 2-up (context, decisions, insights, results); all collapse to one column
  under 860px. Tables stack into labelled blocks under 640px.
- Diagrams keep their drawn size (min 880px) so labels stay >= 12px; on narrow screens they scroll sideways in a
  focusable, labelled region with a visible hint.

## Elevation & Depth

Light theme: hairline border plus a soft two-layer shadow (`0 1px 2px` and `0 10px 30px -16px`, both low alpha). Dark
theme: hairlines only, no shadow. Sticky top bar uses a translucent ground with backdrop blur and a 2px accent
reading-progress bar on its bottom edge.

## Shapes

12px cards, figures and tables; 16px for the contact band; pills for buttons, tier labels and the theme toggle; 6px
for inline code. Borders are 1px; the only thicker strokes are diagram emphasis (2-2.4px).

## Components

- **Top bar:** product label + "· Case study", theme toggle, Contact; under 560px the label shortens to "Game-key platform" and toggle/Contact become 40px icon buttons.
- **Buttons:** primary (blue fill), secondary (surface with strong line), small variant 36px for the top bar; all 44px
  tall elsewhere.
- **Decision ledger:** 2px ink top rule, hairline rows: title column + Risk / Decision / Result; money-critical rows lead with a larger title and a filled tier pill.
- **Ruled columns:** 2px ink top rule, no box (summary, roadmap).
- **Card:** surface, 1px line, 12px radius, 24px padding. Variants: inverse; decision card with Risk / Decision /
  Result definition list (Result label in blue); persona card with Job / Pain points / What they got.
- **Figure:** header row (title + "Figure n"), diagram region, caption on the subtle surface.
- **Table:** in a bordered wrap; uppercase muted head; tabular numerals for values; tier pills (critical filled blue,
  important outlined blue, other neutral).
- **Lists:** hairline-separated insight list; check list with a drawn blue check; numbered step cards for lessons.
- **Diagrams (inline SVG):** classes `box`, `core` (blue soft fill), `ext`, `actor`, `ok` (heavy ink stroke),
  `bad` (dashed), `warn`, `note-box`, `edge`, `edge strong` (blue), `lbl` (halo only on line labels).
- **Contact band:** inverse block with three link tiles (email, phone, GitHub).

## Do's and Don'ts

- Do keep one accent; new emphasis comes from weight, size or the inverse block, not a second hue.
- Do label figures that come from documentation as such; never invent business metrics.
- Do keep the client, supplier and providers anonymous.
- Don't put eyebrow/kicker labels above headings or number the sections.
- Don't use thick coloured side borders on cards, gradient text, or glass as decoration.
- Don't scale diagrams below their drawn size to fit; let them scroll.
