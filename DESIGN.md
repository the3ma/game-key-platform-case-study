---
name: Game-key fulfilment platform · Case study
description: Shared case-study world, a night transit map - one order or export rides a line through named stations; colour lives only on lines and station marks.
colors:
  ground-dark: "#0a0e14"
  ground-light: "#f6f8fb"
  surface-dark: "#111823"
  surface-light: "#ffffff"
  ink-dark: "#eef2f7"
  ink-light: "#0b1220"
  body-dark: "#c9d1dc"
  body-light: "#2a3446"
  muted-dark: "#8e9aab"
  muted-light: "#556173"
  line-dark: "#1d2633"
  line-light: "#e2e7ee"
  line-strong-dark: "#2c3848"
  line-strong-light: "#c9d2de"
  export-line-dark: "#f5a524"
  export-line-light: "#d97706"
  audit-line-dark: "#f0508a"
  audit-line-light: "#be185d"
  notify-line-dark: "#3ec6e0"
  notify-line-light: "#0e7490"
typography:
  display:
    fontFamily: "Overpass, system-ui, sans-serif"
    fontSize: "clamp(2.5rem, 5.6vw, 4.25rem)"
    fontWeight: 800
    lineHeight: 1.02
    letterSpacing: "-0.035em"
  headline:
    fontFamily: "Overpass, system-ui, sans-serif"
    fontSize: "clamp(1.75rem, 3.2vw, 2.4rem)"
    fontWeight: 800
    lineHeight: 1.15
  title:
    fontFamily: "Overpass, system-ui, sans-serif"
    fontSize: "1.12rem"
    fontWeight: 700
  body:
    fontFamily: "Overpass, system-ui, sans-serif"
    fontSize: "17px"
    fontWeight: 400
    lineHeight: 1.65
  code:
    fontFamily: "Overpass Mono, ui-monospace, monospace"
    fontSize: "0.84em"
    fontWeight: 500
rounded:
  xs: "4px"
  sm: "8px"
  md: "16px"
  pill: "999px"
spacing:
  module: "8px"
components:
  button-primary:
    backgroundColor: "{colors.ink-dark}"
    textColor: "{colors.ground-dark}"
    rounded: "{rounded.pill}"
    height: "48px"
  button-secondary:
    textColor: "{colors.ink-dark}"
    rounded: "{rounded.pill}"
    height: "48px"
---

# Design system

## Overview

A night transit map for a Read-mode case study. The export is a line; stages are stations (request, claim, plan,
parts, zip, completed); the audit and notify paths are their own lines. Dark (night map) by default, light (day map)
by toggle, one token set via `light-dark()`.

## Colors

Achromatic text and surfaces. Exactly three colours, used only on lines and station marks: **export** amber,
**audit** magenta, **notify** cyan (light-theme values darkened for contrast). Links are ink text on an export-line
underline. Primary buttons are an ink fill with an amber station ring.

## Typography

Overpass (variable, self-hosted, OFL; signage lineage) for everything; Overpass Mono only for identifiers and code.
Overpass's middot sits off-centre: inside SVG labels use commas or arrows instead.

## Layout

8px module; container 1360px; a 216px sticky contents rail beside the article above 1024px, a sticky collapsible
contents panel below. Grids collapse at 860px; tables stack at 640px; the hero line map turns vertical at 560px.

## Shapes

Round station dots (16px rail, 24px heading marker) with 4px rings; 6px rails in diagrams; 16px radius on figures,
tables and the contact panel; pills for buttons.

## Components

- **Contents rail:** a 4px line with a station per section; passed stations ring amber, the current one fills; the
  line fills to it; the last station (Contact) becomes current when its section is in view.
- **Station list** (`.stations`): hairline rows marked by a station ring.
- **Ruled columns** (`.ruled-3`): 4px top rule, first in export colour; personas use export / audit / notify.
- **Ledger** (`.ledger`): 4px export rule, rows of title + ADR link and Context / Decision / Result.
- **Figures:** header (title + "Figure n"), diagram region (scrolls sideways under 860px, "swipe" hint), caption.
- **Contact panel:** one bordered panel with a three-line strip on top; contacts as ruled rows.

## Do's and Don'ts

- Do put colour only on lines, rails and station marks.
- Don't use cards for groups of equals; use ruled columns, station lists or the ledger.
- Don't nest bordered tiles inside panels.
- Don't use monospace for prose.

