# NAFLD Review Figure Revision — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Update PaperBanana input files with the revised sectored hub-and-spoke content/caption, write the manuscript Figure 1 caption, and generate candidate figures.

**Architecture:** Three text file updates (content, caption, manuscript caption) followed by two PaperBanana generation runs (Full Pipeline + Planner+Critic modes) via the Streamlit GUI.

**Tech Stack:** PaperBanana Streamlit GUI (`demo.py`), text files

**Spec:** `docs/superpowers/specs/2026-04-14-nafld-figure-revision-design.md`

---

### File Map

| Action | Path | Purpose |
|---|---|---|
| Create | `my_inputs/nafld_review/content_v2.txt` | Revised structured content for PaperBanana |
| Create | `my_inputs/nafld_review/caption_v2.txt` | Revised hub-and-spoke caption for PaperBanana |
| Create | `my_inputs/nafld_review/manuscript_caption_v2.txt` | Revised Figure 1 caption for the review paper |
| Keep | `my_inputs/nafld_review/paper_content.txt` | Original content (preserved for reference) |
| Keep | `my_inputs/nafld_review/caption_B_hub_spoke.txt` | Original caption (preserved for reference) |

---

### Task 1: Write revised PaperBanana content input

**Files:**
- Create: `my_inputs/nafld_review/content_v2.txt`

- [ ] **Step 1: Write the structured content file**

Write the full content from the design spec's "Content (Methodology Section)" block to `my_inputs/nafld_review/content_v2.txt`. This is the text that goes in the Streamlit GUI "content" field.

The content starts with `## Central Hub` and ends with the `## Visual Consistency Rules` section. Copy it verbatim from the spec (lines 94–157 of `docs/superpowers/specs/2026-04-14-nafld-figure-revision-design.md`).

- [ ] **Step 2: Verify the content file**

Read `my_inputs/nafld_review/content_v2.txt` and check:
1. Starts with `## Central Hub`
2. Contains all 5 spokes (Favourable, Ectopic Spillover, Hepatic Export, Hepatic Retention, BP-Dominant)
3. Each spoke has Layer 1/2/3 entries
4. Contains `## Convergence Arc` section
5. Contains `## Ancestry Badges` section
6. Contains `## Visual Consistency Rules` section
7. Uses "ectopic fat spillover" not "visceral"
8. Uses "Non-HDL-C (or ApoB)" not "ApoB" alone
9. No OGTTs mentioned
10. Concordant/discordant defined in Sector 2 preamble

---

### Task 2: Write revised PaperBanana caption

**Files:**
- Create: `my_inputs/nafld_review/caption_v2.txt`

- [ ] **Step 1: Write the caption file**

Write the caption from the spec's "Caption (Visual Intent)" block (line 163 of the spec) to `my_inputs/nafld_review/caption_v2.txt`.

The caption is a single paragraph starting with "Sectored hub-and-spoke diagram of a pathway-based framework..." and ending with "...using contrasting colours."

- [ ] **Step 2: Verify the caption file**

Read `my_inputs/nafld_review/caption_v2.txt` and check:
1. Contains "Sectored hub-and-spoke diagram" (diagram type keyword for Retriever)
2. Names all 5 spokes
3. Mentions "three-layer hierarchy"
4. Mentions convergence arc and bypass
5. Mentions ancestry badges
6. Mentions concordant/discordant labels
7. Is a single paragraph (no line breaks — the Retriever matches on the full string)

---

### Task 3: Write revised manuscript Figure 1 caption

**Files:**
- Create: `my_inputs/nafld_review/manuscript_caption_v2.txt`

- [ ] **Step 1: Write the manuscript caption file**

Write the manuscript caption from the spec's "Manuscript Figure 1 Caption" section (lines 79–87 of the spec) to `my_inputs/nafld_review/manuscript_caption_v2.txt`.

This is the caption that goes into the review paper's .docx file. It starts with "**Figure 1: A Pathway-Based Framework for Adiposity and Cardiometabolic Risk.**" and includes the sector-by-sector description plus the ancestry badges note.

