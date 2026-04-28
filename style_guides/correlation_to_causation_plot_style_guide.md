# Correlation to Causation Statistical Plot Aesthetics Guide

## 0. How to read this guide

C2C charts are **Nature Reviews / NEJM data figures with Economist health-desk editorial register**, not academic-journal default charts and not Excel/Seaborn defaults. Reproduce the look exactly:

- Pure white canvas, no border.
- Horizontal-only structural-grey gridlines at 1 px, no verticals.
- Top, right, and bottom spines removed (frame-less).
- Three saturated accent colours allowed in the closed C2C palette; **at most two used per chart**.
- Open Sans throughout (Lato as fallback).
- Bold near-black title centred at the top, one-line strap subtitle in subtitle-grey beneath, **no terminal periods on titles or fragment labels**.
- **3 px** trend lines, **≥4 px radius** filled circular markers, **3 px** error-bar strokes with prominent end caps.
- Inline coloured annotations next to the data, bold, in the matching series colour, no leader lines, no boxed callouts.
- Source/footnote line in source-grey at the bottom, ending in a period.

If the chart looks like it could appear in a Nature Reviews data panel or *The Economist*'s daily chart slot, it is on-brand. If it looks like a Seaborn default, an Excel default, a Matplotlib default, or a NeurIPS-paper plot, it is off-brand.

**Core philosophy.** Strip away decorative elements so raw data takes precedence. White background and a vibrant categorical palette force focus on clinical metrics and biological pathways. Thin lines suggest uncertainty — they are forbidden.

---

## 1. The "Correlation to Causation" Look for plots

- **Vibe.** Editorial data-journalism for a literate non-specialist on a phone. Information-dense but airy. The data carries itself; chrome recedes.
- **Backgrounds.** Pure white `#FFFFFF`. No grey Seaborn backgrounds, no gradients, no paper textures, no tinted panels.
- **Argument carrying.** Every chart has one number, one bar, one line, or one trend that is the point. That element gets the primary accent (usually Primary Violet). The comparison element gets the secondary accent. Everything else is structural-grey or pale-grey.
- **Two-accent rule.** Each chart uses **at most two** saturated accent colours from the C2C palette. Never three. Never four.
- **Accessibility.** Colour-blind friendliness comes from picking accent pairs with hue + lightness contrast (Violet + Burnt-Orange; Vivid-Teal + Burnt-Orange). For black-and-white reproduction, combine colour with shape (circle vs square markers; solid vs hatched bars).

---

## 2. Detailed style options

### 2.1 Colour palette (C2C native, three saturated accents)

Use these exact hexes. Do not substitute Wong-2011, Tableau defaults, or matplotlib presets.

| Token | Hex | Role |
|---|---|---|
| **Primary Violet** | `#5A3BE8` | The argument-carrying bar / line / dot / callout. Observed values; treated arm; primary trend. |
| **Burnt Orange** | `#E86A21` | Counter-series, secondary data, exponential trend, risk / failure / mortality / "bad" arm. |
| **Vivid Teal** | `#00A884` | Clinical-trial markers, genetic-variant indicators, causal-valid effect estimates, "good" arm. |
| **Structural Gray** | `#888888` | Gridlines, tick labels, axis labels, dashed reference lines, neutral text annotations, secondary type. |
| **Subtitle grey** | `#666666` | One-line strap subtitle text. |
| **Source grey** | `#999999` | 9 pt source / footnote line text. |
| **Near-black (titles only)** | `#222222` | Title text. **Never used as a fill or stroke.** |
| **Background** | `#FFFFFF` | Pure white, mandatory. |

**Categorical encoding.** Assign accent colours by semantic role, not by category index. The argument category is Primary Violet (or Vivid Teal if the argument is a positive-outcome / causal claim). The comparison category is Burnt Orange. Non-argument receding categories are structural-grey or pale-grey `#E5E7EB`.

**Sequential / heatmap encoding.** Use Viridis (perceptually uniform) for sequential. Use a custom violet→white→burnt-orange diverging scheme for diverging data. **Never** use rainbow / jet.

**Forbidden colours.** Pure black `#000000`, PowerPoint default blue/orange, Tableau-10 defaults, neon yellows/cyans, pastel decorative tints. The C2C palette above is closed.

### 2.2 Axes, gridlines, spines

