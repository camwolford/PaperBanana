# Correlation to Causation Diagram Aesthetics Guide

## 0. How to read this guide

This guide tells the figure model **what genre to draw in**, not just what colours to use. The single most important sentence in this document is:

> *Correlation to Causation* figures are **BioRender mechanism diagrams meets Economist health-desk charts**, drawn in **flat illustrative biology assets** with **Font Awesome solid people-glyphs**, **Lato/Open Sans** typography, and **two saturated accent colours per figure**. They are NOT line-art / NEJM-pictogram / NeurIPS-style monochrome schematics.

If a candidate looks like a thin grey-stroke line drawing on white, it is wrong. If it looks like a textbook diagram with shaded blobs, illustrative DNA, pink stained tissue, blue/green/orange filled person-icons, and confident two-colour bars, it is right.

---

## 1. The "Correlation to Causation" Look

### 1.1 The closest cousins (use these as visual reference)

The C2C house style is a **hybrid of two well-known genres**, both of which the AI model already knows well. Reproduce the hybrid:

1. **The Economist health-desk chart.** White background, no top/right spines, horizontal-only pale grey gridlines, bold near-black title, one-line medium-grey strap subtitle, two saturated accent colours, inline coloured annotations, dashed mid-grey reference line, source footnote at the bottom in grey.
2. **A BioRender mechanism diagram.** Flat illustrative biology assets (DNA helix as navy + red strands; brain as soft pink with red vasculature; protein as pale-blue cloud-like blob with internal shading; cell as outlined oval with multi-colour organelles; tissue as eosin-pink + haematoxylin-purple stained square). Soft drop shadows and internal shading. Multi-tone fills, never monochrome line art.

Person-icons are the **Font Awesome solid `user` silhouette** (head and shoulders), filled with one of the four palette colours, no outline, no facial detail, no gradient. Never photoreal, never line-art outline, never emoji.

### 1.2 What this style is NOT

To make the genre unambiguous, the model should explicitly avoid:

- ❌ Thin grey-stroke line drawings on white with hollow interiors (the "AI-flatpack" / NeurIPS look)
- ❌ Outlined head-and-torso silhouettes for people (use FA solid filled glyphs instead)
- ❌ Monochrome / grey stippled tissue squares (use real H&E pink+purple instead)
- ❌ Geometric sans-serifs like Inter, IBM Plex, Poppins, Montserrat (use Lato or Open Sans instead)
- ❌ Pastel mints / pale corals / "Notion-illustration" decorative tints (use saturated indigo, teal-green, rust-orange, coral-red instead)
- ❌ Pure black (`#000000`) for fills or strokes (use near-black `#1A1A1A` for titles only, never for shapes)
- ❌ Periods at the end of titles, subtitles, axis labels, panel headers, or fragment captions

### 1.3 The visual argument rule

Every figure carries one visual argument. Of the two saturated accent colours used in the figure, the **stronger** one carries the argument. The weaker one is the comparison or the supporting category. Everything else is grey or white.

---

## 2. Detailed Style Options

### 2.1 Colour palette (C2C native, not Wong-2011)

**The palette is the publication's, not Anthropic-flavoured.** Use these exact hexes. Do not substitute.

| Token | Hex | Semantic role |
|---|---|---|
| **Indigo** (primary) | `#4B3FE4` | Argument-carrying colour. The figure's load-bearing element is indigo. |
| **Teal-green** (primary) | `#1FA579` | Positive / advancement / the "good" comparison. Co-primary with indigo for two-arm comparisons. |
| **Rust-orange** (secondary) | `#C9531C` | Risk / failure / mortality / the "bad" comparison. |
| **Coral-red** (secondary) | `#D94B4B` | Negative biology (disease state, "develops X", failure mode). Often used in person-icons that represent the negative arm. |
| **Near-black** (text only) | `#1A1A1A` | Titles and primary type. Never used as a fill or a stroke colour. |
| **Mid-grey** (structural) | `#6E7480` | Subtitles, axis labels, footnote source lines, reference lines, structural rails. |
| **Pale grey** (gridline) | `#E5E7EB` | Horizontal gridlines only. Never used for type or fills. |
| **Background** | `#FFFFFF` | Pure white, no texture, no gradient, no border. |

**Two-accent rule (hard).** Each figure uses **exactly two saturated accent colours**, drawn from {indigo, teal-green, rust-orange, coral-red}. Never three. Never four. The most common pairings:
- *Indigo + rust-orange* (argument vs comparison; treatment vs control)
- *Teal-green + coral-red* (good outcome vs bad outcome)
- *Indigo + coral-red* (argument vs negative biology)
- *Indigo + teal-green* (argument across two positive arms; multi-class persons)

