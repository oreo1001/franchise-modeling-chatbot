---
title: Bootstrap Claude Harness Docs Without Touching Product Code
date: 2026-05-28
category: documentation-gaps
module: agent-instructions
problem_type: documentation_gap
component: documentation
severity: low
applies_when:
  - "Bootstrapping agent instruction files in a private or restricted repository"
  - "Creating portfolio-readiness guidance without public-release cleanup"
  - "Validating documentation-only changes before commit"
tags: [claude-docs, documentation-only, privacy, git-hygiene, codex]
---

# Bootstrap Claude Harness Docs Without Touching Product Code

## Context

This repository needed Claude/Codex harness instructions, but the task explicitly limited edits to documentation structure and required privacy-first portfolio rules. The repo also had no prior `CLAUDE.md`, no formal Markdown tooling, and a small Python/Docker RAG layout inferred only from tracked files.

Two workflow issues surfaced during execution: some direct PowerShell commands hit a Windows sandbox runner error, and `git diff` did not show new files until they were added with intent-to-add.

## Guidance

For harness-documentation bootstraps, first map the repo from tracked files, then create a short root router plus topic-specific docs. Keep claims file-grounded and avoid adding unsupported product facts.

Use `git add -N` before reviewing a diff for brand-new files. Without intent-to-add, `git diff` can appear empty even though `git status --short` shows untracked documentation.

When a task requires compound learning, treat a `docs/solutions/` entry as a necessary documentation exception to a narrower docs-only boundary, and explain that exception before creating it.

If direct PowerShell filesystem helpers fail under the sandbox, prefer `rg`, targeted `Get-Content`, and git commands that already work in the environment. Escalate only when the required command is blocked and the workflow depends on it.

## Execution Review Notes

- Mistakes: Initial `git diff` review was too weak for brand-new files until intent-to-add made the new Markdown visible in the diff.
- Wrong assumptions: Assuming an empty unstaged diff was meaningful for untracked files would have hidden the actual documentation changes.
- Failed attempts: Some direct PowerShell status and filesystem commands failed with a Windows sandbox runner error, while `rg` and `git -C` checks remained usable.
- Review findings: The first compound note captured the lesson but did not explicitly label every requested category, so the doc was tightened before final completion.
- Final solutions: Created a concise `CLAUDE.md` router, modular `docs/claude/` topic files, and a categorized `docs/solutions/` learning.
- Prevention rules: Use `git add -N` for new-file diff review, verify committed filenames with `git show --name-only HEAD`, and keep privacy/showcase guidance explicit in agent docs.

## Why This Matters

Agent instruction docs can easily drift into invented architecture notes or accidental public-release work. Keeping the docs modular, grounded, and privacy-centered makes future sessions safer without changing application behavior.

The `git add -N` step is especially important because an empty `git diff` on untracked files can produce false confidence during review.

## When to Apply

- When adding or refreshing `CLAUDE.md`, `AGENTS.md`, or agent-facing docs in a private repo.
- When the task is documentation-only but still requires a reusable learning artifact.
- When validating new Markdown files before staging and committing.
- When sandbox behavior differs across direct PowerShell, `rg`, and git commands.

## Examples

Documentation-only validation sequence:

```powershell
git status
rg --files
git add -N CLAUDE.md docs/claude docs/solutions
git diff --name-only
git diff --stat
git diff
```

Privacy rule to preserve in future instruction docs:

```text
Future public portfolio work must happen in a separate sanitized showcase repository, not by making the private repository public.
```

## Related

- [../../claude/README.md](../../claude/README.md)
- [../../claude/security-and-secrets.md](../../claude/security-and-secrets.md)
- [../../claude/portfolio-showcase-rules.md](../../claude/portfolio-showcase-rules.md)
