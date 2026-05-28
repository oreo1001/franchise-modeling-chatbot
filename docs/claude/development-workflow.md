# Development Workflow

## When to use this

Use this before changing files in the repository.

## Default workflow

1. Check `git status` before editing.
2. Read the smallest set of files needed to understand the requested change.
3. Keep edits scoped to the task and the relevant file family.
4. Do not rewrite unrelated code or documentation.
5. Review the diff before reporting completion.
6. Verify that sensitive files, ignored artifacts, and local-only task files were not staged accidentally.

## Change boundaries

For documentation-only tasks, do not change product source code, Dockerfiles, dependency files, lockfiles, CI, release cleanup files, or runtime configuration unless the task explicitly requires it.

For product-code tasks, preserve the existing simple script-oriented structure unless there is a clear, file-supported reason to introduce new architecture.

## Project-specific cautions

This project uses environment-backed settings and local runtime artifacts. Do not hard-code API keys, local absolute paths, customer data, or deployment-specific secrets.

The code includes Korean prompts and comments. Preserve Korean text where it carries behavior, user-facing instructions, or domain meaning. Do not translate behavior-critical text casually.

Some scripts target Docker paths such as `/app/test`. When changing runtime code, account for the Docker execution model shown in `README.md` and Dockerfiles.

## Dependency management

The repository currently shows `requirements.txt` as the Python dependency source. Do not introduce another package manager or dependency file unless the task explicitly asks for it.

Dependency changes can alter model, GPU, and Docker behavior. Treat them as higher-risk than ordinary documentation edits.