**Saturation discipline.** Saturated colour is meaning, not decoration. If a shape carries a saturated fill, it is doing semantic work. Backgrounds, panels, axis chrome, and "everything else" are white or pale-grey. Never tint the canvas.

**Black is forbidden as a fill or stroke colour.** Pure `#000000` does not appear anywhere in a C2C figure. Titles use `#1A1A1A` (near-black). Strokes default to mid-grey `#6E7480`. Reference lines are dashed mid-grey.

### 2.2 Iconography (BioRender illustrative + FA solid people)

**Biological objects are BioRender-style illustrative assets, not line-art.** Each object below has a fixed visual treatment. Use these exact treatments wherever the object appears across the series:

| Object | Treatment |
|---|---|
| **DNA / genome** | Double helix with two distinct strand colours (navy `#2B3990` + coral `#D94B4B`). Soft drop shadow. Not a line-drawn helix stub. |
| **Protein / proteome** | Cloud-like blob with internal pale-blue shading (`#A8C7E8` highlight, `#5B7FB8` shadow). Soft drop shadow. Not a flat ribbon. |
| **Metabolite / molecule** | Hexagon with two-tone fill (teal-green outline `#1FA579`, pale teal interior `#C8EAE0`) and visible bond lines. Not a hollow benzene ring. |
| **Cell** | Oval cell membrane in pale violet-grey, internal nucleus in coral-red `#D94B4B`, 2–3 organelle dots in mid-grey. Multi-tone, not monochrome. |
| **Tissue / H&E** | A square of stained tissue rendered in **eosin-pink (`#E8B4C8`) + haematoxylin-purple (`#6B4A8B`)** with visible nuclear punctate dots. NEVER a grey stipple. NEVER scattered confetti dots on white. Real H&E colour palette. |
| **Organ (brain, heart, liver)** | BioRender flat illustrative — soft pink (`#E8A5B5`) for parenchyma, deeper red (`#C9384B`) for vasculature, faint shading for depth. Not an outline-only silhouette. |
| **Person-icon** | **Font Awesome solid `user` silhouette** (head + rounded shoulders, filled). Single flat fill colour from the palette: indigo, teal-green, coral-red, or rust-orange. No outline. No facial features. No gradient. No drop shadow. |
| **Doctor / clinician** | FA solid `user-md` glyph (with stethoscope), filled in mid-grey or indigo. Not photoreal. |
| **EHR / clinical record** | A small rounded-rectangle "record card" with three thin horizontal data lines inside, top stripe filled in indigo or coral-red. Or a heart-rate waveform glyph in indigo. |

**No emoji. No flags. No country icons. No logos.** Plain text labels only where icons cannot do the job.

**No outlined-head-and-torso "stick figure" silhouettes.** People are always FA solid `user` glyphs with a colour fill. If the figure needs a person, it is a coloured solid silhouette, not a hollow outline.

**No grey stipple tissue.** If the figure shows tissue, it is stained pink+purple. If the model cannot render proper H&E, omit the tissue square entirely and use a pink-shaded organ glyph instead.

### 2.3 Typography

**Font family: Lato (preferred) or Open Sans (fallback).** Both are humanist sans-serifs with rounded terminals and low contrast. Never use geometric sans (Inter, IBM Plex, Poppins, Montserrat). Never use serifs. Never mix families within or across figures.

| Element | Font | Weight | Size (relative) | Colour | Punctuation |
|---|---|---|---|---|---|
| **Figure title** (top of figure) | Lato | Bold | ~22 pt | Near-black `#1A1A1A` | **No terminal period** |
| **Subtitle / strap** (one line under title) | Lato | Regular | ~14 pt | Mid-grey `#6E7480` | **No terminal period** |
| **Panel / column headers** | Lato | Bold | ~16 pt | Near-black `#1A1A1A` | **No terminal period** |
| **Axis labels** | Lato | Regular | ~12 pt | Mid-grey `#6E7480` | **No terminal period** |
| **Numeric chips / scale callouts** | Lato | Bold | ~14 pt | Series colour (indigo / teal / etc.) | **No terminal period** |
| **Inline coloured annotations** ("doubled", "60% fail") | Lato | Bold | ~13 pt | Matching series colour | **No terminal period** |
| **Italic gene / model names** | Lato | Italic | ~12 pt | Body-text grey `#3D4452` | **No terminal period** |
| **Footnote / source line** (bottom of figure) | Lato | Italic-feel Regular | ~10 pt | Mid-grey `#6E7480` | **Period at end (full sentence)** |

