# Release and Git Hygiene

## When to use this

Use this before staging, committing, pushing, opening a PR, preparing release notes, or doing any public/showcase cleanup.

## Branch and status discipline

Start by checking the current branch, HEAD commit, and `git status`. Preserve user changes and do not revert unrelated work.

Use a focused branch name that matches the task. Keep commits small enough to review.

## Diff review checklist

Before staging or committing, review `git diff` and confirm:

- Only intended files changed.
- No product source code changed during documentation-only tasks.
- No lockfiles, dependency files, Dockerfiles, CI, README, LICENSE, SECURITY.md, `pyproject.toml`, Dependabot config, production config, or public-release cleanup files changed unless explicitly required.
- No `.env`, logs, vector DBs, datasets, model artifacts, archives, keys, local task files, or generated output were added.
- No private customer details, credentials, proprietary client information, restricted government-related materials, or non-public public-sector details are present in the commit.

## Commit messages

Use clear, conventional messages when the user provides no project-specific format. Example:

```text
chore: bootstrap Claude harness docs
```

## Public release caution

Do not use this repository itself as the public artifact. Public portfolio work belongs in a separate sanitized showcase repository after a dedicated extraction and review step.
