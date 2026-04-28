# Correlation to Causation Diagram Aesthetics Guide

## 0. How to read this guide

This guide tells the figure model **what genre to draw in**, not just what colours to use. The single most important sentence in this document is:

> *Correlation to Causation* figures are **Nature Reviews / NEJM data-visualisation hybrids with BioRender mechanistic schematics and Economist health-desk editorial register**, drawn in **flat single-colour silhouetted icons**, **vector-based BioRender biological glyphs with thick outlines and consistent stroke weight**, **Open Sans typography**, and a **strict three-colour palette (Primary Violet, Burnt Orange, Vivid Teal) on Structural Gray + Absolute White**. They are NOT line-art / NeurIPS-style monochrome schematics, NOT photoreal-illustration BioRender posters, NOT Excel/Seaborn defaults.

If a candidate looks like a thin grey-stroke line drawing on white, it is wrong. If it looks like a textbook explainer with flat silhouetted humans, vector-based DNA/protein/molecule glyphs, and confident saturated-but-restricted colour, with substantial 3 px lines and 4 px filled nodes, it is right.

**Core philosophy.** Scientific communication first; aesthetics second. Maximal clarity over stylistic flair. Minimal cognitive load. Consistent encoding across figures (same colour = same semantic role). Visual hierarchy is driven by position, weight, and contrast — not decoration.

---

## 1. The "Correlation to Causation" Look

### 1.1 The closest cousins (use these as visual reference)

The C2C house style is a **hybrid of three well-known genres**:

1. **Nature Reviews / NEJM data figures.** White background, frame-less plots, horizontal-only structural-grey gridlines, bold near-black title, clear axis labels, inline data labels. Chart titles centered at the top of the canvas; subtitle below in lighter grey adds interpretation.
2. **BioRender mechanistic schematic (flat-vector register).** Vector-based biological glyphs with **thick consistent outlines** and **smooth curves** — DNA double helix, RNA strand, nucleosome with modification dots, amorphous protein blob, small-molecule clusters, anatomical-mid-detail organs (heart, liver, lungs). NOT the illustrative photoreal BioRender poster register; we want the cleaner vector schematic register.
3. **The Economist health-desk chart (editorial register).** Bold near-black title, one-line medium-grey strap subtitle that carries the interpretation, two saturated accent colours doing semantic work, inline coloured annotations next to data, dashed mid-grey reference line, source footnote at the bottom in grey ending in a period.

