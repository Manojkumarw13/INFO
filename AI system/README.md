# 🧠 Personal AI Operating System (PAIOS) & Free AI Models: Master Guide

Welcome to the master workspace for building a **Personal AI Operating System (PAIOS)** and utilizing the **2026 Free AI Models** ecosystem. This workspace contains blueprints, configurations, schemas, and study paths designed to help you construct a self-hosted, zero-licensing-cost agentic system on a standard laptop.

---

## 📖 Table of Contents
1. [🗺️ Directory Mapping & Navigation Hub](#1-️-directory-mapping--navigation-hub)
2. [🏛️ Personal AI OS (PAIOS) Core Architecture](#2-️-personal-ai-os-paios-core-architecture)
   * 2.1 [Core Philosophy & Design Principles](#21-core-philosophy--design-principles)
   * 2.2 [System Architecture & Data Flows](#22-system-architecture--data-flows)
   * 2.3 [The 9 Core Components](#23-the-9-core-components)
   * 2.4 [Agent Hierarchy & Task Queue Protocol](#24-agent-hierarchy--task-queue-protocol)
   * 2.5 [Memory Architecture (pgvector + Redis)](#25-memory-architecture-pgvector--redis)
   * 2.6 [Knowledge Management Flow (Notion & Obsidian)](#26-knowledge-management-flow-notion--obsidian)
   * 2.7 [Task Orchestration (n8n Master Router)](#27-task-orchestration-n8n-master-router)
3. [⚙️ PAIOS Infrastructure & Operations Setup](#3-️-paios-infrastructure--operations-setup)
   * 3.1 [Core docker-compose.yml Setup](#31-core-docker-composeyml-setup)
   * 3.2 [Environment Variables & Secrets (.env)](#32-environment-variables--secrets-env)
   * 3.3 [Custom MCP Server Configuration](#33-custom-mcp-server-configuration)
   * 3.4 [Database Schemas (Tasks, Memory, Logs)](#34-database-schemas-tasks-memory-logs)
   * 3.5 [Backup, Recovery & Automation Scripts](#35-backup-recovery--automation-scripts)
   * 3.6 [Troubleshooting & Laptop Resource Tuning](#36-troubleshooting--laptop-resource-tuning)
4. [🛣️ Choose Your Pathway: Comparison of Build & Learning Roadmaps](#4-️-choose-your-pathway-comparison-of-build--learning-roadmaps)
   * 4.1 [The 6-Week Project Build Plan](#41-the-6-week-project-build-plan)
   * 4.2 [The 8-Week Windows Study Track](#42-the-8-week-windows-study-track)
   * 4.3 [Windows Deployment Roadmap (19 Deep-Dive Sections)](#43-windows-deployment-roadmap-19-deep-dive-sections)
   * 4.4 [YouTube-Only Learning Path](#44-youtube-only-learning-path)
5. [🆓 Free AI Models Landscape (2026)](#5-free-ai-models-landscape-2026)
   * 5.1 [Provider Deep Dives & Free Tier Limits](#51-provider-deep-dives--free-tier-limits)
   * 5.2 [Capability Rankings (Coding, Reasoning, Speed, Context)](#52-capability-rankings-coding-reasoning-speed-context)
   * 5.3 [Zero-Cost Inference Stacks](#53-zero-cost-inference-stacks)
   * 5.4 [Privacy, Data Handling & API Compatibility](#54-privacy-data-handling--api-compatibility)
6. [🧰 The Complete AI OS Toolkit & Reference Stacks](#6-the-complete-ai-os-toolkit--reference-stacks)
   * 6.1 [Toolkit Index](#61-toolkit-index)
   * 6.2 [Recommended Architectures (Stacks A, B, C, D)](#62-recommended-architectures-stacks-a-b-c-d)
7. [🚀 Next Steps & Getting Started](#7-next-steps--getting-started)

---

## 1. 🗺️ Directory Mapping & Navigation Hub

Below is the directory map of the 9 core files in this folder. Use these links to access deep documentation, complete implementations, and step-by-step schedules.

| File Name | Size | Category | Core Purpose | Quick Link |
| :--- | :--- | :--- | :--- | :--- |
| **README.md** | ~25 KB | Navigation & Synthesis | Master folder index, synthesis of architectures, models, and study paths. | [README.md](README.md) |
| **personal-ai-os-architecture.md** | 83 KB | Architecture Blueprint | System diagrams, database schema definitions, Docker configs, and MCP files. | [personal-ai-os-architecture.md](personal-ai-os-architecture.md) |
| **AI_OS_Complete_Toolkit_Guide.md** | 48 KB | Tool Directory | Reference guide for 20+ coding agents, frameworks, vector DBs, and DevOps tools. | [AI_OS_Complete_Toolkit_Guide.md](AI_OS_Complete_Toolkit_Guide.md) |
| **PAIOS_6Week_Project_Roadmap.md** | 102 KB | Chronological Roadmap | Project-first 6-week build plan containing 18 mini-projects and 3 Capstones. | [PAIOS_6Week_Project_Roadmap.md](PAIOS_6Week_Project_Roadmap.md) |
| **ai_agent_os_8week_roadmap.md** | 72 KB | Chronological Roadmap | Chronological study & build schedule mapped across 8 weeks for local setups. | [ai_agent_os_8week_roadmap.md](ai_agent_os_8week_roadmap.md) |
| **AI_Agent_OS_Roadmap.md** | 74 KB | Windows Deployment | A 19-section learning path optimized for Windows deployment using WSL2. | [AI_Agent_OS_Roadmap.md](AI_Agent_OS_Roadmap.md) |
| **PAIOS_YouTube_Roadmap.md** | 93 KB | Learning Path | Curated YouTube-only tutorial schedule spanning foundation through production. | [PAIOS_YouTube_Roadmap.md](PAIOS_YouTube_Roadmap.md) |
| **free-ai-models-comprehensive-2026.md** | 144 KB | Model Analysis | Mega-compilation mapping free models, AI tooling, and PAIOS architecture. | [free-ai-models-comprehensive-2026.md](free-ai-models-comprehensive-2026.md) |
| **free-cloud-ai-models-2026.md** | 36 KB | Model Analysis | Limitations, comparison tables, and analysis of 10 cloud-hosted API providers. | [free-cloud-ai-models-2026.md](free-cloud-ai-models-2026.md) |
| **free-ai-models-guide-2026.md** | 35 KB | Model Analysis | Summary rankings, decision trees, and free-tier stacking inference paths. | [free-ai-models-guide-2026.md](free-ai-models-guide-2026.md) |

---

## 2. 🏛️ Personal AI OS (PAIOS) Core Architecture

### 2.1 Core Philosophy & Design Principles
PAIOS is built on the philosophy of **"One Interface → Multiple Agents → One Brain → One Database → One Workflow Engine"**.
*   **Zero Licensing Cost**: Rely strictly on open-source frameworks and free tier APIs.
*   **Laptop-First Execution**: Optimized to run on devices with 8GB–32GB RAM using quantized local models and fast cloud APIs.
*   **Single Pane of Glass**: OpenCode serves as the terminal control center, interacting with databases, workflows, and version control via MCP.

### 2.2 System Architecture & Data Flows
```
   [ User NLP Command ] ──► [ OpenCode (Command Center) ]
                                      │ (MCP JSON-RPC)
                                      ▼
                             [ MCP Server Hub ]
                                      │
               ┌──────────────────────┼──────────────────────┐
               ▼                      ▼                      ▼
       [ PostgreSQL DB ]       [ n8n Workflows ]       [ GitHub Repos ]
               │                      │
               └──────────┬───────────┘
                          ▼
       [ Agent Layer: Hermes (Ollama) / CrewAI / OpenHands ]
```
1. **The User** submits instructions in plain English to the [OpenCode](personal-ai-os-architecture.md#31-opencode--the-command-center) console.
2. **OpenCode** uses the Model Context Protocol (MCP) to read databases, fetch code structures, or trigger automation webhooks in **n8n**.
3. **n8n** routes tasks to **Hermes Agent** (planning), **OpenHands** (coding execution), or **CrewAI** (multi-agent research).
4. Results are committed to **GitHub**, indexed in **Notion**, and written to **PostgreSQL**.

### 2.3 The 9 Core Components
The system integrates 9 critical components across four functional layers:
1.  **OpenCode (Control Layer)**: The command interface and MCP client. Details: [OpenCode](personal-ai-os-architecture.md#3-component-explanations).
2.  **Hermes Agent v0.14.0 (Planning Layer)**: Local reasoning engine optimized for structured JSON outputs and planning. Details: [Hermes Agent](personal-ai-os-architecture.md#3-component-explanations).
3.  **n8n (Orchestration Layer)**: The visual workflow engine triggering webhook routes. Details: [n8n Automation](personal-ai-os-architecture.md#3-component-explanations).
4.  **CrewAI (Execution Layer)**: Multi-agent research crew that handles data scraping and text composition. Details: [CrewAI Teams](personal-ai-os-architecture.md#3-component-explanations).
5.  **OpenHands (Execution Layer)**: Sandboxed software engineering agent that writes code, runs tests, and commits fixes. Details: [OpenHands](personal-ai-os-architecture.md#3-component-explanations).
6.  **Notion / AppFlowy (Knowledge Layer)**: Human-readable project dashboards, notes, and records. Details: [Notion Integration](personal-ai-os-architecture.md#3-component-explanations).
7.  **PostgreSQL (Memory Layer)**: Relational DB containing task state, episodic logs, and semantic vector embeddings via `pgvector`. Details: [PostgreSQL Brain](personal-ai-os-architecture.md#3-component-explanations).
8.  **GitHub (Repository Layer)**: Code hosting, PR hooks, and actions-based testing. Details: [GitHub Integration](personal-ai-os-architecture.md#3-component-explanations).
9.  **Docker (Runtime Layer)**: Infrastructure virtualization engine containing the entire network. Details: [Docker Runtime](personal-ai-os-architecture.md#3-component-explanations).

### 2.4 Agent Hierarchy & Task Queue Protocol
Agents operate in a three-tier command structure:
*   **Planner (Hermes)**: Receives parent tasks, parses objectives, and publishes subtask plans.
*   **Worker Agents (OpenHands, CrewAI)**: Claim tasks corresponding to their specialty.
*   **Reviewer (CrewAI)**: Quality-checks outputs before completing the workflow lifecycle.

The task routing protocol relies on a shared JSON schema stored in a PostgreSQL table:
```json
{
  "task_id": "uuid",
  "project_id": "uuid",
  "parent_task_id": "uuid|null",
  "type": "code|research|plan|write|analyze|review|notify",
  "title": "Implement User Authentication",
  "priority": 3,
  "status": "pending|running|done|failed",
  "assigned_to": "openhands|crewai|hermes",
  "payload": { "repo_url": "git://..." },
  "result": { "commit_hash": "a1b2c3d4" }
}
```
*Detail file:* [Agent Hierarchy & Communication](personal-ai-os-architecture.md#4-agent-architecture)

### 2.5 Memory Architecture (pgvector + Redis)
PAIOS implements a multi-tier memory stack:
*   **Working Memory (Redis)**: Short-term cache and Pub/Sub channel for active agent negotiations.
*   **Episodic Memory (PostgreSQL)**: Transaction-logged history of actions, reasoning logs, and token usage.
*   **Semantic Memory (pgvector)**: Cosmic vector indexes utilizing 768-dimension embeddings generated by `nomic-embed-text`.

```sql
-- Store a semantic memory
SELECT store_memory('FASTAPI async routes are handled via async def', 'technical_fact', 'research_agent', 'project_uuid', 'task_uuid', 0.8);

-- Recall relevant context via cosine distance
SELECT content, cosine_distance(embedding, '[0.12, 0.43, ...]') AS distance 
FROM memory_store ORDER BY distance ASC LIMIT 5;
```
*Detail file:* [Memory Architecture Details](personal-ai-os-architecture.md#5-memory-architecture)

### 2.6 Knowledge Management Flow (Notion & Obsidian)
*   **Data Injection**: n8n intercepts web scrapes, conversational notes, or terminal logs and splits them into 512-token chunks.
*   **Obsidian Vault Sync**: Stored as markdown files locally.
*   **Notion Hub Sync**: n8n maps metadata fields into Notion database properties (e.g., Projects, Task Tracker, Daily Logs).
*   *Detail file:* [Knowledge Flow & Notion Config](personal-ai-os-architecture.md#6-knowledge-management)

### 2.7 Task Orchestration (n8n Master Router)
The central n8n master router manages the entire pipeline:
```
[Webhook Input] ──► [Parse & Validate Code] ──► [Switch Node (type)]
                                                    ├──► "code"     ──► [OpenHands API]
                                                    ├──► "research" ──► [CrewAI FastAPI]
                                                    └──► "plan"     ──► [Ollama Hermes API]
```
*Detail file:* [Task Lifecycle and Orchestration](personal-ai-os-architecture.md#7-task-orchestration)

---

## 3. ⚙️ PAIOS Infrastructure & Operations Setup

### 3.1 Core docker-compose.yml Setup
The entire PAIOS stack is spun up via a unified Compose file. It configures the Postgres database (with pgvector), Redis queue, Ollama engine, n8n orchestrator, custom agents, and a Prometheus/Grafana monitoring dashboard.
*   *Full configuration location:* [Main docker-compose.yml File](personal-ai-os-architecture.md#121-main-docker-composeyml)

### 3.2 Environment Variables & Secrets (.env)
The environment configuration template holds the API keys, credentials, and model flags.
*   *Environment blueprint:* [.env Environment Template](personal-ai-os-architecture.md#14-environment-variables)

### 3.3 Custom MCP Server Configuration
To allow OpenCode to interface with the Docker network services, edit `~/.config/opencode/config.json`. This maps stdio and HTTP processes to expose database tools, filesystem control, and n8n hooks directly to the LLM console.
*   *Configuration schemas:* [MCP Server Configuration Map](personal-ai-os-architecture.md#131-opencode-config-file)
*   *Custom Python MCP Server:* [Custom PAIOS MCP Implementation Code](personal-ai-os-architecture.md#132-custom-paios-mcp-server--full-implementation)

### 3.4 Database Schemas (Tasks, Memory, Logs)
The PostgreSQL schema uses specialized indices for vector operations:
*   **Table `projects`**: Tracks active development targets.
*   **Table `task_queue`**: Implements atomic claiming of tasks via PostgreSQL's `FOR UPDATE SKIP LOCKED` query.
*   **Table `memory_store`**: Contains the HNSW cosine index `idx_memory_embedding` for semantic searching.
*   **Table `agent_logs` & `workflow_runs`**: Monitors execution traces.
*   *Full SQL source:* [Database DDL Init Script](personal-ai-os-architecture.md#15-database-schema)

### 3.5 Backup, Recovery & Automation Scripts
Operations scripts protect data across both SQL tables and raw Docker volumes:
*   **`backup.sh`**: Runs a compressed database dump, exports active n8n workflow JSON arrays via API, records current Ollama configurations, and commits updates to Git.
*   **`restore.sh`**: Reconstructs database schemas and restores Docker volume states.
*   *Full Bash Code:* [Backup & Restore Scripts](personal-ai-os-architecture.md#19-backup-strategy)

### 3.6 Troubleshooting & Laptop Resource Tuning
*   **Docker RAM Caps**: postgres (1GB limit), redis (512MB limit), n8n (1GB limit) configured in Compose to prevent laptop freezing.
*   **Ollama RAM Alignment**:
    *   **8GB RAM**: Deploy `hermes3:3b` and `nomic-embed-text`.
    *   **16GB RAM**: Deploy `hermes3:8b`.
    *   **32GB+ RAM**: Deploy `hermes3:8b` alongside high-quantized `llama3.1:70b` models.
*   *Troubleshooting guide:* [Troubleshooting & Performance Tuning Guide](personal-ai-os-architecture.md#20-troubleshooting-guide)

---

## 4. 🛣️ Choose Your Pathway: Comparison of Build & Learning Roadmaps

This workspace provides four distinct roads to build and learn the PAIOS ecosystem. Use the matrix below to select your pathway:

| Attribute | 6-Week Project Track | 8-Week Windows Track | Windows Deployment Roadmap | YouTube Learning Roadmap |
| :--- | :--- | :--- | :--- | :--- |
| **Primary Goal** | Project builds & Capstones | Methodical local study | OS environment setup | Self-taught visual study |
| **Pace** | Intensive (3 projects/week) | Medium (1 unit/week) | Progressive Deep-dives | Self-guided browsing |
| **Platform** | Windows + WSL2 + API | Local Windows Native | WSL2 Ubuntu Environment | General OS Setup |
| **Special Focus** | Portfolio & Monetization | Infrastructure & Logic | CLI & Shell config | Video references |
| **Source File** | [6-Week Roadmap](PAIOS_6Week_Project_Roadmap.md) | [8-Week Roadmap](ai_agent_os_8week_roadmap.md) | [Windows Deployment](AI_Agent_OS_Roadmap.md) | [YouTube Roadmap](PAIOS_YouTube_Roadmap.md) |

### 4.1 The 6-Week Project Build Plan
Focuses on creating 18 projects divided into structured weeks, culminating in Capstone deliverables:
*   **Week 1**: Setup infrastructure, Docker network, and OpenCode command console.
*   **Week 2**: Deploy the MCP Server Hub and FastAPI/CrewAI agent interfaces.
*   **Week 3**: Establish pgvector semantic memory databases and the Obsidian AI bridge.
*   **Week 4**: Configure n8n webhook routing and Dockerized OpenHands agents. **[Capstone A: PAIOS MVP]**.
*   **Week 5**: Build Browser agents and sandboxed desktop environments. **[Capstone B: NomadOS]**.
*   **Week 6**: Complete LangGraph supervisors and deploy to production. **[Capstone C: Production System]**.
*   *Details:* [6-Week Project Schedule & Monetization](PAIOS_6Week_Project_Roadmap.md#week-by-week-build-plan)

### 4.2 The 8-Week Windows Study Track
A methodical approach mapping core concepts to weekly study targets:
*   **Week 1–2**: Foundations, WSL2 setup, and first OpenCode terminal agents.
*   **Week 3–4**: Multi-agent orchestration (CrewAI), pgvector schemas, and n8n webhooks.
*   **Week 5–6**: Integrating OpenHands sandbox, computer-use security, and LangGraph states.
*   **Week 7–8**: Monitoring instrumentation, Loki logs, security hardening, and final Capstones.
*   *Details:* [8-Week Step-by-Step Study Guide](ai_agent_os_8week_roadmap.md#21-8-week-study-plan)

### 4.3 Windows Deployment Roadmap (19 Deep-Dive Sections)
Provides a structured learning pathway containing prerequisites, official documentation links, learning outcomes, and mini-projects across 19 separate architectural domains (from Docker networking to browser virtualization).
*   *Details:* [Windows Deployment Sections](AI_Agent_OS_Roadmap.md#chronological-learning-path)

### 4.4 YouTube-Only Learning Path
A curated guide listing specific free tutorial videos, playlists, and channels for students who prefer video learning.
*   *Details:* [YouTube Video & Playlist Catalog](PAIOS_YouTube_Roadmap.md#section-01--foundation)

---

## 5. 🆓 Free AI Models Landscape (2026)

This workspace details how to build a high-performance developer workspace utilizing free cloud APIs and chat interfaces.

### 5.1 Provider Deep Dives & Free Tier Limits
In 2026, 14 major providers offer substantial free-tier developer keys:
1.  **Google AI Studio**: Gemini 1.5 Pro (2M context, 2 RPM), Gemini 1.5 Flash (1M context, 15 RPM).
2.  **Groq**: Llama 4 / Llama 3 models hosted on LPU hardware (14,400 tokens/min limit).
3.  **Cerebras**: Fast inference hosting for Llama 3.1 8B/70B (free tiers capping at 1M tokens/day).
4.  **DeepSeek**: Direct API access or free inference routing for V3 and R1 reasoning engines.
5.  **GitHub Models**: Free developer access to GPT-4o, Claude 3.5 Sonnet, and Qwen 2.5 Coder.
6.  **Cloudflare Workers AI**: Capped daily free allocation of small llama/Qwen models.
7.  *Other Providers detailed:* Mistral AI, Alibaba (Qwen), xAI (Grok), OpenAI, Anthropic, NVIDIA NIM, OpenRouter, Hugging Face, and Cohere.
*   *Full provider comparison:* [Provider Overviews & Limits](free-cloud-ai-models-2026.md#provider-overviews)

### 5.2 Capability Rankings (Coding, Reasoning, Speed, Context)
*   **Best for Coding**: DeepSeek-R1, Qwen 2.5 Coder (via OpenRouter/GitHub), Gemini 2.0 Flash.
*   **Best for Reasoning**: DeepSeek-R1, Gemini 1.5 Pro, Llama 3.1 70B (Instruct).
*   **Fastest Latency**: Cerebras (450+ TPS for 8B models), Groq (250+ TPS for 70B models).
*   **Longest Context**: Gemini 1.5 Pro (2,000,000 token window), Gemini 1.5 Flash (1,000,000 tokens).
*   *Full rankings data:* [Cross-Provider Category Rankings](free-ai-models-comprehensive-2026.md#4-cross-provider-rankings-by-category)

### 5.3 Zero-Cost Inference Stacks
To bypass API rate limits, developers can "stack" multiple free APIs. Below are the recommended stacking structures:
*   **Developer Stack (High Volume)**: Use Cerebras for fast coding completions → route large files to Google AI Studio for long-context analysis → use Groq for quick JSON validation.
*   **AI Agent Stack**: Use GitHub Models (Claude 3.5 Sonnet) for orchestrator reasoning → offload subtasks to Groq Llama 3.1 70B → run local Gemma 2 9B (Ollama) for routine tasks.
*   **Research & Reasoning Stack**: Combine DeepSeek-R1 (via OpenRouter free keys) for mathematical/logic steps with Gemini 1.5 Pro for literature indexing.
*   *Stack configuration files:* [Stacking Free Tiers Blueprint](free-ai-models-comprehensive-2026.md#8-stacking-free-tiers-the-zero-cost-inference-stack)

### 5.4 Privacy, Data Handling & API Compatibility
Ensure you conform to privacy standards:
*   **Data Storing policies**: Avoid sending sensitive keys to public chat interfaces. Use developer endpoints (like Google AI Studio or Groq Cloud) which explicitly do not use data payload inputs to retrain base models.
*   **OpenAI Compatibility**: Most API hosts (Cerebras, Groq, OpenRouter) expose endpoints fully compatible with `openai.openai_client` parameters, allowing seamless switching.
*   *Detail file:* [Privacy & Data Guidelines](free-ai-models-comprehensive-2026.md#7-privacy--data-handling)

---

## 6. 🧰 The Complete AI OS Toolkit & Reference Stacks

### 6.1 Toolkit Index
The workspace categorizes 20+ specialized tool components for building agentic infrastructure:
*   **Coding Agents**: [Claude Code](AI_OS_Complete_Toolkit_Guide.md#claude-code), [Aider](AI_OS_Complete_Toolkit_Guide.md#aider), [Cline](AI_OS_Complete_Toolkit_Guide.md#cline).
*   **Agent Frameworks**: [LangGraph](AI_OS_Complete_Toolkit_Guide.md#4-ai-frameworks--orchestration), [Pydantic AI](AI_OS_Complete_Toolkit_Guide.md#pydantic-ai).
*   **Vector Databases**: [Qdrant](AI_OS_Complete_Toolkit_Guide.md#8-vector-databases), [pgvector](AI_OS_Complete_Toolkit_Guide.md#pgvector-postgresql-extension).
*   **Observability & Logging**: [Langfuse](AI_OS_Complete_Toolkit_Guide.md#13-observability--monitoring), [Prometheus + Grafana](AI_OS_Complete_Toolkit_Guide.md#13-observability--monitoring).

### 6.2 Recommended Architectures (Stacks A, B, C, D)
*   **Stack A: Personal AI OS (Local Core)**: OpenCode + n8n + pgvector + Ollama (Hermes 8B).
*   **Stack B: RAG Application**: LlamaIndex + Qdrant + FastAPI + Next.js + Gemini Flash.
*   **Stack C: Full-Stack SaaS**: Next.js + Supabase + Tailwind + pgvector + Clerk.
*   **Stack D: Autonomous Agent Mesh**: LangGraph + CrewAI + OpenHands + Langfuse + Claude Sonnet.
*   *Detailed tool lists:* [Toolkit Stacks & Reference Profiles](AI_OS_Complete_Toolkit_Guide.md#18-recommended-tech-stacks)

---

## 7. 🚀 Next Steps & Getting Started

To initialize the Personal AI OS codebase on your machine:
1.  **Clone the workspace** and navigate to this folder.
2.  **Verify prerequisites** (Docker, Python 3.11+, and Node.js) are installed.
3.  **Prepare local environment keys** by copying `.env.example` to `.env` and setting secrets.
4.  **Execute the compose stack**:
    ```bash
    docker compose up -d postgres redis ollama n8n
    ```
5.  **Initialize schemas**:
    ```bash
    docker exec -i ai-os-postgres psql -U ai_os -d ai_os_db < database/init.sql
    ```
6.  **Open OpenCode** and load the config file map to run task commands.

*Complete step-by-step pipeline setup:* [PAIOS Phase-by-Phase Installation Guide](personal-ai-os-architecture.md#17-installation-roadmap)
