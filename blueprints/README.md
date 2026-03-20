````markdown
# 🧠 n8n AI Intelligence Hub & Repository Classifier

An advanced, autonomous pipeline designed to discover, analyze, and organize the AI automation ecosystem. This system transforms unstructured GitHub repository data into a highly structured, deduplicated knowledge tree inside Notion using Large Language Models (LLMs).

## 🚀 Overview
This project solves the "information overload" in the n8n and AI sectors. Instead of a simple list of links, it builds a **Knowledge Architecture** where every resource is semantically analyzed and placed with surgical precision into a predefined technical taxonomy.

## 🏗️ System Architecture
The workflow operates as a modular production pipeline:

```mermaid
graph TD
    A[GitHub API Discovery] --> B[README & Metadata Extraction]
    B --> C[Content Normalization]
    C --> D[LLM Semantic Classification]
    D --> E[JSON Validation & Repair]
    E --> F[Category-to-Notion Block Mapping]
    F --> G[Deduplication Engine]
    G --> H[Notion Structured Storage]
````

## ⚙️ Key Features

  * **Leaf Node Precision:** The LLM is constrained to identify the most specific "leaf" category (e.g., `MCP Servers` instead of just `AI`), ensuring deep hierarchy placement.
  * **Deterministic Mapping:** A custom JavaScript engine bridges the gap between AI semantics and Notion's infrastructure by mapping categories to unique Block IDs.
  * **Intelligent Deduplication:** Before writing, the system performs a real-time traversal of existing Notion blocks to compare GitHub URLs, ensuring an idempotent database.
  * **LLM Safety Layer:** Includes a fail-soft JSON repair logic to handle non-standard outputs from models like GPT-4o-mini or Gemini 2.5 Flash.
  * **5-Tier Logic for AI Sales:** Specifically optimized to categorize GTM tools into: *Discovery ➔ Enrichment ➔ Intelligence ➔ Generation ➔ Lifecycle.*

## 🛠️ Tech Stack

  * **Orchestration:** [n8n](https://www.google.com/search?q=https://n8n.io/) (Self-hosted)
  * **Models:** Gemini 2.0 Flash, GPT-4o-mini (via OpenRouter)
  * **Storage:** Notion API (Hierarchical Database)
  * **Logic:** Node.js / JavaScript (Custom n8n Nodes)
  * **Data Source:** GitHub REST API

## 📋 Categorization Schema

The system maps repositories into specialized domains including:

  * **Infrastructure:** Docker, Cloud Native, Proxmox/LXC, Kubernetes.
  * **AI & Agents:** RAG Systems, MCP Protocol, Autonomous Browser Operators.
  * **Workflow Collections:** Production blueprints and template search engines.
  * **Security:** SecOps automation, audits, and vulnerability scanners.

## 🚦 Getting Started

1.  **Import:** Download the [workflow JSON](./github-repo-classifier.json) and import it into your n8n instance.
2.  **Configure:** Set up credentials for GitHub, Notion, and your LLM provider.
3.  **Map:** Replace the placeholder Notion Block IDs in the `Resolve Notion Block` node with your own structure.
4.  **Run:** Execute the search trigger to start the autonomous classification.

## 📈 Impact & Results

  * **1,000+ Repositories** processed and verified.
  * **40,000+ Automation Templates** mapped and indexed.
  * **100% Private Inference:** Optimized for local hardware (NVIDIA RTX 5090).

-----

*Built by [Paweł Wójcikiewicz (Nev89)](https://www.google.com/search?q=https://github.com/Nev89)*
