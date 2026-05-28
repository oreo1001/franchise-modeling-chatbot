# Repository Map

## When to use this

Use this when you need to find the relevant files for a task or verify that a change stays inside the expected area.

## Top-level files

- `README.md`: Korean Docker execution manual.
- `requirements.txt`: Python dependencies for RAG, Gemini, Chroma, PyTorch GPU packages, and training.
- `config.py`: Pydantic settings for `GEMINI_API_KEY`, vector DB path, Gemini model name, embedding model path, and device.
- `franchise_service.py`: Main Gemini and Chroma RAG service, including few-shot retrieval and answer generation.
- `reranker.py`: Gemini-based document reranker.
- `create_collection.py`: Converts input JSON files into Chroma documents and QA pairs.
- `run_inference.py`: Runs the RAG service and writes inference output to `/app/test/test_data.json`.
- `franchise_RAG.sh`: Bash entrypoint that builds the vector store and runs inference.
- `emb_dpr.py`: DPR/LoRA embedding training script using Transformers, PEFT, PyTorch, and W&B.
- `run_train.sh`: Bash entrypoint that exports `WANDB_API_KEY` and launches training through Accelerate.
- `check_google_model.py`: Lists Gemini models available for content generation.
- `sbert-wrapping.py`: Wraps a local transformer model into a SentenceTransformer format.
- `Dockerfile`: GPU runtime image for RAG inference.
- `Dockerfile.cpu`: CPU-oriented runtime image.
- `Dockerfile.train`: GPU training image.

## Data and test fixtures

- `test_data.json`, `test_data_flash1.5.json`, and `test_data_flash2.0.json` are tracked JSON files.
- `test/` contains tracked JSON files.
- Ignored local paths include vector databases, datasets, local model directories, logs, archives, and environment files.

Before using any JSON, dataset, vector DB, log, or generated output in a public context, review and sanitize it.

## Ignored local artifacts

The `.gitignore` excludes `.env`, logs, virtual environments, vector database paths, `/data`, local model directories such as `squad-v1/`, `dataset/`, archives, key/certificate files, and common generated artifacts.

Do not assume ignored files are safe to share. Ignored often means local, heavy, secret, or sensitive.

## Current documentation scope

The Claude instruction files live under `docs/claude/`. The root `CLAUDE.md` should remain a short index/router and should not become a large single-file manual.
