# NAFLD Review Figure Revision — Design Spec

**Date:** 2026-04-14
**Status:** Draft
**Context:** Revising the hub-and-spoke "Central Illustration" for the Adiposity/T2DM/MASLD review paper (Dalakoti, Wolford et al.)

## Problem

The current PaperBanana-generated hub-and-spoke figure has four structural clarity issues:

1. **Inconsistent information layers** — each spoke packs pathway name, biomarkers, ethnicity, and outcome with varying visual hierarchy
2. **No clear reading order** — no obvious start point or directionality through the spokes
3. **Concordant/discordant distinction invisible** — the paper's central insight (PNPLA3/TM6SF2 = liver risk without ASCVD vs GCKR = liver + ASCVD) has no visual weight
4. **Ethnicity placement inconsistent** — ancestry labels float without visual logic

Additionally, reviewer feedback requires:

- "Visceral fat" → "ectopic fat spillover" (no evidence visceral fat per se is toxic)
- Remove OGTTs; keep fasting glucose + HbA1c
- Non-HDL-C leads over ApoB (UK cost/availability; ApoB as parenthetical for US readers)
- African ancestry's more favourable lipid profile noted on the haemodynamic spoke

## Approach: Sectored Hub-and-Spoke

Keep the hub-and-spoke identity the team preferred, but group the 5 spokes into 3 visual sectors. Each spoke follows a consistent 3-layer strip. A convergence arc connects two spokes to a shared vascular effector.

### Structure

**Hub (centre):** Energy Surplus & Adipose Tissue Expandability

**Left sector — Favourable (1 spoke):**

| Layer | Content |
|---|---|
| Pathway | Favourable Subcutaneous Expansion |
| Biomarkers | Preserved insulin sensitivity, lower ectopic fat, lower Non-HDL-C (or ApoB) |
| Outcome | Lower Cardiometabolic Risk |

No ancestry badge. Green/calming tones.

**Centre sector — Lipid Partitioning (3 spokes):**

| Spoke | Pathway | Biomarkers | Outcome | Label |
|---|---|---|---|---|
| Ectopic Fat Spillover | Lipid spillover to liver, muscle, visceral depots → insulin resistance | Insulin resistance, ceramides/sphingolipids, fasting glucose/HbA1c, Non-HDL-C (or ApoB) | T2DM & MASLD | — |
| Hepatic Lipid Export | GCKR-driven overproduction and export of TG-rich lipoproteins | GCKR pathway, TG-rich remnants, high Non-HDL-C/ApoB | ASCVD | **CONCORDANT** (red accent) |
| Hepatic Lipid Retention | PNPLA3/TM6SF2-driven lipid trapping; lower circulating lipids | PNPLA3/TM6SF2 variants, elevated liver enzymes, lower circulating lipids | MASLD-Fibrosis | **DISCORDANT** (blue accent) |

Amber/warm tones for the sector. Concordant spoke has red border/badge; discordant has blue.

**Right sector — Haemodynamic (1 spoke):**

| Layer | Content |
|---|---|
| Pathway | BP-Dominant Risk |
| Biomarkers | High blood pressure, LVH, target-organ markers |
| Outcome | Hypertensive Organ Damage (Stroke, Heart Failure) |

Blue tones (distinct from hepatic retention blue).

### Convergence Arc

A visual arc connecting the Ectopic Spillover and Hepatic Export spokes through a shared **Non-HDL-C / ApoB particle burden** node, then to ASCVD. The Hepatic Retention spoke explicitly bypasses this arc, reinforcing the discordant message visually.

### Ethnicity Badges

Small pill-shaped tags at a consistent position on each spoke:

| Spoke | Badge | Rationale |
|---|---|---|
| Ectopic Fat Spillover | South Asian / East Asian | Dysglycaemia and MASLD at lower BMI |
| Haemodynamic | African ancestry | More favourable lipid profile; BP burden predominates |
| All others | None | Gene-driven or population-agnostic |

Footnote: "Ancestry indicates predominant pathway tendency, not individual-level prediction."

## Manuscript Figure 1 Caption

> **Figure 1: A Pathway-Based Framework for Adiposity and Cardiometabolic Risk.** Energy surplus is partitioned through five biological pathways determined by adipose tissue expandability and hepatic lipid handling. The central hub represents positive energy balance; three sectors radiate outward, each containing spokes that trace a consistent path from biological mechanism through measurable biomarkers to clinical outcome.
>
> *Lipid partitioning sector (centre):* When subcutaneous storage is exceeded, lipid is redirected to ectopic sites (liver, muscle). The ectopic fat spillover spoke drives insulin resistance, dysglycaemia, and atherogenic particle burden. Two hepatic spokes are distinguished: a **concordant** pathway (GCKR-driven overproduction and export of triglyceride-rich lipoproteins, raising Non-HDL-C and ASCVD risk) and a **discordant** pathway (PNPLA3/TM6SF2-driven lipid retention, increasing fibrosis risk while lowering circulating atherogenic lipids). A convergence arc shows that ectopic spillover and hepatic export both feed Non-HDL-C/ApoB particle burden as a shared vascular effector, whereas hepatic retention bypasses this arc.
>
> *Haemodynamic sector:* A BP-dominant pathway leading to hypertensive target-organ damage (stroke, heart failure).
>
> *Favourable sector:* Preserved subcutaneous expansion with maintained insulin sensitivity and lower cardiometabolic risk.
>
> Ancestry badges indicate predominant pathway tendency as a pragmatic bedside clue (South Asian/East Asian on ectopic spillover; African ancestry on the haemodynamic spoke, noting a typically more favourable lipid profile), not individual-level prediction.