- **Spines.** Top, right, and bottom spines removed. Optional 1 px structural-grey `#888888` left spine for scale orientation; usually absent.
- **Gridlines.** **Horizontal only**, 1 px structural-grey `#888888`, behind the data (low z-order). **No vertical gridlines.** Ever.
- **Ticks.** Structural-grey, 10 pt Open Sans Regular tick labels positioned directly adjacent to gridlines. No tick marks; numeric labels float beside each gridline.
- **Reference lines.** **3 px dashed** structural-grey `#888888` (HR=1, OR=1, baseline). **Never solid. Never coloured.**
- **Axis labels.** Open Sans Regular 12 pt, structural-grey, central along their respective axes. **No terminal period.** Include unit in parentheses where applicable, e.g. "Hazard ratio", "Cells (millions)".
- **Log scales.** Clearly labelled.

### 2.3 Typography

**Font family: Open Sans (preferred) or Lato (fallback).** Humanist sans-serifs only. Never geometric sans (Inter, IBM Plex, Poppins, Montserrat). Never serifs. Never mix families.

| Element | Weight | Size | Colour | Alignment | Punctuation |
|---|---|---|---|---|---|
| **Chart title** | Bold | 16–20 pt | Near-black `#222222` | Centred at top | No terminal period |
| **Strap subtitle** (one line) | Regular | 13 pt | Subtitle grey `#666666` | Centred or left | No terminal period |
| **Axis labels** | Regular | 12 pt | Structural-grey `#888888` | Central along axis | No terminal period |
| **Tick labels** | Regular | 10 pt | Structural-grey `#888888` | Adjacent to gridline | No terminal period |
| **Inline coloured annotations** | Bold | 12 pt | Matching series colour | Adjacent to data | No terminal period |
| **Direct labels** (line / bar / dot labels) | Bold | 11 pt | Matching series colour | Adjacent to series | No terminal period |
| **Source / footnote** | Italic-feel Regular | 9 pt | Source grey `#999999` | Bottom centre or bottom left | **Period at end (full sentence)** |

**Sentence case** for titles and panel headers. Acronyms keep their casing (HR, OR, RCT, MR, FM, EHR, BMI).

### 2.4 Annotations and legends

- **Inline coloured annotations** are the default. Place the annotation next to the data point it describes, in the matching series colour, bold weight. **No leader lines.** **No boxed callouts.** **No drop shadows.**
- **Direct labels** preferred over external legends wherever they don't crowd. Label the line at its endpoint, in the line's colour.
- **Legends** sit below the plot, centred, with small filled square swatches and Open Sans Regular 10 pt labels. Use only when direct labels would crowd. Subtitle does the interpretive work — never use the legend to repeat the takeaway.

### 2.5 Data mechanics (line weights, nodes, error bars)

- **Trend lines and connecting paths: exactly 3 px thick.** Thin lines suggest uncertainty and are forbidden.
- **Data nodes: solid filled circles, ≥4 px radius (≥8 px diameter).** No hollow markers on argument-carrying data.
- **Error bars: 3 px stroke with prominent vertical end caps** of comparable thickness.
- **Horizontal grids: 1 px structural-grey, low z-order.** Vertical grids omitted.
- **Bar fills: solid colour, no outline stroke.**
- **Lines.** Solid for observed data; dashed (3 px) for theoretical / model / null reference lines.

### 2.6 Density budget for charts

A chart that obeys the C2C density rule has:

1. **One** title line (bold near-black, fragment, no period, centred at top)
2. **One** strap subtitle line (regular subtitle-grey, fragment, no period)
3. **The data**, with at most two saturated accent colours
4. **One** inline coloured annotation marking the argument-carrying point
5. **Axis labels** in structural-grey, fragment, no period
6. **One** source/footnote line at the bottom in source-grey ending in a period

Anything beyond this list — explanatory text blocks inside the plot area, multi-line callouts, secondary annotations, watermarks — is over-budget.

---

## 3. Type-specific guidelines

### 3.1 Bar charts and histograms
- Solid fills, no outlines. Argument bar uses Primary Violet (or Vivid Teal for positive framing). Comparison bar uses Burnt Orange.
- Bars grouped tightly within categories; generous whitespace between groups.
- Error bars: 3 px structural-grey strokes with flat end caps.
- Numeric labels above or inside bars: Open Sans Bold 11 pt, in the bar's colour.

