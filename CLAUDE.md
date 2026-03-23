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

```bash
source .env && streamlit run demo.py
```
