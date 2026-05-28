# Testing and Validation

## When to use this

Use this when deciding how to verify a change before reporting it as complete.

## What is visible in the repository

The repository does not currently show a pytest suite, CI workflow, `pyproject.toml`, `package.json`, or other formal test runner configuration in the tracked files.

Validation should therefore be proportional to the change and grounded in available files.

## Documentation-only validation

For documentation changes:

- Confirm expected files exist.
- Check relative Markdown links between `CLAUDE.md` and `docs/claude/`.
- Review Markdown headings for consistent structure.
- Run `git diff` and verify that only intended docs changed.
- Confirm `.codex_task.md` or other local-only files were not staged.

## Code validation

For Python or script changes, choose the lightest useful checks that do not require unavailable secrets or large ignored artifacts:

- Import or syntax checks for changed Python files when feasible.
- Script help or dry-run behavior when available.
- Docker build checks only when the task concerns Docker and the local environment supports it.
- Avoid running Gemini, W&B, model download, CUDA, or vector DB workflows unless the task explicitly requires those external or heavy operations.

## Runtime prerequisites

The code expects `GEMINI_API_KEY` through settings. Training expects `WANDB_API_KEY` through `run_train.sh`. Local model directories, datasets, and vector stores are ignored and may not exist in a fresh checkout.

Do not treat missing local secrets, model artifacts, datasets, or vector DB directories as ordinary code failures unless the task is specifically about setup.
