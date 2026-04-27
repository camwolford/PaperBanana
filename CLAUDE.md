# PaperBanana

## Repo Structure

- `origin` → `camwolford/PaperBanana` (personal fork — push here)
- `upstream` → `dwzhu-pku/PaperBanana` (original repo — pull updates from here)

## Syncing Upstream

```bash
git fetch upstream && git rebase upstream/main && git push
```

## Personal Files

- `my_inputs/` — personal paper inputs, organized by project (e.g., `my_inputs/nafld_review/`). Gitignored.
- `.env` — API keys. Gitignored. Source before running.
- `configs/model_config.yaml` — local config, gitignored. Uses new field names: `main_model_name`, `image_gen_model_name`.

## Running

Upstream ships two demos. **Default to Streamlit** (`demo.py`) — it's the more mature surface and matches user preference. Use Gradio (`app.py`) only when explicitly mirroring the HF Spaces deployment.

```bash
# Streamlit (default)
source .env && streamlit run demo.py

# Gradio (HF Spaces parity only)
source .env && python app.py
```

## Known Upstream Fixes

- `944c055` (2026-04) — OpenRouter refine path was silently dropping the input image, so refinements ran against no image. If a refined output looks identical to the prompt-only baseline, confirm this fix is in your tree (`git log --oneline | grep 944c055`).
