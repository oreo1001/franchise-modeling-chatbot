# Claude Instruction Index

## When to use this

Use this document at the start of any Claude Code or Codex session in this repository. It explains which focused instruction file to open next.

## How to use these instructions

This repository uses a modular instruction structure. Read only the files relevant to the task, but always honor the privacy and git hygiene rules.

- Use [project-overview.md](project-overview.md) to understand the apparent purpose, stack, and constraints inferred from repository files.
- Use [repository-map.md](repository-map.md) when locating code, scripts, Dockerfiles, test fixtures, ignored artifacts, or documentation.
- Use [development-workflow.md](development-workflow.md) before changing project files.
- Use [testing-and-validation.md](testing-and-validation.md) before deciding what checks are appropriate.
- Use [security-and-secrets.md](security-and-secrets.md) for any task involving configuration, API keys, customer data, JSON fixtures, model artifacts, vector databases, or logs.
- Use [portfolio-showcase-rules.md](portfolio-showcase-rules.md) for any resume, portfolio, public-release, or showcase extraction work.
- Use [release-and-git-hygiene.md](release-and-git-hygiene.md) before staging, committing, pushing, or preparing a PR.

## Repository-wide rules

Keep the original repository private or restricted. Do not make this repository public as a portfolio shortcut.

Do not expose private customer details, internal credentials, proprietary client information, restricted government-related materials, or non-public public-sector details.

Do not commit local-only task files, local secrets, model checkpoints, vector databases, datasets, logs, or generated runtime output unless the task explicitly requires it and the diff has been reviewed for sensitive content.

Prefer small, grounded edits. Infer project facts from files in this repository, not from assumptions.
