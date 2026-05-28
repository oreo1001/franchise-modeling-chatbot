# AGENTS.md

This file provides guidance to Codex and other coding agents working in this repository.

For Claude Code-specific entrypoint instructions, read:
- CLAUDE.md

For durable shared project instructions, read:
- docs/claude/README.md
- docs/claude/project-overview.md
- docs/claude/repository-map.md
- docs/claude/development-workflow.md
- docs/claude/testing-and-validation.md
- docs/claude/security-and-secrets.md
- docs/claude/portfolio-showcase-rules.md
- docs/claude/release-and-git-hygiene.md

Core rules for agents:
- Treat docs/claude/ as the shared instruction source of truth.
- Keep CLAUDE.md as the Claude Code router and AGENTS.md as the Codex/general-agent router.
- Do not duplicate long instruction bodies across AGENTS.md and CLAUDE.md.
- Do not expose secrets, credentials, private customer details, internal URLs, proprietary assets, or non-public business information.
- Do not make this private repository public.
- Public portfolio or showcase work must happen in a separate sanitized repository.
- Before editing, check git status, current branch, and HEAD.
- Keep edits scoped to the requested task.
- Review git diff before staging.
- Commit only intentional files.
- Report final branch, commit hash, validation, and git status.
