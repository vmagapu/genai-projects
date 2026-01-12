# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a GenAI projects template repository for experimenting with Large Language Models (LLM) and Diffusion models. It uses Ollama for local LLM inference and PyTorch with MPS (Metal Performance Shaders) support on macOS.

## Development Commands

```bash
# Activate virtual environment
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run Jupyter notebooks
jupyter notebook
# or
jupyter lab

# Ollama must be running for LLM experiments
ollama serve  # if not already running as a service
```

## Architecture

```
src/genai-projects/
├── llm/           # LLM utilities (generation, RAG, embeddings, eval)
├── diffusion/     # Image generation (txt2img, LoRA)
└── utils/         # Common utilities (IO, timing, seed)

notebooks/         # Jupyter notebooks for experiments
data/
├── raw/           # Raw input data
└── processed/     # Processed data
outputs/
├── images/        # Generated images
├── logs/          # Experiment logs
└── models/        # Saved models/checkpoints
```

## Key Dependencies

- **LLM**: `ollama`, `sentence-transformers`, `transformers`
- **Vector Search**: `faiss-cpu`
- **ML Framework**: `torch` (with MPS acceleration on Apple Silicon)
- **Web Apps**: `streamlit`, `fastapi`, `uvicorn`
- **Data**: `pandas`, `numpy`, `scikit-learn`

## Environment

- Python 3.13 with virtual environment in `.venv/`
- Uses `.env` for environment variables (see `.env.example`)
- MPS (Metal) acceleration available for PyTorch on macOS