Person-icons are **flat silhouetted humans**, single solid colour fill (the figure's primary accent), no outline, no facial detail, no gradient, anatomy abstracted to basic shapes (rounded torso, simple limbs). Whole-body or head-and-shoulders is figure-dependent — see iconography rules in §2.2. Never photoreal, never line-art outline, never emoji.

### 1.2 What this style is NOT

To make the genre unambiguous, the model should explicitly avoid:

- ❌ Thin grey-stroke line drawings on white with hollow interiors (the "AI-flatpack" / NeurIPS look)
- ❌ Outlined head-and-torso silhouettes for people (use solid filled silhouettes)
- ❌ Photoreal-illustration BioRender posters (soft drop shadows, pastel skin tones, internal organ collages with multi-tone fills) — too decorative; we want the cleaner flat-vector schematic register
- ❌ Multi-tone gradient fills on biological glyphs (use flat single-colour fills with thick consistent outlines)
- ❌ Geometric sans-serifs like Inter, IBM Plex, Poppins, Montserrat (use Open Sans, Lato as fallback)
- ❌ Pastel mints / pale corals / "Notion-illustration" decorative tints (use the saturated palette)
- ❌ Pure black (`#000000`) for fills or strokes (use near-black `#222222` for titles only, never for shapes)
- ❌ Periods at the end of titles, subtitles, axis labels, panel headers, or fragment captions
- ❌ 3D effects, drop shadows on chart elements, decorative textures, dense text blocks
- ❌ Inconsistent icon styles within a single figure (a flat silhouette next to a photoreal BioRender body is wrong — pick one register and hold it)

### 1.3 The visual argument rule

Every figure carries one visual argument. Of the saturated accent colours used in the figure, the **stronger** one carries the argument. The weaker one is the comparison or the supporting category. Everything else is structural-grey or white.

### 1.4 Cross-figure narrative arc

The C2C figure series is a **sequence**, not a set of stand-alone images. The canonical narrative pattern is:

1. **Empirical observation** (a chart showing the phenomenon)
2. **Mechanistic hypothesis** (a schematic showing the proposed pathway)
3. **Bias explanation** (a diagram showing why naïve interpretations mislead)
4. **Causal-inference solution** (a comparative diagram showing the corrected approach)

Subtitles carry interpretation across the arc, not repetition. A figure that breaks the same-colour-same-role rule across the sequence breaks the arc.

---

## 2. Detailed Style Options

### 2.1 Colour palette (C2C, three saturated accents + structural)

**The palette is closed.** Use these exact hexes. Do not substitute Wong-2011, Tableau defaults, matplotlib `tab:`, or seaborn presets.

| Token | Hex | Semantic role |
|---|---|---|
| **Primary Violet** | `#5A3BE8` | Argument-carrying / focal series / treated population / observed values. The figure's load-bearing element is violet. |
| **Burnt Orange** | `#E86A21` | Counter-series / harmful comparator / blocked path / mortality / risk / exponential trend. |
| **Vivid Teal** | `#00A884` | Causal-valid / clinical-trial markers / genetic-variant indicators / forest-plot effect estimates / "good" arm. |
| **Structural Gray** | `#888888` | Gridlines, tick labels, axis labels, neutral text annotations, dashed reference lines (null effect), confounder arrows, body strokes default. |
| **Absolute White** | `#FFFFFF` | Mandatory background. No texture, no gradient, no border. |
| Subtitle text grey (paired) | `#666666` | One-line strap subtitle beneath the title. |
| Near-black (titles only) | `#222222` | Title text. **Never used as a fill or stroke colour.** |
| Source/footnote grey | `#999999` | 9 pt source-line text at bottom. |

**Biological-detail tones (object render specs only — NOT figure-level accents).** When BioRender vector glyphs need internal differentiation, the following tones are permitted *inside the glyph* and do not count against the three-accent rule:

| Tone | Hex | Where used |
|---|---|---|
| Coral (DNA strand B / disease accent) | `#E63946` | DNA strand B paired with `#3B5BDB` strand A; disease-state highlight inside an organ glyph |
| Saturated blue (DNA strand A / male) | `#3B5BDB` | DNA strand A; male participant in person-icon counts |
| Pale-violet wash (cell interior) | `#EDE7F8` | Inside the BioRender cell membrane glyph |
| Pale-teal interior (molecule) | `#C8EAE0` | Inside the metabolite hexagon glyph |

These tones are part of canonical glyph render specs. They appear *only inside* a biological glyph, never as figure-level fills or strokes.

### 2.1.1 Colour-pairing rules (three pairings, no cross-mixing)

The C2C palette uses **three exclusive accent pairings**, each tied to a figure type. A figure picks ONE pairing and never crosses into another:

1. **Violet `#5A3BE8` + Burnt Orange `#E86A21`** — the *headline-chart pair*. Used for two-series bar charts, two-series line charts, and any "primary vs counter" comparison. Violet carries the argument; burnt-orange carries the counter / failure / risk.
2. **Vivid Teal `#00A884` + Structural Gray `#888888` dashed null** — the *causal-diagram pair*. Used for forest plots, Mendelian-randomisation diagrams, DAGs, and any figure asserting a causal claim. Teal carries the effect; structural-grey dashed lines mark null/no-effect (e.g. OR=1, HR=1). Confounder arrows in structural-grey solid.
3. **Violet `#5A3BE8` + Vivid Teal `#00A884`** — the *multi-omic / converging-streams pair*. Used when the argument is "violet = whole-person joint-state" and the supporting accent is "teal = a specific causal/clinical signal".

A fourth pairing — **Violet `#5A3BE8` + Coral `#E63946`** — is permitted *only for the masked-prediction comparative figure* (cf. Fig 4), because coral encodes "what the model is predicting" rather than "secondary biological data". This is the single figure-level exception.

**Cross-mixing is forbidden.** A figure that is fundamentally a "headline chart" never uses teal at figure level. A figure that is fundamentally a "causal diagram" never uses violet at figure level. Pick the pairing first, then build the figure.

**Saturation discipline.** Saturated colour is meaning, not decoration. If a shape carries a saturated fill, it is doing semantic work. Backgrounds, panels, axis chrome, and "everything else" are white or structural-grey. Never tint the canvas.

**Black is forbidden as a fill or stroke colour.** Pure `#000000` does not appear anywhere in a C2C figure. Titles use `#222222` (near-black). Body strokes default to structural-grey `#888888`.

### 2.1.2 Line-weight inventory (uniform standard)

C2C figures use a **uniform 3 px standard line weight** for trend lines and connecting paths. Thin lines suggest uncertainty and are forbidden. Specific weights:

| Line type | Weight | Colour | Where it appears |
|---|---|---|---|
| Trend / line-chart series | **3 px** | Violet (argument), burnt-orange (counter), teal (causal) | Headline plots, Eroom curves, mortality lines |
| Connecting / process paths in diagrams | **3 px** | Structural-grey or accent | Pipeline connectors, attribution lines |
| Causal-flow arrows | **3 px** with small filled triangular arrowhead | Teal (causal-valid) or structural-grey (plain process) | DAG, MR diagrams |
| Confounder / unobserved-path arrows | **3 px** | Structural-grey `#888888` | Causal-diagram side branches |
| Blocked-path overlay | **3 px** with bold thick red cross glyph centred on the shaft | Burnt-orange `#E86A21` shaft + coral cross | Excluded paths in DAGs |
| Reference / null line | **3 px**, dashed | Structural-grey `#888888` | OR=1, HR=1 verticals on forest plots |
| Forest-plot CI whiskers | **3 px** with **prominent vertical end caps** | Teal `#00A884` | Effect-estimate intervals |
| Forest-plot point estimate | Filled circle, **≥4 px radius** (≥8 px diameter) | Teal `#00A884` | Central effect |
| Headline trend area-fill underlay | ~10 % alpha shaded band | Series colour | Optional band beneath the 3 px trend line |
| Chart horizontal gridlines | **1 px** | Structural-grey `#888888` | Behind data, low z-order |
| Chart vertical gridlines | **Omitted** | n/a | Vertical grids are forbidden |
| Chart axis spines | Top, right, bottom **omitted** (frame-less); optional thin 1 px structural-grey left spine | Structural-grey `#888888` if shown | C2C charts are frame-less by default |
| BioRender vector-glyph outlines | **3 px** | Self-coloured / structural-grey | DNA helix, protein blob, molecule hex, organ glyphs |
| Token chip borders | 1 px | Structural-grey `#888888` | Token strips in mechanism diagrams |
| Annotation pointer arrows | **Forbidden** — annotations are inline coloured bold text, no leader lines | n/a | n/a |

**Data nodes** are solid filled circles with a radius of **at least 4 px** (i.e. ≥ 8 px diameter). Smaller dots read as uncertainty and are forbidden on argument-carrying data.

**Error bars** use **3 px stroke** with **prominent vertical end caps** of comparable thickness. Thin error bars are forbidden.

### 2.1.3 Frame-less chart rule

C2C charts (bar charts, line charts, forest plots, scatters) are rendered **frame-less**:

- **No top spine, no right spine, no bottom spine.** Optional thin 1 px structural-grey left spine for scale orientation; usually absent.
- **Horizontal gridlines only**, 1 px structural-grey `#888888`, low z-order.
- **No vertical gridlines.** Ever.
- **No tick marks.** Numeric tick labels float beside the gridline.
- **Data floats on white**: the visual impression is "numbers, bars, and 3 px lines in whitespace", not "data inside a box".

### 2.2 Iconography genre rules (cross-figure)

This section sets the *genre* of iconography across the C2C series. Per-object render specs (organelle counts, helix turns, exact hex values for individual objects, scale ratios between paired glyphs) **do not live here** — they live in each figure's Method Content at the point of use, because they often vary by what the figure is arguing.

**Genre rules that apply across every figure in the series:**

1. **Human forms are flat silhouetted icons.** Single solid-colour fill in the figure's primary accent (violet for argument-carrying; structural-grey for receding). No outline, no facial features, no gradient, no internal organ collage. Anatomy is abstracted to basic shapes (rounded torso, simple limbs, simple head). Whole-body or head-and-shoulders is figure-dependent — Fig 1 Stage 4, Fig 3 Module 3, Fig 4 Column 3, and Fig 5 central anchor use **whole-body silhouettes** because the argument is "the whole person"; population-count person-icons elsewhere use **head-and-shoulders silhouettes**.
2. **Biological molecules are vector-based with thick consistent outlines and smooth curves.** Outlines at 3 px, in either the molecule's natural BioRender colour or structural-grey. Internal fills are flat single-colour or pale-teal/pale-violet wash. **No multi-tone gradient fills.** **No photoreal soft-shadow rendering.**
3. **The standardised C2C icon dictionary** (use these consistently across the series):
   - **Genome / DNA:** double-helix glyph — two smooth-curve rounded ribbons (3 px stroke each) in saturated blue `#3B5BDB` + coral `#E63946`, ~3 turns visible, structural-grey rung hatches
   - **Epigenetics (when shown):** nucleosome — pale-violet sphere with 3–5 modification dots in coral around its surface
   - **Transcriptomics / RNA:** single RNA strand — one smooth-curve ribbon (3 px stroke) in coral, single-stranded
   - **Proteomics:** amorphous protein blob — cloud-like ribbon-helix outline (3 px stroke) in violet, with smooth-curve interior contour suggestion (single internal stroke at 1 px)
   - **Metabolomics:** small-molecule cluster — one or more hexagons (3 px teal outline, pale-teal `#C8EAE0` interior) with explicit bond lines through the hexagon edges and at least one explicit side-chain stub (`–OH`, `–NH₂`, etc.)
   - **Cell biology:** rounded oval cell membrane (3 px structural-grey or saturated-blue outline, pale-violet interior) with central coral nucleus, ≥3 mitochondrion ovals, ≥1 ER strand, ≥1 Golgi stack, ≥4 cytoplasmic ribosome dots — never a hollow oval with one nucleus
   - **Disease / multi-omic person:** flat human silhouette in primary accent
   - **Tissue (H&E):** if present, a square showing eosin-pink + haematoxylin-purple stained tissue *or omit entirely* — grey stipple substitutes are forbidden
   - **Anatomical organs (heart, liver, lungs):** vector outlines (3 px structural-grey or organ-natural-colour stroke) with single-tone flat fills; visible anatomical features (heart chambers + aorta arch; lobed liver; lung lobes)
4. **Status indicators.** Blocked pathways use a **thick coral cross** (3 px stroke, two crossing diagonals) overlaid on the path. Active pathways use **straight directional arrows** (3 px stroke) with small filled triangular arrowheads, minimal curvature.
5. **No emoji, no flags, no country icons, no logos** anywhere in any figure.
6. **Person-icons that carry the figure's argument are paired with a four-modality spoke halo** (DNA, protein, molecule, EHR) in clockwise order. Two-spoke or three-spoke halos are wrong — the four-modality halo is the visual signature of "multi-omic human" across the series.

Everything beyond these genre rules — exact hex values, glyph dimensions, organelle counts, side-chain stub identity — is figure-specific and lives in the relevant Method Content.

### 2.3 Typography

**Font family: Open Sans (preferred) or Lato (fallback).** Both are humanist sans-serifs with rounded terminals and low contrast. Never use geometric sans (Inter, IBM Plex, Poppins, Montserrat). Never use serifs. Never mix families within or across figures.

| Element | Font | Weight | Size | Colour | Alignment | Punctuation |
|---|---|---|---|---|---|---|
| **Diagram title** (top of figure) | Open Sans | Bold | ~22 pt | Near-black `#222222` | Left | **No terminal period** |
| **Chart title** (top of plot canvas) | Open Sans | Bold | 16–20 pt | Near-black `#222222` | Centred | **No terminal period** |
| **Subtitle / strap** (one line under title) | Open Sans | Regular | ~13 pt | Subtitle grey `#666666` | Matches title alignment | **No terminal period** |
| **Panel / column headers** | Open Sans | Bold | ~16 pt | Near-black `#222222` | Centred or left | **No terminal period** |
| **Axis labels** | Open Sans | Regular | 12 pt | Structural-grey `#888888` | Central along axis | **No terminal period** |
| **Tick labels / annotations** | Open Sans | Regular | 10 pt | Structural-grey `#888888` | Adjacent to tick | **No terminal period** |
| **Numeric chips / scale callouts** | Open Sans | Bold | ~13 pt | Series colour (violet / teal / etc.) | Inside chip | **No terminal period** |
| **Inline coloured annotations** ("doubled", "60% fail") | Open Sans | Bold | ~12 pt | Matching series colour | Adjacent to data | **No terminal period** |
| **Italic gene / model names** | Open Sans | Italic | ~10 pt | Body-text grey `#3D4452` | Inline | **No terminal period** |
| **Footnote / source line** | Open Sans | Italic-feel Regular | 9 pt | Source-line grey `#999999` | Bottom centre or bottom left | **Period at end (full sentence)** |

**The terminal-period rule, restated.** Titles, subtitles, panel headers, axis labels, chip captions, inline annotations, and any other fragment label all have **NO period at the end**. The only place a period appears in the figure is at the end of a complete-sentence footnote or source-citation line at the bottom of the figure.

**Letter-case rule.** Titles and panel headers use sentence case ("Why drugs fail by phase"), not Title Case ("Why Drugs Fail By Phase"). "What it enables" capability lines on argument-carrying stages may use Title Case for emphasis. Acronyms keep their casing (DNA, PBPK, FM, EHR).

### 2.4 Composition and chrome

- **Canvas:** pure white `#FFFFFF`. No border around the whole figure. No background tint.
- **Margins:** generous outer padding, ~5–8% of the canvas width. Internal spacing consistent and grid-aligned (implicit grid; no visible grid lines).
- **Aspect ratio:** plots ~16:9 or 3:2; mechanistic diagrams vertical stack (portrait) or horizontal scale-axis (landscape) per figure-specific need.
- **Spines:** if the figure contains a chart panel, **top, right, and bottom spines are removed**. Optional 1 px structural-grey left spine.
- **Gridlines:** **horizontal only**, 1 px structural-grey `#888888`, behind the data. **No vertical gridlines** anywhere.
- **Reference lines:** dashed structural-grey `#888888`, 3 px. Never solid. Never coloured.
- **Whitespace:** generous. The reader's eye should rest, not scan a wall of text.
- **Annotations:** inline next to the data they describe, in the matching series colour, bold weight. **No leader lines.** **No boxed callouts.**
- **Legends:** prefer direct labels next to lines/bars/icons. If a legend is unavoidable, it sits below the figure, centred, with small filled square swatches.
- **Footnote / source line:** if used, sits at the bottom-left or bottom-centre in source-grey `#999999` italic-feel Regular 9 pt, ending in a period.

### 2.5 Density budget (the anti-text rule)

Figures must not be padded with prose, nor stripped down to a single icon and a chip.

**Per-panel ceiling (max 7 visual elements):**
1. **One** illustrative icon (BioRender vector glyph or flat silhouette; for argument-carrying panels, the icon may include up to one supporting glyph — counted as a single element)
2. **One** short header (≤5 words, fragment, no period)
3. **One** short descriptor strap (≤10 words, fragment, no period) — OPTIONAL but encouraged on argument-carrying panels
4. **One** numeric chip (≤8 characters: a number + a one-word unit) — OPTIONAL
5. **One** model-name chip strip — a single horizontal row of ≤3 small italic chips — OPTIONAL
6. **One** inline coloured annotation (≤4 words) — OPTIONAL
7. **One** small supporting depiction (e.g. a candidate-funnel triangle, mini bar chart) — OPTIONAL

Six elements is the typical landing point for an argument-carrying panel. Three or four elements is right for a passive panel.

### 2.5a The `>` prefix rule for "more than" numbers

Numeric chips that mean *"at least this many"* or *"more than this many"* take an explicit `>` prefix: `>200M proteins`, `>100M cells`, `>1.5M slides`, `>500k people`. Numeric chips that mean an exact value or order of magnitude take no prefix: `~250 metabolites`, `30 yr`, `$$$`. The `>` prefix is bold, in the chip's accent colour, and immediately precedes the digit with no space.

**Forbidden inside the figure:**
- ❌ Multi-sentence descriptions inside a panel
- ❌ Bullet-list paragraphs inside a panel
- ❌ Citations or DOI strings
- ❌ Methodology disclaimers
- ❌ Legends repeating colour semantics already shown by direct labels
- ❌ Long model-roster lists of more than 3 names

**Allowed and encouraged:**
- ✅ A bare number with a one-word unit
- ✅ A single fragment header
- ✅ A single descriptor strap
- ✅ A coloured annotation pinned next to a data point

---

## 3. Common pitfalls (how to look "off-brand")

1. **Drawing the figure as line-art.** Thin grey strokes with white interiors is the AI-flatpack default and the strongest tell that the figure is off-brand. C2C uses 3 px confident strokes.
2. **Outlined hollow person-icons or stick figures.** Person-icons are flat silhouettes filled with the primary accent colour. A line-drawn outline is wrong.
3. **Multi-tone gradient fills on biological glyphs.** Use flat single-colour fills with thick consistent outlines.
4. **Photoreal-illustration BioRender posters.** Soft drop shadows, pastel skin tones, internal organ collages — too decorative. Use the cleaner flat-vector schematic register.
5. **Geometric sans-serifs.** Inter, IBM Plex, Poppins, Montserrat — all wrong. Open Sans (or Lato) only.
6. **Periods at the end of titles, subtitles, panel headers, axis labels, fragment captions.** The terminal-period rule must hold.
7. **Pure black** for any fill or stroke.
8. **More than three saturated accent colours in a single figure.** Two or three only, drawn from the {Violet, Burnt Orange, Vivid Teal} set, in one of the three permitted pairings (or the masked-prediction exception).
9. **Tool / model name lists baked into the figure.** Names go in the post body.
10. **Wall-of-text panels** with multiple sentences each.
11. **Vertical gridlines.** Horizontal only.
12. **Top, right, and bottom spines on charts.** Remove all three.
13. **Boxed callouts with leader lines.** Annotations are inline coloured bold text, no box, no leader.
14. **Pastel mint / pale coral / "Notion illustration" tints.** The palette is saturated.
15. **Drop shadows on chart elements** (bars, lines, dots, text). Drop shadows are forbidden across the system in this revision — flat fills only.
16. **3D effects, gradients, presentation-template shapes.** Forbidden.
17. **"Figure N:" baked into the image.** The post supplies the caption externally.
18. **Hallucinated model names.** If the input does not name the model, do not invent one.
19. **Mobile illegibility.** Every figure must read at ~600 px Substack mobile width. If text would shrink below ~9 pt at that width, cut text — do not shrink text.
20. **Inconsistent semantic colouring across the figure series.** Same colour = same role. Violet = argument/observed/treated; burnt-orange = counter/comparator/risk; teal = causal-valid/clinical-marker.

---

## 4. Domain-specific styles

### 4.1 Scale / hierarchy diagram
*(e.g. biological scales of foundation models, layers of evidence)*

- Horizontal scale-axis, equally weighted stage panels left-to-right.
- Each stage panel obeys the 7-element density ceiling.
- Single solid arrowhead at the right end of the axis. **No connector arrows between stages** — the axis is hierarchy, not pipeline.
- The argument-carrying stage uses Primary Violet for its icon fill and chip; non-argument stages use structural-grey for their icon fill (or BioRender-natural colour for biological glyphs, e.g. saturated-blue + coral DNA).
- Empty / aspirational stage: NO dashed indigo border. Stage 4 in particular sits on the same open canvas as the others; the argument is carried by violet icon fill + violet numeric chip + violet capability line + four-modality halo, never by an enclosing rectangle.

### 4.2 Pipeline / lifecycle diagram
*(e.g. drug-development phases, training loops)*

- Horizontal pipeline preferred; vertical-stack permitted. Pick one per figure.
- Phase blocks are interlocking right-pointing chevrons sharing a baseline; white fill, 3 px structural-grey border, and an internal coloured stripe matching the phase's accent if needed.
- Forward arrows between phases are 3 px structural-grey with a small filled arrowhead. Feedback / aspirational arrows are 3 px dashed violet.
- Per-phase numeric chips use the phase's accent colour. The argument-carrying phase uses violet.
- Failure / attrition is encoded with burnt-orange proportional bars, not text.

### 4.3 Comparative multi-panel diagram
*(e.g. three architectures side-by-side)*

- Equal-width columns separated by ~32 px of whitespace. **No vertical dividers.**
- The argument-carrying column gets a 3 px violet top-edge accent and a violet header. Non-argument columns have a structural-grey header.
- A "rail of architectural sameness" — a 1 px structural-grey horizontal line — can run behind shared components across columns to signal "this is the same across columns".
- Per-column density budget identical to a stage panel.

### 4.4 Converging-streams / fan-in diagram
*(e.g. multi-modal data inputs feeding a model)*

- Parallel input streams enter from above a central anchoring element (whole-body flat silhouette in violet, or a labelled embedding chip).
- Each stream is one BioRender vector glyph + fragment label (≤2 words) + numeric chip — three elements max per stream.
- The anchoring element is rendered in violet. Streams converge into one joint rail beneath the anchor.
- The exit arrow from the joint rail is 3 px solid violet with a filled arrowhead, terminating in a violet-filled embedding chip.

### 4.5 Statistical chart embedded in an explanatory diagram
*(e.g. a bar chart, line chart, or attrition funnel that lives inside a larger figure)*

- Apply the C2C plot style guide rules to the chart sub-region.
- Bars: solid fills, no outline. Argument bar uses violet (or teal for positive framing). Comparison bar uses burnt-orange.
- Lines: 3 px stroke, ≥4 px filled circular markers at every data point.
- Reference line: 3 px dashed structural-grey, never solid, never coloured.
- Inline coloured annotations next to the argument data point, no leader line.

### 4.6 RCT vs MR side-by-side comparison
*(e.g. parallel causal-design diagrams)*

- Side-by-side symmetric panels with identical structure mirrored.
- Colour-coded groups (violet vs burnt-orange) for treated/control or genetic-allele groups.
- Same shape vocabulary reused across both panels for visual equivalence.
- Large bold panel headers; minimal explanatory text inside the diagram.

### 4.7 Multi-omic biological cascade
*(e.g. genomics → epigenomics → transcriptomics → proteomics → metabolomics → disease)*

- Strict vertical pipeline with equal vertical gaps and arrow-centred alignment.
- Mid-level visual abstraction: recognisable biology, not overly detailed.
- Mostly structural-grey body chrome with violet/teal accents on the argument-carrying step.
- Coral only for epigenetic modifications on the nucleosome.

---

## 5. Drop-in usage

This guide is the C2C diagram analogue to `neurips2025_diagram_style_guide.md`. Activate by:

```bash
export PAPERBANANA_STYLE_GUIDE_PREFIX=correlation_to_causation
```

before launching PaperBanana. The Stylist agent will read `correlation_to_causation_diagram_style_guide.md`; the NeurIPS files remain available for any non-C2C work.

---

## 6. Authorial note for the model

When in doubt between two visual interpretations, ask: *"Would this fit naturally inside a Nature Reviews article, an NEJM perspective piece, or an Economist health-desk explainer? Are the biological glyphs flat-vector BioRender schematic, with thick consistent 3 px outlines and single solid-colour fills?"* If yes, the figure is on-brand. If it looks like thin grey lines on white, photoreal soft-shadow illustration, or Excel/Seaborn defaults, it is off-brand and must be redrawn.

---

## 7. Forward-looking note (speculative — not binding)

The user has flagged two plausible future evolutions of this system: (a) translating these parameters into a programmatic JSON design-token system feeding a headless graphics library (e.g. Vega-Lite, Plotly low-level, custom matplotlib theme), and (b) an inverted dark-mode palette for digital review portals. Both are speculative roadmap items, not part of the binding spec. Treat them as candidate next steps, not as current rules.
