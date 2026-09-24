# 🧠 LLM Engineering Starter (`llm-engineering-starter`)

A comprehensive, 8-week hands-on engineering repository covering the practical implementation of Large Language Models (LLMs), Prompt Engineering, Retrieval-Augmented Generation (RAG), Fine-Tuning, and Autonomous Multi-Agent Systems.

---

## Project Overview

**LLM Engineering Starter** provides structured code notebooks, interactive laboratory exercises, and standalone agent implementations designed to transition engineers from foundational model calls to advanced autonomous multi-agent pipelines.

### Repository Naming Analysis
- **Recommended Repository Name**: `llm-engineering-starter`
- **Naming Formula**: **Formula C** (`[ecosystem/framework]-[sample/starter]`)
- **Rationale**: Replaces the generic snake_case `llm_engineering` with a descriptive kebab-case name specifying domain/ecosystem (`llm-engineering`) and role as an educational reference starter (`starter`).

---

## Features

- **8-Week Progressive Curriculum**:
  - **Week 1**: Local model inference with Ollama (`llama3.2`), OpenAI API fundamentals, and tokenization.
  - **Week 2**: Frontier models comparison (OpenAI, Anthropic Claude, Google Gemini) and cost optimization.
  - **Week 3**: Hugging Face pipelines, tokenizers, open-source model architectures, and Google Colab GPU execution.
  - **Week 4**: Embeddings, vector spaces, and semantic search.
  - **Week 5**: Retrieval-Augmented Generation (RAG) pipelines and vector databases (ChromaDB).
  - **Week 6**: Advanced prompting techniques, structured outputs, and evaluation metrics.
  - **Week 7**: Fine-tuning open models with custom datasets on GPU instances.
  - **Week 8**: Full-stack autonomous multi-agent systems with tool use and messaging integrations.
- **Local & Cloud Flexibility**: Supports completely offline inference via Ollama as well as cloud-hosted frontier LLMs.
- **Security-First Configuration**: Standardized environment variable resolution ensuring API keys and credentials are never hardcoded.

---

## Prerequisites

- **Python**: `>= 3.10`
- **Package Manager**: `pip` or `conda`
- **Jupyter Environment**: JupyterLab or VS Code Jupyter extension
- **Local Model Runner (Optional)**: [Ollama](https://ollama.com) for running open models locally

---

## Installation and Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/llm-engineering-starter.git
cd llm-engineering-starter
```

### 2. Configure Virtual Environment
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# Linux/macOS:
source .venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables
Copy `.env.example` to `.env` and insert your API credentials:
```bash
cp .env.example .env
```

---

## Configuration & Environment Variables

| Variable | Provider / Description | Required For |
| :--- | :--- | :--- |
| `OPENAI_API_KEY` | OpenAI API access | Weeks 1, 2, 5, 6, 8 |
| `ANTHROPIC_API_KEY` | Anthropic Claude API access | Weeks 2, 6 |
| `GOOGLE_API_KEY` | Google AI Studio API access | Week 2 |
| `HF_TOKEN` | Hugging Face Hub user access token | Weeks 3, 6, 7, 8 |
| `TWILIO_ACCOUNT_SID` | Twilio account identifier | Week 8 (Messaging Agent) |
| `TWILIO_AUTH_TOKEN` | Twilio authorization token | Week 8 (Messaging Agent) |

---

## Usage

### Quick Start with Ollama (Local)
1. Install and start Ollama from [ollama.com](https://ollama.com).
2. Pull the default lightweight model:
   ```bash
   ollama run llama3.2
   ```

### Launching JupyterLab
```bash
jupyter lab
```
Navigate to `week1/day1.ipynb` to begin the interactive exercises.

### Google Colab GPU Notebooks
For GPU-intensive modules (Weeks 3 & 7), pre-configured Google Colab notebooks are provided in each respective folder:
- **Week 3 (Hugging Face Pipelines)**: [Colab Pipeline Notebook](https://colab.research.google.com/drive/1aMaEw8A56xs0bRM4lu8z7ou18jqyybGm?usp=sharing)
- **Week 7 (Model Fine-Tuning)**: [Colab Fine-Tuning Day 1](https://colab.research.google.com/drive/15rqdMTJwK76icPBxNoqhI7Ww8UM-Y7ni?usp=sharing)

---

## Defensive Security Architecture

- **Credential Isolation**: All vendor tokens and API secrets are loaded strictly via `os.getenv()` from local `.env` files.
- **Git Hygiene**: Environment files (`.env`), vector database storage directories (`vector_db/`), model weights caches (`model_cache/`), and Jupyter temporary documents (`.virtual_documents/`, `.ipynb_checkpoints/`) are strictly untracked.
- **Cost Controls**: Recommended usage of cost-efficient models (`gpt-4o-mini`, `claude-3-haiku-20240307`) to prevent unexpected cloud billing spikes.

---