**The terminal-period rule, restated.** Titles, subtitles, panel headers, axis labels, chip captions, inline annotations, and any other fragment label all have **NO period at the end**. The only place a period appears in the figure is at the end of a complete-sentence footnote or source-citation line at the bottom of the figure.

**Letter-case rule.** Titles and panel headers use sentence case ("Why drugs fail by phase"), not Title Case ("Why Drugs Fail By Phase"). Acronyms keep their casing (DNA, PBPK, FM, EHR).

### 2.4 Composition and chrome

- **Canvas:** pure white `#FFFFFF`. No border around the whole figure. No background tint.
- **Spines:** if the figure contains a chart panel, **top and right spines are removed**. Left and bottom spines remain as thin mid-grey lines.
- **Gridlines:** **horizontal only**, pale grey `#E5E7EB`, behind the data. **No vertical gridlines** anywhere.
- **Reference lines:** dashed mid-grey `#6E7480`. Never solid. Never coloured.
- **Whitespace:** generous. The reader's eye should rest, not scan a wall of text.
- **Annotations:** inline next to the data they describe, in the matching series colour, bold weight. **No leader lines.** **No boxed callouts.**
- **Legends:** prefer direct labels next to lines/bars/icons. If a legend is unavoidable, it sits below the figure, centred, with small filled square swatches.
- **Footnote / source line:** if used, sits at the bottom-left of the figure in mid-grey italic-feel Regular ~10 pt, ending in a period.

### 2.5 Density budget (the anti-text rule)

Figures in this series have repeatedly been too text-heavy. The model must enforce a hard density budget per panel, card, column, or stage.

**Per-panel ceiling (max 5 visual elements):**
1. **One** illustrative icon (BioRender asset or FA glyph)
2. **One** short header (≤4 words, fragment, no period)
3. **One** short subtitle or descriptor (≤8 words, fragment, no period) — OPTIONAL
4. **One** numeric chip (≤6 characters: a number + a one-word unit, e.g. "200M cells", "~500k people", "$$$") — OPTIONAL
5. **One** inline coloured annotation (≤3 words, e.g. "60% fail", "doubled") — OPTIONAL

That is the ceiling. Anything beyond five elements must be cut, not added.

**Forbidden inside the figure:**
- ❌ Tool / model name lists (e.g. "AlphaFold 2/3, ESM-2, RFdiffusion") — these belong in the post body, not the figure.
- ❌ Multi-sentence descriptions inside a panel.
- ❌ Bullet-list paragraphs inside a panel.
- ❌ Citations or DOI strings.
- ❌ Methodology disclaimers ("results may vary", "individual results...").
- ❌ Legends repeating colour semantics already shown by direct labels.

**Allowed and encouraged:**
- ✅ A bare number with a one-word unit ("500k", "$1.2B", "60%", "30 yr").
- ✅ A single fragment header ("Whole humans", "Phase II", "Tissues").
- ✅ A single descriptor strap ("Population scale, multi-omic" — no period).
- ✅ A coloured annotation pinned next to a data point ("doubled in 30 yr").

**Compression strategies (apply when over budget):**
1. **Move tool lists out of the figure entirely.** Named models (AlphaFold, scGPT, UNI, etc.) live in the post's body text, not in the figure. The figure shows the *category*, not the *roster*.
2. **Replace prose captions with chip captions.** A sentence "Hundreds of millions of human cells contributed by a few thousand donors" → a chip "200M cells · 1.4k donors".
3. **Use icons to carry meaning.** Instead of writing "trial duration: 1–2 years", show a clock glyph next to "1–2 yr".
4. **Drop the description if the icon + header + chip already communicate it.** Three-line panels are usually two lines too many.

---

## 3. Common pitfalls (how to look "off-brand")

1. **Drawing the figure as line-art.** Thin grey strokes with white interiors is the AI-flatpack default and the strongest tell that the figure is off-brand. C2C is illustrative, not line-art.
2. **Outlined hollow person-icons.** Person-icons must be Font Awesome solid filled silhouettes. A line-drawn head-and-torso silhouette is wrong.
3. **Grey stippled / monochrome H&E tissue.** Tissue is stained pink + purple, not grey dots. If pink+purple cannot be rendered, omit the tissue square.
4. **Geometric sans-serifs.** Inter, IBM Plex, Poppins, Montserrat — all wrong. Lato or Open Sans only.
5. **Periods at the end of titles, subtitles, panel headers, axis labels, fragment captions.** The terminal-period rule must hold.
6. **Pure black** for any fill or stroke.
7. **Three or more saturated accent colours** in a single figure. Two only, drawn from the four-colour set.
8. **Tool / model name lists baked into the figure.** Names go in the post body.
9. **Wall-of-text panels** with multiple sentences each.
10. **Vertical gridlines.** Horizontal only.
11. **Top and right spines on charts.** Remove both.
12. **Boxed callouts with leader lines.** Annotations are inline coloured bold text, no box, no leader.
13. **Pastel mint / pale coral / "Notion illustration" tints.** The palette is saturated; pastels read as default-AI decoration.
14. **Drop shadows on chart elements** (bars, lines, dots, text). Drop shadows are reserved for BioRender biological assets only.
15. **PowerPoint defaults**: 3D bevels, gradients, presentation-template shapes.
16. **"Figure N:" baked into the image.** The post supplies the caption externally.
17. **Hallucinated model names** ("Boltz-Tx-2", "Living-Heart-Pro", garbled acronyms). If the input does not name the model, do not invent one.
18. **Mobile illegibility.** Every figure must read at ~600 px Substack mobile width. If text would shrink below ~9 pt at that width, cut text — do not shrink text.

