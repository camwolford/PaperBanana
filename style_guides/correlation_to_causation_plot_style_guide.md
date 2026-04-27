# Correlation to Causation Statistical Plot Aesthetics Guide

## 0. How to read this guide

C2C charts are **Economist health-desk charts**, not academic-journal charts and not Excel-default charts. Reproduce the Economist look exactly:

- Pure white canvas, no border.
- Horizontal-only pale grey gridlines, no verticals.
- Top and right spines removed.
- Two saturated accent colours per chart, drawn from a fixed C2C palette.
- Lato or Open Sans throughout.
- Bold near-black title, one-line medium-grey strap subtitle, **no terminal periods on titles or fragment labels**.
- Inline coloured annotations next to the data, bold, in the matching series colour, no leader lines, no boxed callouts.
- Source/footnote line in mid-grey at the bottom-left, ending in a period.

If the chart looks like it could appear in *The Economist*'s daily chart slot, it is on-brand. If it looks like a Seaborn default, an Excel default, a Matplotlib default, or a NeurIPS-paper plot, it is off-brand.

---

## 1. The "Correlation to Causation" Look for plots

- **Vibe.** Editorial data-journalism for a literate non-specialist on a phone. Information-dense but airy. The data carries itself; chrome recedes.
- **Backgrounds.** Pure white `#FFFFFF`. No grey Seaborn backgrounds, no gradients, no paper textures, no tinted panels.
- **Argument carrying.** Every chart has one number, one bar, one line, or one trend that is the point. That element gets the primary accent (usually indigo). The comparison element gets the secondary accent. Everything else is mid-grey or pale grey.
- **Two-accent rule.** Each chart uses **exactly two** saturated accent colours from the four-colour set. Never three. Never four.
- **Accessibility.** Colour-blind friendliness comes from picking accent pairs with hue + lightness contrast (indigo + rust-orange; teal-green + coral-red). For black-and-white reproduction, combine colour with shape (circle vs square markers; solid vs hatched bars).

---

## 2. Detailed style options

### 2.1 Colour palette (C2C native)

Use these exact hexes. Do not substitute Wong-2011, Tableau defaults, or Anthropic-flavoured colours.

| Token | Hex | Role |
|---|---|---|
| **Indigo** (primary) | `#4B3FE4` | The argument-carrying bar / line / dot / callout. |
| **Teal-green** (primary) | `#1FA579` | Positive comparison / advancement / "good" arm. |
| **Rust-orange** (secondary) | `#C9531C` | Risk / failure / mortality / "bad" arm. |
| **Coral-red** (secondary) | `#D94B4B` | Negative biology (disease, develops X). Often the second arm in a two-class comparison. |
| **Near-black** | `#1A1A1A` | Title text only. Never used as a fill or stroke. |
| **Mid-grey** | `#6E7480` | Subtitle, axis labels, axis ticks, reference lines, source footnote, secondary type. |
| **Pale grey** | `#E5E7EB` | Horizontal gridlines only. Never used as type colour or as a fill. |
| **Background** | `#FFFFFF` | Pure white. |

**Categorical encoding.** Assign accent colours by semantic role, not by category index. The argument category is indigo (or teal-green if the argument is a positive outcome). The comparison category is rust-orange (or coral-red if disease/negative-biology framing). Non-argument receding categories are pale grey `#E5E7EB`.

**Sequential / heatmap encoding.** Use Viridis (perceptually uniform) for sequential. Use a custom indigo→white→rust-orange diverging scheme for diverging data. **Never** use rainbow / jet.

**Forbidden colours.** Pure black `#000000`, PowerPoint default blue/orange, Tableau-10 defaults, neon yellows/cyans, pastel decorative tints. The C2C palette above is closed.

### 2.2 Axes, gridlines, spines

- **Spines.** Top and right spines removed. Left and bottom spines retained as thin (~1 px) mid-grey `#6E7480` lines.
- **Gridlines.** **Horizontal only**, pale grey `#E5E7EB`, behind the data (low z-order). **No vertical gridlines.** Ever.
- **Ticks.** Mid-grey, short, outward-facing. Tick labels in Lato Regular ~11 pt, mid-grey.
- **Reference lines.** Dashed mid-grey `#6E7480` (HR=1, OR=1, baseline). **Never solid. Never coloured.**
- **Axis labels.** Lato Regular ~12 pt, mid-grey. **No terminal period.** Include unit in parentheses where applicable, e.g. "Hazard ratio", "Cells (millions)".

### 2.3 Typography

**Font family: Lato (preferred) or Open Sans (fallback).** Humanist sans-serifs only. Never geometric sans (Inter, IBM Plex, Poppins, Montserrat). Never serifs. Never mix families.

| Element | Weight | Size | Colour | Punctuation |
|---|---|---|---|---|
| **Chart title** | Bold | ~18 pt | Near-black `#1A1A1A` | No terminal period |
| **Strap subtitle** (one line under title) | Regular | ~13 pt | Mid-grey `#6E7480` | No terminal period |
| **Axis labels** | Regular | ~12 pt | Mid-grey | No terminal period |
| **Tick labels** | Regular | ~11 pt | Mid-grey | No terminal period |
| **Inline coloured annotations** | Bold | ~12 pt | Matching series colour | No terminal period |
| **Direct labels** (line / bar / dot labels) | Bold | ~11 pt | Matching series colour | No terminal period |
| **Source / footnote** | Italic-feel Regular | ~9 pt | Mid-grey | **Period at end (full sentence)** |

**Sentence case** for titles and panel headers. Acronyms keep their casing (HR, OR, RCT, MR, FM, EHR, BMI).

