# Portfolio Showcase Rules

## When to use this

Use this for any task involving resumes, portfolio posts, public repositories, demos, screenshots, public READMEs, writeups, sanitized examples, or showcase extraction.

## Core rule

Do not make this original repository public. Future portfolio work must be created in a separate sanitized repository, expected to be named `franchise-modeling-chatbot-showcase` unless the user specifies otherwise.

## What must be removed or rewritten before public release

Before anything is copied into a public showcase, review and sanitize:

- Customer, client, company, brand, contract, franchise, QA, and public-sector details.
- API keys, W&B identifiers, local paths, logs, model artifacts, datasets, vector DBs, and generated outputs.
- Internal comments, prompts, examples, screenshots, commit history, or filenames that reveal restricted context.
- Any non-public government-related or public-sector information.

## Showcase extraction approach

Build the showcase as a separate artifact with synthetic or approved sample data. Prefer documenting architecture and engineering approach over exposing raw source, raw prompts, private data, or operational details.

If code is copied, copy only reviewed, sanitized code. Do not mirror the private repository history.

## Public narrative guidance

Keep public claims grounded. It is acceptable to describe the visible architecture at a high level: Python RAG pipeline, Gemini integration, Chroma retrieval, Dockerized execution, and embedding training workflow. Do not imply deployment status, customer usage, competition results, or data provenance unless supported by sanitized public materials.