## PaperBanana Inputs

### Content (Methodology Section)

```
## Central Hub
Energy surplus and adipose tissue expandability. This is the central node of a radial hub-and-spoke diagram. All five pathways radiate outward from this hub. The hub represents the starting point: when energy intake exceeds expenditure, the body must partition surplus energy, and the outcome depends on adipose tissue's capacity to safely store it.

## Sector 1 (Left): Favourable Adiposity
This sector contains a single spoke representing the metabolically protective phenotype.

### Spoke: Favourable Subcutaneous Expansion
- Layer 1 (Pathway): Preserved subcutaneous adipose expansion — surplus energy is stored safely in subcutaneous fat depots without spillover to ectopic sites.
- Layer 2 (Biomarkers): Preserved insulin sensitivity, lower ectopic fat deposition, lower Non-HDL-C (or ApoB).
- Layer 3 (Outcome): Lower cardiometabolic risk.
- Visual: Spoke should use green/calming tones to signal this is the protective pathway. The outcome node should be visually distinct from adverse outcomes (e.g., green-tinted rounded rectangle).
- Note: No specific ancestry badge on this spoke. This phenotype occurs across populations.

## Sector 2 (Centre): Lipid Partitioning
This is the largest sector, containing three spokes. It represents what happens when subcutaneous storage capacity is exceeded or intrinsically limited, and lipid is redirected to ectopic sites (liver, muscle) or exported as atherogenic lipoproteins. Two of the three spokes carry special labels:
- "Concordant" means the pathway increases BOTH liver fat AND circulating atherogenic lipids, aligning hepatic and cardiovascular risk.
- "Discordant" means the pathway increases liver fat while LOWERING circulating lipids, dissociating hepatic risk from cardiovascular risk.

### Spoke 2.1: Ectopic Fat Spillover
- Layer 1 (Pathway): Ectopic fat spillover — when adipose storage is limited, lipid spills over into liver, muscle, and visceral depots, driving insulin resistance and metabolic dysfunction.
- Layer 2 (Biomarkers): Insulin resistance markers, ceramides and sphingolipids, fasting glucose and HbA1c, elevated Non-HDL-C (or ApoB).
- Layer 3 (Outcome): Type 2 diabetes (T2DM) and MASLD.
- Ancestry badge: "South Asian / East Asian" — these populations develop dysglycaemia and MASLD at lower BMI, consistent with earlier ectopic lipid deposition and/or beta-cell vulnerability.
- Visual: Warm/amber tones for this spoke.

### Spoke 2.2: Hepatic Lipid Overproduction and Export [CONCORDANT]
- Layer 1 (Pathway): Hepatic lipid overproduction and export — the liver overproduces and exports triglyceride-rich lipoproteins into the circulation. Driven by the GCKR genetic pathway. Both liver fat and circulating atherogenic lipids are elevated.
- Layer 2 (Biomarkers): GCKR pathway, triglyceride-rich remnant lipoproteins, high Non-HDL-C / ApoB particle burden.
- Layer 3 (Outcome): Atherosclerotic cardiovascular disease (ASCVD).
- Label: A visible "CONCORDANT" badge or border on this spoke, indicating that liver fat and cardiovascular risk are aligned.
- Visual: Red/coral accent to signal cardiovascular danger. Distinct border style or colour from the discordant spoke.

### Spoke 2.3: Hepatic Lipid Retention / Trapping [DISCORDANT]
- Layer 1 (Pathway): Hepatic lipid retention (trapping) — the liver retains lipid internally rather than exporting it. Driven by PNPLA3 I148M and TM6SF2 E167K genetic variants. Liver fat is elevated but circulating atherogenic lipids are lower.
- Layer 2 (Biomarkers): PNPLA3 and TM6SF2 genetic variants, elevated liver enzymes, lower circulating lipids (lower LDL-C, lower triglycerides).
- Layer 3 (Outcome): MASLD-fibrosis (liver injury and progressive fibrosis, without proportionate ASCVD risk).
- Label: A visible "DISCORDANT" badge or border, indicating that liver fat and cardiovascular risk are dissociated.
- Visual: Blue accent to contrast with the concordant spoke's red. The visual distinction between concordant (red) and discordant (blue) should be immediately obvious.

## Convergence Arc
Spoke 2.1 (Ectopic fat spillover) and Spoke 2.2 (Hepatic lipid overproduction/export) both feed into a shared downstream effector: Non-HDL-C / ApoB particle burden. This convergence should be shown as a visual arc or band connecting these two spokes before reaching ASCVD and T2DM outcomes. The convergence arc represents the key clinical simplification: diverse upstream pathways converge on atherogenic particle burden as the shared vascular effector.

Spoke 2.3 (Hepatic lipid retention) explicitly BYPASSES this convergence arc — it does not feed into Non-HDL-C/ApoB burden. This visual bypass reinforces the discordant message: liver fat without atherogenic particle burden.

## Sector 3 (Right): Haemodynamic Risk
This sector contains a single spoke representing the blood pressure-dominant pathway.

### Spoke: BP-Dominant Risk
- Layer 1 (Pathway): Haemodynamic / BP-dominant risk — cardiovascular risk driven primarily by blood pressure rather than lipid pathways.
- Layer 2 (Biomarkers): High blood pressure, left ventricular hypertrophy (LVH), target-organ damage markers.
- Layer 3 (Outcome): Hypertensive organ damage (stroke, heart failure).
- Ancestry badge: "African ancestry" — this population has a more favourable lipid profile but higher BP burden; haemodynamic risk predominates. When fatty liver is present, metabolic disturbances are pronounced, but the primary pathway is BP-driven.
- Visual: Blue tones for this spoke, distinct from the hepatic retention blue.

## Ancestry Badges (General)
Small pill-shaped or shield-shaped tags at a consistent position on each spoke. Only two spokes carry badges: Ectopic Spillover (South Asian / East Asian) and Haemodynamic (African ancestry). A small footnote at the bottom reads: "Ancestry indicates predominant pathway tendency, not individual-level prediction."

## Visual Consistency Rules
- Every spoke must follow the same three-layer structure: Pathway → Biomarkers → Outcome, reading outward from the hub.
- Each layer should be visually distinguishable (e.g., different container styles or background shades per layer).
- Outcome nodes at the outermost ring should be in rounded rectangles with colour matching their sector.
- Arrows or connection lines flow outward from hub through each layer.
- Background should be white or very light, clean and uncluttered.
- No figure title embedded in the image.
```

