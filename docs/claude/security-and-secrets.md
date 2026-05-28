# Security and Secrets

## When to use this

Use this for any task touching configuration, environment variables, API calls, logs, JSON fixtures, vector databases, datasets, model artifacts, generated answers, Docker images, or portfolio/public-share work.

## Hard rules

Never expose, commit, paste, summarize publicly, screenshot, or send to external tools:

- Private customer details.
- Internal credentials or API keys.
- Proprietary client information.
- Restricted government-related materials.
- Non-public public-sector details.
- Raw contract, franchise, QA, dataset, vector DB, log, or generated-output content that has not been explicitly reviewed and sanitized.

## Secrets visible from code structure

`config.py` requires `GEMINI_API_KEY` and loads `.env`. `run_train.sh` exports `WANDB_API_KEY` from its first argument. `.gitignore` excludes `.env`, keys, certificates, logs, archives, local data, vector DBs, datasets, and model directories.

Keep these values and artifacts out of commits and public examples.

## Handling data safely

Assume JSON files, vector DBs, generated answers, logs, and training datasets may contain sensitive or proprietary information. Use synthetic or explicitly sanitized examples in public-facing docs.

If a task requires inspecting sensitive data, quote the smallest possible amount internally and avoid copying it into commits or final public summaries.

## External services

Gemini and W&B calls can send prompts, examples, metadata, or training information to external services. Do not run external-service workflows with real or sensitive data unless the task explicitly requires it and the user has provided the necessary authorization and credentials.
