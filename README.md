# 🤖 Local AI Automation Infrastructure (n8n + Ollama)

[](https://opensource.org/licenses/Apache-2.0)

Self-hosted automation stack integrated with a local LLM inference server, deployed for internal use in an engineering environment. This repository documents the configuration, deployment decisions, and operational notes for a fully local AI infrastructure — **zero external API calls for inference, no vendor lock-in.**

-----

## 🧩 Production Workflows (Blueprints)

This repository hosts production-ready n8n workflows integrated with local LLMs.

  * **[GitHub Repository Classifier](https://www.google.com/search?q=blueprints/README.md):** An autonomous engine that classifies technical repositories into a structured Notion database.
      * *Features:* Semantic analysis (Gemini/GPT), JSON auto-repair, and Notion block mapping.
      * *Source:* [github-repo-classifier.json](https://www.google.com/search?q=blueprints/github-repo-classifier.json)

-----

## 🛠 Stack

| Service | Role | |
|---|---|
| **n8n** | Workflow automation engine (self-hosted) | |
| **Ollama** | Local LLM inference server | |
| **Supabase** | PostgreSQL database + pgvector for RAG | |
| **Qdrant** | Vector store for semantic search | |
| **Open WebUI** | Chat interface for local models | |
| **Langfuse** | LLM observability and tracing | |
| **Neo4j** | Knowledge graph (GraphRAG) | |
| **SearXNG** | Private web search | |
| **Portainer** | Docker container management | |

All services run as Docker containers via [coleam00/local-ai-packaged](https://github.com/coleam00/local-ai-packaged).

-----

## 🖥 Hardware Configuration

Optimized for high-density local inference and large-scale data processing.

  - **GPU:** NVIDIA GeForce **RTX 5090 (32 GB VRAM)**
  - **CPU:** AMD Ryzen 7 9700X (Zen 5, AVX-512)
  - **RAM:** 64 GB DDR5 6000 MHz
  - **SSD:** Samsung 990 EVO Plus 1TB (NVMe, PCIe 4.0)
  - **OS:** Ubuntu 24.04 LTS

-----

## 🧠 Models (Ollama)

Models selected for dense architecture optimized for the 32 GB VRAM envelope:

| Model | Quantization | Logic/Reasoning | Tools/Automation | Speed | |
|---|---|---|---|---|
| **Qwen3-32B** | Q6\_K\_L | ★★★★★ | ★★★★★ | ★★★☆☆ | |
| **DeepSeek-R1-Distill-32B** | Q6\_K | ★★★★★ | ★★★☆☆ | ★★☆☆☆ | |
| **Mistral-Small-3.2-24B** | Q8\_0 | ★★★★☆ | ★★★★★ | ★★★★★ | |
| **Gemma-3-27B-IT** | Q8\_0 | ★★★★☆ | ★★★★★ | ★★★★☆ | |

-----

## 🔌 MCP Integration (Model Context Protocol)

n8n is connected to **Claude Code** via [n8n-mcp](https://github.com/czlonkowski/n8n-mcp), enabling natural language workflow management.

### Claude Code Environment

Claude Code routes through local **Qwen3-Coder (30B)** running on the RTX 5090:

```powershell
$env:ANTHROPIC_AUTH_TOKEN="ollama"
$env:ANTHROPIC_BASE_URL="http://[INTERNAL_IP]:11434"
claude --model qwen3-coder:30b
```

-----

## 🚀 Deployment & Operational Notes

### Supabase Pooler — CRLF fix (Linux)

```bash
sed -i 's/\r$//' supabase/docker/volumes/pooler/pooler.exs
```

### n8n LAN Access (HTTP)

```bash
N8N_SECURE_COOKIE=false
```

-----

## 💾 Backup Strategy

1.  **Folder Archive:** Compressed `tar.gz` of the full project directory.
2.  **System Snapshots:** Timeshift for OS and NVIDIA driver stability.
3.  **Bare Metal:** Rescuezilla for full 1:1 disk cloning.

-----

### Resources

  * [coleam00/local-ai-packaged](https://github.com/coleam00/local-ai-packaged)
  * [czlonkowski/n8n-mcp](https://github.com/czlonkowski/n8n-mcp)
  * [Nev89 Intelligence Hub](https://www.google.com/search?q=https://github.com/NeV89/Nev89/blob/main/docs/intelligence-hub.md)