### Caption (Visual Intent)

```
Sectored hub-and-spoke diagram of a pathway-based framework for adiposity and cardiometabolic risk. Central hub represents energy surplus and adipose tissue expandability. Three sectors radiate outward: a left sector with one favourable subcutaneous expansion spoke; a central lipid partitioning sector with three spokes (ectopic fat spillover, concordant hepatic lipid export via GCKR, and discordant hepatic lipid retention via PNPLA3/TM6SF2); and a right haemodynamic sector with one BP-dominant risk spoke. Each spoke follows a consistent three-layer hierarchy from pathway mechanism through biomarkers to clinical outcome. A convergence arc links the ectopic spillover and hepatic export spokes through a shared Non-HDL-C/ApoB particle burden node toward ASCVD, while the hepatic retention spoke bypasses this arc toward MASLD-fibrosis. Small ancestry badges mark the ectopic spillover spoke (South Asian/East Asian) and haemodynamic spoke (African ancestry). Concordant and discordant labels visually distinguish the two hepatic spokes using contrasting colours.
```

### Recommended Settings

| Setting | Value | Rationale |
|---|---|---|
| Aspect ratio | 3:2 | Balanced layout for radial hub-and-spoke |
| Mode | Run BOTH Full Pipeline and Planner+Critic | Stylist may strip badges/labels; compare both |
| Candidates | 3 per mode | Complex structure benefits from diversity |
| Critic rounds | 3 | Default; diminishing returns beyond |

### Known Risks

1. **Critic may prematurely approve** (Issue #35) — manually inspect all candidates for missing spokes, layers, and the convergence arc
2. **Convergence arc is the most likely feature to get dropped** — described in both content and caption as mitigation
3. **Badges may be stripped by Stylist** — Planner+Critic mode skips the Stylist and preserves more detail

## Feedback Incorporated

| Feedback | How addressed |
|---|---|
| "Visceral fat" → "ectopic fat spillover" | Spoke renamed; "ectopic" used throughout |
| Remove OGTTs | Removed; fasting glucose + HbA1c retained |
| African ancestry has better lipids | Noted on haemodynamic spoke: "more favourable lipid profile" |
| Non-HDL-C over ApoB | Non-HDL-C leads everywhere; ApoB as parenthetical "(or ApoB)" |
| Simon Griffin may scrutinize | All biomarker choices defensible; Non-HDL-C as proxy for ApoB is well-established (PMID 36427190) |
