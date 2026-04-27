### 1. The "Correlation to Causation" Look

The prevailing aesthetic is **"Editorial Health-Desk Schematic."** Imagine a diagram from a Nature Reviews editorial, an NEJM central illustration, and an Our World in Data infographic, sitting side-by-side. Clean, academic, minimalist, pictogram-driven. The vibe balances **clinical precision** (the figure says exactly what it means) with **lay accessibility** (a non-specialist Substack reader can parse it on a phone).

Every figure carries a single visual argument. Saturation is reserved for the element that argument touches. Everything else recedes into neutral greys. The reader should be able to identify the load-bearing claim of the figure within two seconds, even at thumbnail resolution.

---

### 2. Detailed Style Options

#### **A. Color Palette (Wong-2011 colour-blind safe)**
*Design Philosophy: Saturation is meaning, not decoration. The colour set is fixed across every figure in the series so semantics never shift.*

**Functional palette (the only colours permitted):**
| Token | Hex | Semantic role |
|---|---|---|
| Primary indigo | `#4f46e5` | **THE ARGUMENT.** The single element the figure is drawing attention to. Indigo appears nowhere else. |
| Accent green | `#009E73` | **ADVANCEMENT / POSITIVE.** Progression markers, "go" signals, upward bars in result charts. |
| Accent orange | `#D55E00` | **RISK / REJECTION / WARNING.** Failure segments, severity markers, rejection × markers. |
| Accent purple | `#CC79A7` | **AUXILIARY CATEGORY.** A second non-argument category when one is genuinely needed. |
| Neutral light grey | `#bdbdbd` | **RECEDING / NON-FOCUS / MASKED.** Built / non-argument elements, masked tokens, secondary chrome. |
| Neutral mid grey | `#758091` | **STRUCTURE / AXIS / SECONDARY TYPOGRAPHY.** Axes, gridlines, body type on non-argument elements, structural rails. |
| Body text | `#1f2937` | All plain-English annotation text, for accessibility contrast. |
| Background | `#ffffff` | Pure white. No vignette, no paper texture, no gradient. |

**Saturation rule.** If a colour appears in the figure, it is carrying meaning. Indigo means *this is the argument*. Orange means *risk or rejection*. Green means *advancement*. Purple means *auxiliary category*. Grey means *receding / structural*. The semantics never change between figures, so a series of figures using this palette reads as one coherent set.

**Palette scope.** No other colours are permitted. No PowerPoint blue/orange presets. No amber. No cyan. No secondary red. No yellow. If a category needs distinguishing beyond the seven tokens above, use opacity (e.g. orange at 100% vs orange at 40%) rather than introducing new hues.

#### **B. Shapes & Containers**
*Design Philosophy: "Editorial geometry." Every shape carries a job; every job has a shape.*

**Core components**
- **Rounded rectangles** (corner radius 8–10 px) for panels, cards, modules, stages, columns, architecture boxes, token chips, embedding chips. This is the dominant shape.
- **Token chips:** small rounded rectangles, ~36–48 px wide × 18–22 px tall, 1 px outline, white fill, short text label inside.
- **Chevrons** (interlocking right-pointing arrows) reserved for pipeline-stage progressions only.
- **Cylinders / databases:** not used in this series.

**Borders**
- **Solid borders** = built / existing components.
- **Dashed borders** = aspirational / unbuilt / feedback / masked, rendered in indigo when argument-relevant or grey when receding.
- **Stroke weight:** 1–1.5 px throughout. No heavy black outlines.
- **No double borders.** No outlined text except indigo bold callouts.

**Grouping & hierarchy**
- **Solid background fills** are not used. Backgrounds are pure white. Containers rely on outlines, corner radius, and internal whitespace, not on fill colour.
- **Structural rails** (thin mid-grey horizontal lines behind a row of containers) are used to signal "these belong together" without enclosing them.

#### **C. Lines & Arrows**
*Design Philosophy: Line style dictates flow type, not decoration.*

**Connector styles**
- **Orthogonal / right-angle connectors** for structural diagrams (pipelines, architectures, scale axes).
- **Curved connectors** for system-level data flow and feedback loops.
- **Straight connectors** for attribution lines (e.g. modality streams attributing to a person silhouette).

**Line semantics**
- **Solid mid-grey lines** = forward / built / existing flow.
- **Dashed indigo lines** = aspirational / auxiliary / feedback flow.
- **Arrowheads** appear only where direction matters (pipeline advancement, training loops, scale axes, exit-to-transformer arrows). Hierarchies and stacks have no arrowheads.
- **Attention curves inside transformer boxes:** thin 0.75 px mid-grey lines connecting tokens to each other, 3–4 per box.

#### **D. Typography & Icons**
*Design Philosophy: One font family throughout. Type weight signals importance.*