- [ ] **Step 2: Verify the manuscript caption**

Read `my_inputs/nafld_review/manuscript_caption_v2.txt` and check:
1. Uses "ectopic sites" not "visceral depots"
2. Describes three sectors explicitly
3. Explains concordant and discordant with gene names
4. Non-HDL-C leads over ApoB
5. Notes African ancestry's "more favourable lipid profile"
6. No OGTTs
7. Describes the convergence arc

- [ ] **Step 3: Commit all input files**

```bash
git add my_inputs/nafld_review/content_v2.txt my_inputs/nafld_review/caption_v2.txt my_inputs/nafld_review/manuscript_caption_v2.txt
git commit -m "Add revised NAFLD figure inputs: structured content, caption, and manuscript caption"
```

---

### Task 4: Generate candidate figures — Full Pipeline mode

This task is manual via the Streamlit GUI. The steps below are a checklist for the user.

- [ ] **Step 1: Launch PaperBanana**

```bash
source .env && streamlit run demo.py
```

- [ ] **Step 2: Configure GUI settings**

Set these in the Streamlit sidebar:
1. **Main Model Name** → `google/gemini-2.5-pro`
2. **Image Generation Model Name** → `google/gemini-3.1-flash-image-preview`
3. **Mode** → `Full pipeline` (demo_full)
4. **Aspect Ratio** → `3:2`
5. **Retrieval Setting** → default (not random — we want good reference matching for this complex figure)
6. **Number of Candidates** → `3`
7. **Max Critic Rounds** → `3`

- [ ] **Step 3: Paste content**

Copy the entire contents of `my_inputs/nafld_review/content_v2.txt` into the "Content" field.

- [ ] **Step 4: Paste caption**

Copy the entire contents of `my_inputs/nafld_review/caption_v2.txt` into the "Caption" field.

- [ ] **Step 5: Run generation**

Click "Generate" and wait for 3 candidates to complete. Each candidate takes 3–10 minutes.

- [ ] **Step 6: Review candidates**

For each candidate, check:
1. All 5 spokes present?
2. Consistent 3-layer structure per spoke?
3. Convergence arc visible?
4. Concordant/discordant visually distinct?
5. Ancestry badges present?
6. Hub clearly labelled?
7. Sector grouping visible?

Note which candidates pass and which features are missing.

---

### Task 5: Generate candidate figures — Planner+Critic mode

Same inputs, different mode. The Stylist is skipped, so more structural detail should be preserved (especially badges and labels).

- [ ] **Step 1: Change mode**

In the Streamlit sidebar, change:
- **Mode** → `Planner + Critic` (demo_planner_critic)
- All other settings stay the same as Task 4

- [ ] **Step 2: Run generation**

Click "Generate" and wait for 3 candidates. Same content and caption as Task 4.

- [ ] **Step 3: Review candidates**

Same checklist as Task 4 Step 6. Compare against the Full Pipeline candidates — does Planner+Critic preserve more detail (badges, labels, convergence arc)?

---

### Task 6: Select best candidate and next steps

- [ ] **Step 1: Compare all 6 candidates**

Pick the best candidate across both modes. Priority:
1. All 5 spokes present with 3-layer consistency
2. Convergence arc visible
3. Concordant/discordant visually distinct
4. Ancestry badges present
5. Overall aesthetic quality

- [ ] **Step 2: If convergence arc is missing from all candidates**

Re-run with the caption modified to emphasise the arc more heavily. Add to the end of the caption: "The convergence arc is the most important structural feature — it must be clearly visible as a band or curved connection linking ectopic spillover and hepatic export through a Non-HDL-C/ApoB node."

- [ ] **Step 3: Save best candidate**

Download the best figure image and save to `my_inputs/nafld_review/figure_v2_best.png`.

- [ ] **Step 4: Copy manuscript caption into the .docx**

Open `~/Desktop/Adiposity_T2DM_MASLD_With_Figure_v1_naveed_md_naveed2.docx` and replace the current Figure 1 caption (line 55) with the text from `my_inputs/nafld_review/manuscript_caption_v2.txt`.
