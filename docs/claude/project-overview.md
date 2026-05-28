# Project Overview

## When to use this

Use this when you need a quick, file-grounded understanding of what this repository appears to contain before planning or editing.

## What the repository appears to be

This is a Python project for a franchise-related RAG workflow. The tracked files show a pipeline that:

- Builds a Chroma vector store from JSON input with `create_collection.py`.
- Runs Gemini-backed retrieval and answer generation through `franchise_service.py` and `run_inference.py`.
- Uses a Gemini-based reranker in `reranker.py`.
- Includes an embedding-model training script in `emb_dpr.py`, launched by `run_train.sh`.
- Provides Docker build files for GPU, CPU, and training-oriented images.

The README is a short Korean execution manual focused on Docker image loading, passing `GEMINI_API_KEY`, running `franchise_RAG.sh`, and launching training through `run_train.sh`.

## Stack inferred from files

- Language: Python 3.10 is used in the Dockerfiles.
- LLM provider: Google Gemini through `google-generativeai` and `google-genai`.
- Retrieval and vector store: LangChain, Hugging Face embeddings, Chroma.
- Training: PyTorch, Transformers, PEFT/LoRA, W&B, Accelerate.
- Runtime wrappers: Bash scripts and Docker.
- Configuration: `pydantic-settings` with `.env` support in `config.py`.

## Privacy posture

Treat this as a private or restricted repository. The file names and code indicate franchise, contract, QA, and dataset-oriented workflows, so any JSON data, vector databases, local datasets, logs, model artifacts, or generated answers may contain sensitive or proprietary material.

Never disclose private customer details, internal credentials, proprietary client information, restricted government-related materials, or non-public public-sector details in prompts, docs, commits, PRs, logs, examples, screenshots, or public summaries.

Future public portfolio or resume work must be extracted into a separate sanitized repository. Do not convert this original repository into the public showcase.