**Typography**
- **Font family:** Open Sans (or nearest humanist sans-serif: Inter, Source Sans Pro, Lato). No serif fonts. No font mixing within or across figures.
- **Headline elements** (stage titles, phase headers, module titles, column titles, stream titles): Open Sans Bold, ~18–22 pt.
- **Plain-English descriptions and pipeline-stage labels:** Open Sans Regular, ~14–16 pt.
- **Italic annotations** (flagship model names, gene names, attention-curve labels): Open Sans Italic, ~12–14 pt.
- **Small labels and glosses** (axis labels, annotations, loop-loss annotations): Open Sans Regular, ~11–12 pt.
- **Token chip text:** Open Sans Regular, ~9–10 pt.
- **Indigo callouts** (the argument-carrying line in each figure): Open Sans Bold, indigo `#4f46e5`.

**Iconography**
- **Flat line art**, single stroke weight matched to body-text weight, NEJM clinical-pictogram tradition.
- **Modality glyphs**, used consistently across the series:
  - DNA double-helix stub for *Genome*.
  - Protein ribbon for *Proteome*.
  - Molecule hex (benzene-ring skeleton) for *Metabolome*.
  - EHR-waveform / chart-line for *Longitudinal clinical record*.
  - Single eukaryotic cell outline (with one nucleus disk) for *Single cell*.
  - Human silhouette (head and torso, line art) for *Whole human*.
- **No cartoons.** No anthropomorphic AI mascots, no robot characters, no faces or expressions on silhouettes.
- **No emoji** inside the figure.
- **No photoreal imagery, no logos, no flags, no country icons.** Plain text labels only.
- Icons sit at the top ~12–15% of stage/panel/column where applicable.

---

### 3. Common Pitfalls (How to look "Amateur")

1. **PowerPoint defaults.** Standard blue/orange presets, drop shadows, bevels, gradients, 3D isometric depth, neumorphism.
2. **Saturated coloured backgrounds** on non-focus elements. The argument-carrying indigo must stay exclusive to the argument.
3. **Indigo leaking** to non-argument elements. Indigo is rationed; if it appears, it carries the argument.
4. **Mixing serif and sans-serif fonts.** One family throughout.
5. **Emoji inside the figure.** Icons are line-art glyphs, not emoji.
6. **Cartoon robots, anthropomorphic AI mascots, humanised-AI characters,** faces or expressions on silhouettes.
7. **Logos, flags, country icons.** Plain text labels only.
8. **Heavy black outlines** thicker than 1.5 px around the whole figure or individual panels.
9. **"Figure N:" baked into the image.** The post supplies its own caption externally.
10. **Adding colours outside the palette.** Introducing a second red, amber, yellow, or cyan destroys the series' colour semantics.
11. **Using the same line style for forward flow and feedback flow.** Dashed indigo means feedback or aspirational; do not also use dashed for forward flow.
12. **Mobile illegibility.** Every figure must remain legible at Substack mobile width (~600 px). Cluttered four-column layouts that work on desktop but blur on phone are failures.

---

### 4. Domain-Specific Styles

This style guide is tuned for **biomedical and life-sciences explainer diagrams** intended for a non-specialist Substack audience.

**If the figure is a SCALE / HIERARCHY diagram (e.g. biological scales, layers of evidence):**
- Use a horizontal scale-axis layout with equally-weighted stage panels left-to-right.
- A single solid arrowhead at the right end of the axis indicates increasing scale.
- No connector arrows between stages — the axis is hierarchy, not pipeline.

**If the figure is a PIPELINE / LIFECYCLE diagram (e.g. drug-development stages, training loops):**
- Use chevron-shaped pipeline stages with right-pointing flow.
- Forward arrows are solid mid-grey; feedback loops are dashed indigo.
- Phase boundaries use thin mid-grey vertical dividers, not heavy walls.

**If the figure is a COMPARATIVE / MULTI-PANEL diagram (e.g. three architectures side-by-side):**
- Use equal-width columns with thin mid-grey vertical dividers.
- A horizontal "rail of sameness" can run behind shared components to signal "this is the same across columns."
- The argument-carrying column gets indigo top-edge accent and indigo column title; the others stay mid-grey.

**If the figure is a CONVERGING-STREAMS / FAN-IN diagram (e.g. multi-modal data inputs):**
- Use parallel input streams entering from above a central anchoring element (silhouette, hub, embedding chip).
- Each stream contributes its native data shape, then narrows into a tokenisation row, then converges into a single joint rail.
- The anchoring element is rendered in indigo; streams are rendered in mid-grey.

**If the figure is a STATISTICAL CHART embedded in an explanatory diagram:**
- Bars, lines, dots use the seven-token palette only.
- Bars use solid colour fills with no outline; gridlines are thin mid-grey dashed lines.
- Line charts use markers at every data point, not just a stroke.
- Heatmap cells are square, with values written inside in body-text colour.

---

*This style guide is the C2C analogue to NeurIPS 2025. Drop in by setting `export PAPERBANANA_STYLE_GUIDE_PREFIX=correlation_to_causation` before launching PaperBanana.*
