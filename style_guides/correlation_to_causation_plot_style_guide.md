# Correlation to Causation Statistical Plot Aesthetics Guide

## 1. The "Correlation to Causation" Look for Plots

The prevailing aesthetic is **"Editorial Health-Desk Chart."** Imagine a chart from an Our World in Data explainer, an FT health-desk piece, or an NEJM results panel. Clean white background, restrained palette, the data carries itself.

- **Vibe:** Professional, editorial, information-dense, lay-readable. The reader is a literate non-specialist on a phone.
- **Backgrounds:** Pure white. No grey "Seaborn" backgrounds, no gradients, no paper textures.
- **Accessibility:** Wong-2011 colour-blind safe palette. Categories distinguish by colour AND by shape (markers, hatches), so the chart prints in black-and-white.
- **Argument carrying:** Every chart has one number or one trend that is the point. That element gets the indigo accent. Everything else is grey.

---

## 2. Detailed Style Options

### **Color Palettes**
Use the seven-token palette below for every chart. The semantics never shift between charts.

| Token | Hex | Role |
|---|---|---|
| Primary indigo | `#4f46e5` | The argument-carrying number, bar, line, or callout. |
| Accent green | `#009E73` | Advancement / positive direction. |
| Accent orange | `#D55E00` | Risk / failure / warning. |
| Accent purple | `#CC79A7` | Auxiliary category. |
| Light grey | `#bdbdbd` | Receding / non-focus bars, lines, and dots. |
| Mid grey | `#758091` | Axes, gridlines, secondary type. |
| Body text | `#1f2937` | Annotations and labels. |

- **Categorical data:** assign tokens by semantic role, not by category index. The argument-carrying category gets indigo; everything else is grey unless a second category needs distinguishing (use orange or purple).
- **Sequential / heatmap:** use Viridis (perceptually uniform). Avoid the rainbow/jet colormap.
- **Diverging:** use Coolwarm (blue-to-red).
- **Accessibility mode:** combine colour with hatches/dots/stripes when the chart will be printed in black-and-white.

### **Axes & Grids**
- **Grid style:** thin mid-grey dashed lines `#758091`, behind the data (low Z-order). No solid black gridlines.
- **Spines:** "open" style. Top and right spines removed; left and bottom spines kept as thin mid-grey lines.
- **Ticks:** subtle, inward-facing, or removed entirely if gridlines provide the alignment.
- **Axis labels:** Open Sans Regular ~12 pt, mid-grey, with a unit indication where applicable.

### **Layout & Typography**
- **Font family:** Open Sans (or nearest humanist sans-serif). No serif fonts for axis labels, titles, or annotations.
- **X-axis label rotation:** horizontal where space allows; 45° only when necessary to prevent overlap.
- **Legends:**
  - Internal placement (top-left or top-right inside plot area) preferred.
  - Single-row above-plot placement acceptable.
  - **Direct labelling next to lines or on top of bars** is preferred over external legends where it doesn't crowd.
- **Annotations:** indigo callouts mark the argument-carrying number. Use Open Sans Bold ~12 pt for the callout, with a thin indigo leader line if the callout sits away from the data point.

---

## 3. Type-Specific Guidelines

### **Bar Charts & Histograms**
- Solid colour fills, no outlines. Argument-carrying bar is indigo; non-argument bars are light grey `#bdbdbd`.
- Bars are grouped tightly within categories with significant whitespace between groups.
- Error bars use thin mid-grey lines with flat caps.
- Percentage numerals inside bars: Open Sans Regular ~9–10 pt, body-text colour.

### **Line Charts**
- Lines use solid strokes for primary data, dashed strokes for theoretical limits or baselines.
- Markers at every data point: circles for primary data, squares or triangles for secondary categories.
- Uncertainty bands use semi-transparent shaded fills (alpha ~0.2), not vertical error bars.
- Argument-carrying line is indigo; comparison lines are mid-grey `#758091`.

### **Pie / Donut Charts**
- Donuts preferred over pies.
- Thick white separators between slices.
- Use slice "explosion" sparingly to highlight the argument-carrying slice.
- Direct slice labels with values, not external legends.

### **Scatter Plots**
- Markers use solid fills, fully opaque.
- Combine colour and shape to encode two categorical dimensions simultaneously.
- Argument-carrying group is indigo; non-argument groups are light grey.
- For dense scatters, reduce non-argument-group opacity to ~30% rather than introducing a new colour.

### **Heatmaps**
- Square cells.
- Annotate every cell with its numeric value (Open Sans Regular ~10 pt, automatic black/white text colour for contrast against cell fill).
- Cells separated by very thin white lines, not borders.
- Use Viridis for sequential, Coolwarm for diverging.

### **Dot / Lollipop Plots**
- Dot plots styled as lollipops (dots connected to the axis by a thin line) for ranked comparisons.
- Argument-carrying dot is indigo; rest are light grey.

### **Forest Plots / Effect-Size Plots**
- Effect estimates as solid filled markers, confidence intervals as horizontal lines through the marker.
- Reference line (null effect) as a vertical mid-grey dashed line.
- Argument-carrying estimate(s) in indigo; non-significant estimates in light grey.
- Direct labels for variant names on the left, point estimates with CI on the right.

---

## 4. Common Pitfalls

1. **Excel default look.** Heavy 3D effects, drop shadows, serif fonts on axes.
2. **Rainbow / Jet colormaps.** Outdated and perceptually misleading; use Viridis or Coolwarm.
3. **Markerless line charts** with sparse data. Always add markers.
4. **Colour-only category coding.** Add hatches or marker shapes so the chart works in black-and-white.
5. **Cluttered grids** with solid black or thick gridlines competing with the data.
6. **Saturated coloured backgrounds.** Backgrounds are pure white.
7. **Indigo leaking** to non-argument elements. Indigo is rationed; one argument per chart.
8. **External legends when direct labels would do.** Direct labels are preferred where they don't crowd.
9. **Y-axis truncation that exaggerates the argument.** Charts must show the appropriate baseline (zero for proportional data, sensible domain for ratio data).
10. **Mobile illegibility.** Every chart must remain legible at Substack mobile width (~600 px). Cluttered multi-panel layouts that work on desktop but blur on phone are failures.

---

*This style guide is the C2C analogue to NeurIPS 2025 for statistical plots. Drop in by setting `export PAPERBANANA_STYLE_GUIDE_PREFIX=correlation_to_causation` before launching PaperBanana.*
