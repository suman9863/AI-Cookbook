AI Cookbook
About the Project

AI Cookbook is building for real-world AI systems in Python. Instead of one monolithic app, it is organized as a set of independent modules that each demonstrate a specific AI engineering concept — from basic LLM calls to agents, retrieval-augmented generation (RAG), memory, and the Model Context Protocol (MCP). Each module has its own scripts and dependencies, so you can drop any single example straight into your own project.

Main folders:

Folder	What it covers
agents/	Building agents from scratch — from a single augmented LLM call up to prompt chains, tool-calling agents, an agent harness, and multi-agent setups
patterns/workflows	Core LLM workflow patterns (chaining, routing, parallelization, etc.)
models/openai	OpenAI API basics — endpoints, Assistants, structured outputs, the Responses API, agents, GPT-OSS, video, web, and human-in-the-loop
models/whisper	Audio transcription using OpenAI's Whisper
knowledge/agentic-rag	Building a RAG agent with custom tools, streaming, and structured output
knowledge/hybrid-retrieval	Combining keyword (BM25) search with vector embeddings, reciprocal rank fusion, and reranking
knowledge/docling	Document extraction, chunking, embedding, search, and chat over documents with Docling
knowledge/mem0	Long-term memory for AI agents using Mem0 (cloud and self-hosted)
mcp/	An MCP crash course (server setup, OpenAI integration, Docker, lifecycle) and example MCP servers
context/web	Giving agents web access — page fetching, web search, and search agents
tools/uv-guide	Guide to using uv as the Python package/project manager for this repo
roadmaps/	Suggested learning roadmaps for becoming an AI engineer
How to Run

This repo uses uv for Python environment and dependency management (Python 3.12).

Install uv (see tools/uv-guide/README.md for details), then clone the repo:
bash
   git clone https://github.com/suman9863/ai-cookbook.git
   cd ai-cookbook
Set your API key(s). Copy the example env file and fill in your key(s):
bash
   cp .env.example .env
   # then edit .env and add your OPENAI_API_KEY (and any other keys a module needs)
Go into the module you want to run — each one is self-contained with its own requirements.txt:
bash
   cd models/openai        # example: pick any module folder
   uv venv
   uv pip install -r requirements.txt
Run a script:
bash
   uv run 1-introduction/some_script.py

Check the README.md inside each module for any extra setup (e.g. knowledge/mem0 and mcp/crash-course also use docker compose up -d to spin up local services before running examples).

Models and Tools Used
Purpose	Model / Tool
Chat / reasoning LLM	OpenAI GPT family — gpt-4, gpt-4o, gpt-4o-mini, gpt-4.1, gpt-4.1-nano, gpt-5, gpt-5-mini, gpt-5-nano, gpt-3.5-turbo
Open-weight LLM	gpt-oss (via OpenAI's open-weight models example)
Speech-to-text	OpenAI Whisper
Text embeddings	OpenAI text-embedding-3-small / text-embedding-3-large
Keyword search	BM25 (used in hybrid retrieval)
Reranking	Cross-encoder / Cohere Rerank (rerank-v4.0-fast)
Document parsing	Docling
Long-term agent memory	Mem0 (cloud and open-source)
Agent-tool interoperability	Model Context Protocol (MCP)
Package/environment manager	uv
# AI Cookbook

## About the Project

AI Cookbook is a collection of standalone, copy/paste-ready examples and tutorials for building real-world AI systems in Python. Instead of one monolithic app, it is organized as a set of independent modules that each demonstrate a specific AI engineering concept — from basic LLM calls to agents, retrieval-augmented generation (RAG), memory, and the Model Context Protocol (MCP). Each module has its own scripts and dependencies, so you can drop any single example straight into your own project.

Main folders:

| Folder | What it covers |
|---|---|
| `agents/` | Building agents from scratch — from a single augmented LLM call up to prompt chains, tool-calling agents, an agent harness, and multi-agent setups |
| `patterns/workflows` | Core LLM workflow patterns (chaining, routing, parallelization, etc.) |
| `models/openai` | OpenAI API basics — endpoints, Assistants, structured outputs, the Responses API, agents, GPT-OSS, video, web, and human-in-the-loop |
| `models/whisper` | Audio transcription using OpenAI's Whisper |
| `knowledge/agentic-rag` | Building a RAG agent with custom tools, streaming, and structured output |
| `knowledge/hybrid-retrieval` | Combining keyword (BM25) search with vector embeddings, reciprocal rank fusion, and reranking |
| `knowledge/docling` | Document extraction, chunking, embedding, search, and chat over documents with Docling |
| `knowledge/mem0` | Long-term memory for AI agents using Mem0 (cloud and self-hosted) |
| `mcp/` | An MCP crash course (server setup, OpenAI integration, Docker, lifecycle) and example MCP servers |
| `context/web` | Giving agents web access — page fetching, web search, and search agents |
| `tools/uv-guide` | Guide to using `uv` as the Python package/project manager for this repo |
| `roadmaps/` | Suggested learning roadmaps for becoming an AI engineer |

## How to Run

This repo uses **[uv](https://docs.astral.sh/uv/)** for Python environment and dependency management (Python 3.12).

1. **Install uv** (see `tools/uv-guide/README.md` for details), then clone the repo:
   ```bash
   git clone https://github.com/daveebbelaar/ai-cookbook.git
   cd ai-cookbook
   ```

2. **Set your API key(s).** Copy the example env file and fill in your key(s):
   ```bash
   cp .env.example .env
   # then edit .env and add your OPENAI_API_KEY (and any other keys a module needs)
   ```

3. **Go into the module you want to run** — each one is self-contained with its own `requirements.txt`:
   ```bash
   cd models/openai        # example: pick any module folder
   uv venv
   uv pip install -r requirements.txt
   ```

4. **Run a script:**
   ```bash
   uv run 1-introduction/some_script.py
   ```

Check the `README.md` inside each module for any extra setup (e.g. `knowledge/mem0` and `mcp/crash-course` also use `docker compose up -d` to spin up local services before running examples).

## Models and Tools Used

| Purpose | Model / Tool |
|---|---|
| Chat / reasoning LLM | OpenAI GPT family — `gpt-4`, `gpt-4o`, `gpt-4o-mini`, `gpt-4.1`, `gpt-4.1-nano`, `gpt-5`, `gpt-5-mini`, `gpt-5-nano`, `gpt-3.5-turbo` |
| Open-weight LLM | `gpt-oss` (via OpenAI's open-weight models example) |
| Speech-to-text | OpenAI **Whisper** |
| Text embeddings | OpenAI `text-embedding-3-small` / `text-embedding-3-large` |
| Keyword search | **BM25** (used in hybrid retrieval) |
| Reranking | Cross-encoder / Cohere **Rerank** (`rerank-v4.0-fast`) |
| Document parsing | **Docling** |
| Long-term agent memory | **Mem0** (cloud and open-source) |
| Agent-tool interoperability | **Model Context Protocol (MCP)** |
| Package/environment manager | **uv** |