---

## 4. Domain-specific styles

### 4.1 Scale / hierarchy diagram
*(e.g. biological scales of foundation models, layers of evidence)*

- Horizontal scale-axis, equally weighted stage panels left-to-right.
- Each stage panel obeys the 5-element density ceiling: one illustrative icon, one fragment header, optional one-line descriptor, optional numeric chip, optional inline annotation.
- Single solid arrowhead at the right end of the axis. **No connector arrows between stages** — the axis is hierarchy, not pipeline.
- The argument-carrying stage uses indigo for its icon fill and chip; non-argument stages use mid-grey for their icon fill (or BioRender pastel, e.g. pink for tissue).
- Empty / aspirational stage: dashed indigo border + a single chip "Not yet built" — no other text inside.

### 4.2 Pipeline / lifecycle diagram
*(e.g. drug-development phases, training loops)*

- Vertical-stack pipeline (top-to-bottom) **OR** horizontal pipeline (left-to-right). Pick one orientation per figure and hold it.
- Phase blocks are rounded rectangles with white fill, mid-grey thin border, and an internal coloured stripe matching the phase's accent colour.
- Forward arrows between phases are solid mid-grey with a small filled arrowhead. Feedback / aspirational arrows are dashed indigo.
- Per-phase numeric chips use the phase's accent colour. The argument-carrying phase uses indigo.
- Failure / attrition is encoded with rust-orange or coral-red proportional bars, not with text.

### 4.3 Comparative multi-panel diagram
*(e.g. three architectures side-by-side)*

- Equal-width columns separated by thin mid-grey vertical dividers.
- The argument-carrying column gets an indigo top edge accent and an indigo header. Non-argument columns have a mid-grey header.
- A "rail of sameness" — a thin mid-grey horizontal line — can run behind shared components across columns to signal "this is the same across columns".
- Per-column density budget identical to a stage panel: 5 elements max.

### 4.4 Converging-streams / fan-in diagram
*(e.g. multi-modal data inputs feeding a model)*

- Parallel input streams enter from above a central anchoring element (FA solid person-icon in indigo, or a labelled embedding chip).
- Each stream is one BioRender biological asset (DNA helix / protein blob / molecule hex / EHR card), one fragment label (≤2 words), and one numeric chip — three elements max per stream.
- The anchoring element is rendered in indigo. Streams converge into one joint rail beneath the anchor.
- The exit arrow from the joint rail is solid indigo with a filled arrowhead, terminating in an indigo-filled embedding chip.

### 4.5 Statistical chart embedded in an explanatory diagram
*(e.g. a bar chart, line chart, or attrition funnel that lives inside a larger figure)*

- Apply the C2C plot style guide rules to the chart sub-region.
- Bars: solid coloured fills, no outline. The argument bar uses indigo or the figure's primary accent. Comparison bars use the secondary accent.
- Lines: 2 px stroke, markers at every data point. Argument line is the primary accent; comparison line is the secondary accent.
- Reference line: dashed mid-grey, never solid, never coloured.
- Inline coloured annotations next to the argument data point, no leader line.

---

## 5. Drop-in usage

This guide is the C2C diagram analogue to `neurips2025_diagram_style_guide.md`. Activate by:

```bash
export PAPERBANANA_STYLE_GUIDE_PREFIX=correlation_to_causation
```

before launching PaperBanana. The Stylist agent will read `correlation_to_causation_diagram_style_guide.md`; the NeurIPS files remain available for any non-C2C work.

---

## 6. Authorial note for the model

When in doubt between two visual interpretations, ask: *"Would this fit naturally inside an Economist health-desk explainer? Would the biological assets look like they came out of BioRender?"* If both answers are yes, the figure is on-brand. If either answer is no — especially if the figure looks like thin grey lines on white — it is off-brand and must be redrawn.