### 3.2 Line charts
- Lines: **3 px solid strokes** for primary data; **3 px dashed** for theoretical limits or null reference lines.
- Markers at every data point: solid filled circles, **≥4 px radius**, in the line's colour. Squares or triangles for secondary categories.
- Uncertainty bands: semi-transparent shaded fills (alpha ~0.2) in the line's colour, never as substitutes for error bars on individual points.
- Argument line in Primary Violet (or Vivid Teal); comparison line in Burnt Orange.
- Direct endpoint labels preferred over a legend.

### 3.3 Scatter plots
- Solid filled markers, fully opaque for the argument category, **≥4 px radius**.
- For two-class encoding, combine colour and shape (Violet circle vs Burnt-Orange square).
- Non-argument groups: pale grey `#E5E7EB` at full opacity, or accent colour at ~30% opacity for dense scatters.

### 3.4 Forest / effect-size plots
- Effect estimates: solid filled markers, ≥4 px radius. Confidence intervals: **3 px horizontal lines** through the marker with prominent end caps, in the same colour.
- Reference line (null effect, HR=1, OR=1): **3 px dashed structural-grey** vertical line. Never solid. Never coloured.
- Argument estimate(s) in Vivid Teal. Non-significant estimates in pale grey `#E5E7EB`.
- Variant names left-aligned on the left; point estimate + CI numbers right-aligned on the right.

### 3.5 Heatmaps
- Square cells.
- Annotate every cell with its numeric value in Open Sans Regular 10 pt. Use automatic black/white text colour for contrast against the cell fill.
- Cell separators: very thin white lines, not borders.
- Sequential: Viridis. Diverging: custom violet→white→burnt-orange.

### 3.6 Dot / lollipop plots
- Lollipops (≥4 px filled dots connected to the axis by a 3 px structural-grey line) for ranked comparisons.
- Argument dot in Primary Violet. Comparison dots in Burnt Orange or pale grey.

### 3.7 Pie / donut charts
- Donuts only, never solid pies.
- Thick white separators between slices.
- Slice "explosion" used sparingly to highlight the argument-carrying slice.
- Direct slice labels with the percentage in bold inside the slice. No external legend if direct labels fit.

---

## 4. Common pitfalls

1. **Excel / Seaborn / Matplotlib defaults** — grey backgrounds, heavy black axis spines, default colour cycles, drop shadows, 3D effects, serif fallback fonts.
2. **Pure black** for any element. Use near-black `#222222` for title text only.
3. **Vertical gridlines.** Horizontal-only, always.
4. **Top, right, or bottom spines retained.** Always remove all three.
5. **Three or more saturated accent colours.** Two only.
6. **Pastel decorative tints** (mint, peach, sky-blue, lavender). The palette is saturated.
7. **Periods at the end of titles, subtitles, axis labels, fragment annotations.** Periods only on the source/footnote line.
8. **Geometric sans-serifs.** Inter, IBM Plex, Poppins, Montserrat — all wrong.
9. **Rainbow / jet colormaps.** Outdated and perceptually misleading.
10. **External legends when direct labels would do.** Direct labels preferred.
11. **Y-axis truncation that exaggerates the argument.** Show zero baseline for proportional data; sensible domain for ratio data.
12. **Boxed callouts with leader lines.** Annotations are inline coloured bold text, no box, no leader.
13. **Hatched / patterned fills** on bars unless the chart is for B&W reproduction. Solid fills by default.
14. **Thin lines (under 3 px)** on argument-carrying trends. Thin lines suggest uncertainty.
15. **Hollow markers** on argument-carrying data. Use solid filled markers ≥4 px radius.
16. **Mobile illegibility.** Charts must read at ~600 px Substack mobile width. If text would fall below ~9 pt at that width, cut data points or simplify the chart, not the text.

---

## 5. Drop-in usage

This guide is the C2C plot analogue to `neurips2025_plot_style_guide.md`. Activate by:

```bash
export PAPERBANANA_STYLE_GUIDE_PREFIX=correlation_to_causation
```

before launching PaperBanana. The Stylist agent will read `correlation_to_causation_plot_style_guide.md` for plot tasks; the NeurIPS files remain available for any non-C2C work.

---

## 6. Authorial note for the model

When in doubt, ask: *"Would this chart fit naturally on a Nature Reviews data panel or the daily-chart slot of The Economist's website?"* If yes, it is on-brand. If it looks like a Seaborn default, a NeurIPS supplementary figure, or a corporate-deck slide, it is off-brand and must be redrawn.