### 2.4 Annotations and legends

- **Inline coloured annotations** are the default. Place the annotation next to the data point it describes, in the matching series colour, bold weight. **No leader lines.** **No boxed callouts.** **No drop shadows.**
- **Direct labels** preferred over external legends wherever they don't crowd. Label the line at its endpoint, in the line's colour.
- **Legends** sit below the plot, centred, with small filled square swatches and Lato Regular ~11 pt labels. Use only when direct labels would crowd.

### 2.5 Density budget for charts

A chart that obeys the C2C density rule has:

1. **One** title line (bold near-black, fragment, no period)
2. **One** strap subtitle line (regular mid-grey, fragment, no period)
3. **The data**, with at most two saturated accent colours
4. **One** inline coloured annotation marking the argument-carrying point
5. **Axis labels** in mid-grey, fragment, no period
6. **One** source/footnote line at the bottom-left ending in a period

Anything beyond this list — explanatory text blocks inside the plot area, multi-line callouts, secondary annotations, watermarks — is over-budget.

---

## 3. Type-specific guidelines

### 3.1 Bar charts and histograms
- Solid fills, no outlines. Argument bar uses indigo (or teal-green for positive framing). Comparison bar uses rust-orange (or coral-red for negative-biology framing).
- Bars grouped tightly within categories; generous whitespace between groups.
- Error bars: thin mid-grey lines with flat caps.
- Numeric labels above or inside bars: Lato Bold ~11 pt, in the bar's colour.

### 3.2 Line charts
- Lines: 2–2.5 px solid strokes for primary data; dashed for theoretical limits or null reference lines.
- Markers at every data point: filled circles for primary, filled squares or triangles for secondary categories.
- Uncertainty bands: semi-transparent shaded fills (alpha ~0.2) in the line's colour. Not vertical error bars.
- Argument line in indigo (or teal-green); comparison line in rust-orange (or coral-red).
- Direct endpoint labels preferred over a legend.

### 3.3 Scatter plots
- Solid filled markers, fully opaque for the argument category.
- For two-class encoding, combine colour and shape (indigo circle vs rust-orange square).
- Non-argument groups: pale grey `#E5E7EB` at full opacity, or accent colour at ~30% opacity for dense scatters.

### 3.4 Forest / effect-size plots
- Effect estimates: solid filled markers. Confidence intervals: horizontal lines through the marker, in the same colour.
- Reference line (null effect, HR=1, OR=1): vertical dashed mid-grey line. Never solid. Never coloured.
- Argument estimate(s) in indigo. Non-significant estimates in pale grey `#E5E7EB`.
- Variant names left-aligned on the left; point estimate + CI numbers right-aligned on the right.

### 3.5 Heatmaps
- Square cells.
- Annotate every cell with its numeric value in Lato Regular ~10 pt. Use automatic black/white text colour for contrast against the cell fill.
- Cell separators: very thin white lines, not borders.
- Sequential: Viridis. Diverging: custom indigo→white→rust-orange.

### 3.6 Dot / lollipop plots
- Lollipops (dots connected to the axis by a thin mid-grey line) for ranked comparisons.
- Argument dot in indigo. Comparison dots in rust-orange or pale grey.

### 3.7 Pie / donut charts
- Donuts only, never solid pies.
- Thick white separators between slices.
- Slice "explosion" used sparingly to highlight the argument-carrying slice.
- Direct slice labels with the percentage in bold inside the slice. No external legend if direct labels fit.

---

## 4. Common pitfalls

1. **Excel / Seaborn / Matplotlib defaults** — grey backgrounds, heavy black axis spines, default colour cycles, drop shadows, 3D effects, serif fallback fonts.
2. **Pure black** for any element. Use near-black `#1A1A1A` for title text only.
3. **Vertical gridlines.** Horizontal-only, always.
4. **Top and right spines retained.** Always remove both.
5. **Three or more saturated accent colours.** Two only.
6. **Pastel decorative tints** (mint, peach, sky-blue, lavender). The palette is saturated.
7. **Periods at the end of titles, subtitles, axis labels, fragment annotations.** Periods only on the source/footnote line.
8. **Geometric sans-serifs.** Inter, IBM Plex, Poppins, Montserrat — all wrong.
9. **Rainbow / jet colormaps.** Outdated and perceptually misleading.
10. **External legends when direct labels would do.** Direct labels preferred.
11. **Y-axis truncation that exaggerates the argument.** Show zero baseline for proportional data; sensible domain for ratio data.
12. **Boxed callouts with leader lines.** Annotations are inline coloured bold text, no box, no leader.
13. **Hatched / patterned fills** on bars unless the chart is for B&W reproduction. Solid fills by default.
14. **Mobile illegibility.** Charts must read at ~600 px Substack mobile width. If text would fall below ~9 pt at that width, cut data points or simplify the chart, not the text.

---

## 5. Drop-in usage

This guide is the C2C plot analogue to `neurips2025_plot_style_guide.md`. Activate by:

```bash
export PAPERBANANA_STYLE_GUIDE_PREFIX=correlation_to_causation
```

before launching PaperBanana. The Stylist agent will read `correlation_to_causation_plot_style_guide.md` for plot tasks; the NeurIPS files remain available for any non-C2C work.

---

## 6. Authorial note for the model

When in doubt, ask: *"Would this chart fit naturally on the daily-chart slot of The Economist's website?"* If yes, it is on-brand. If it looks like a Seaborn default, a NeurIPS supplementary figure, or a corporate-deck slide, it is off-brand and must be redrawn.
