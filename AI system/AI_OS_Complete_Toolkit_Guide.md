# 🧠 The Complete AI Operating System Toolkit
## Production-Grade Guide for Autonomous Agents, Full-Stack Apps & AI Systems

> **Built around:** OpenCode · Hermes Agent · n8n · CrewAI · OpenHands · PostgreSQL · GitHub · Docker · Notion  
> **Last Researched:** June 2026 | **Focus:** Free, open-source, self-hostable, laptop-first

---

## Table of Contents

1. [Core Philosophy & Architecture](#1-core-philosophy--architecture)
2. [AI Coding Agents](#2-ai-coding-agents)
3. [MCP Servers](#3-mcp-servers)
4. [AI Frameworks & Orchestration](#4-ai-frameworks--orchestration)
5. [Multi-Agent Systems](#5-multi-agent-systems)
6. [LLM Providers & Local Models](#6-llm-providers--local-models)
7. [RAG & Knowledge Systems](#7-rag--knowledge-systems)
8. [Vector Databases](#8-vector-databases)
9. [Backend Development](#9-backend-development)
10. [Frontend Development](#10-frontend-development)
11. [Databases & Storage](#11-databases--storage)
12. [DevOps & Deployment](#12-devops--deployment)
13. [Observability & Monitoring](#13-observability--monitoring)
14. [Automation & Workflows](#14-automation--workflows)
15. [Authentication & Security](#15-authentication--security)
16. [Testing & Evaluation](#16-testing--evaluation)
17. [Productivity & Project Management](#17-productivity--project-management)
18. [Recommended Tech Stacks](#18-recommended-tech-stacks)
19. [Learning Roadmap](#19-learning-roadmap)
20. [Implementation Priorities](#20-implementation-priorities)

---

## 1. Core Philosophy & Architecture

### The AI OS Vision
You are building a **laptop-first AI operating system** — a unified development environment where AI agents assist, automate, and augment every layer of your workflow. Everything is self-hostable, open-source preferred, and production-ready.

### Architectural Layers

```
┌─────────────────────────────────────────────────────────────┐
│                    INTERFACE LAYER                          │
│         OpenCode (CLI) · Cursor/VS Code · Notion           │
├─────────────────────────────────────────────────────────────┤
│                  AGENT ORCHESTRATION                         │
│         CrewAI · LangGraph · Hermes Agent · n8n            │
├─────────────────────────────────────────────────────────────┤
│               TOOL & CONTEXT LAYER (MCP)                    │
│     GitHub MCP · PostgreSQL MCP · Browser · File System    │
├─────────────────────────────────────────────────────────────┤
│                    MODEL LAYER                               │
│     Claude (Anthropic) · GPT · Gemini · Ollama (local)     │
├─────────────────────────────────────────────────────────────┤
│                  DATA & MEMORY LAYER                         │
│         PostgreSQL · Qdrant · Redis · pgvector             │
├─────────────────────────────────────────────────────────────┤
│              INFRASTRUCTURE LAYER                            │
│              Docker · GitHub Actions · Coolify             │
└─────────────────────────────────────────────────────────────┘
```

### Design Principles
- **Local-first**: Everything runs on your laptop. Cloud is optional.
- **Model-agnostic**: Swap LLMs without rewriting agents.
- **Composable**: Small tools that chain together.
- **Observable**: Every agent action is traced and logged.
- **Reproducible**: Docker + GitHub = instant environment restore.

---

## 2. AI Coding Agents

> The tools that write, edit, debug, and refactor code autonomously.

---

### ⭐ OpenCode
| Field | Details |
|-------|---------|
| **Purpose** | Terminal-native AI coding agent, open-source Claude Code alternative |
| **License** | Open Source (MIT) |
| **GitHub Stars** | 150K+ (fastest growing in 2026) |
| **Learning Priority** | **Beginner** — your primary coding agent |

**Key Features:**
- Supports 75+ AI model providers (BYOK — Bring Your Own Key)
- LSP integration for automatic language server configuration
- Multi-session parallel agents on same project
- Terminal UI + desktop app + VS Code extension
- Session sharing via links
- GitHub Copilot subscriber authentication (no extra license since Jan 2026)
- Real-time cost monitoring

**Unique Advantages:**
- The only open-source tool matching Claude Code's feature set while being model-agnostic
- 150K+ GitHub stars, 6.5M+ monthly active developers
- Works offline with Ollama local models at zero API cost

**Use Cases:** Daily coding, refactoring, feature building, debugging, multi-file edits

**Alternatives:** Claude Code (Anthropic official, 87.6% SWE-bench), Aider (git-native), Cline (VS Code), Cursor (IDE)

---

### Claude Code
| Field | Details |
|-------|---------|
| **Purpose** | Anthropic's official agentic coding CLI |
| **Cost** | $20/month Pro or API usage |
| **Learning Priority** | **Beginner** — best reasoning quality |

**Key Features:**
- Highest SWE-bench score (87.6% with Opus 4.7)
- Auto mode for fully autonomous tasks
- Agent View for multi-step planning
- Native binary, fast startup
- Best for large codebase reasoning

**Use Cases:** Complex refactors, long-horizon tasks, production bug fixing

---

### Aider
| Field | Details |
|-------|---------|
| **Purpose** | Git-native AI coding assistant, terminal-based |
| **License** | Apache 2.0 |
| **GitHub Stars** | 44K+ |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Works with Claude, GPT, Gemini, Llama, DeepSeek, 20+ models
- Auto-commits changes with meaningful git messages
- Works inside any editor
- 6.6M+ installs

**Use Cases:** Quick code changes, model-agnostic workflows, git-tracked AI edits

---

### OpenHands (formerly OpenDevin)
| Field | Details |
|-------|---------|
| **Purpose** | Fully autonomous coding agent with Docker isolation |
| **License** | MIT |
| **Learning Priority** | **Intermediate** — for delegating feature-sized tasks |

**Key Features:**
- Docker runtime for isolated execution
- Can write code, run tests, browse web, call APIs
- Designed for feature delegation, not just line edits
- Self-hostable web UI

**Use Cases:** Building entire features autonomously, CI/CD agent tasks, complex multi-step coding

**Alternatives:** Goose (Block), SWE-agent (Princeton)

---

### Cline
| Field | Details |
|-------|---------|
| **Purpose** | VS Code AI coding agent with Plan/Act oversight |
| **License** | Apache 2.0 |
| **Learning Priority** | **Beginner** — best for VS Code users |

**Key Features:**
- Plan/Act mode: AI plans first, executes with your approval
- MCP marketplace built-in
- File, terminal, browser, and MCP access
- Works with Ollama for private/offline use
- Real-time cost monitoring

**Use Cases:** IDE-first development, controlled agent execution, MCP-powered workflows

---

## 3. MCP Servers

> Model Context Protocol — the "USB standard" for AI tools. Connect agents to any data source or service.

---

### Core Concept
MCP servers translate real-world systems into a format AI agents can act on. One standard, infinite integrations.

---

### ⭐ GitHub MCP Server
| Field | Details |
|-------|---------|
| **Purpose** | Full GitHub access for AI agents |
| **Provider** | Official GitHub/Anthropic |
| **Priority** | **Must-Have** |

**Features:** Repository management, PR creation/review, issue tracking, code search, Actions integration

**Use Cases:** Automated PR reviews, issue triage, codebase analysis

---

### ⭐ PostgreSQL MCP Server
| Field | Details |
|-------|---------|
| **Purpose** | Database access and queries for agents |
| **Priority** | **Must-Have** |

**Features:** Schema inspection, SQL query execution, data analysis, safe read/write operations

**Use Cases:** AI-driven data analysis, schema migration assistance, query optimization

---

### ⭐ Filesystem MCP Server
| Field | Details |
|-------|---------|
| **Purpose** | Local file system access |
| **Priority** | **Must-Have** |

**Features:** Read/write files, directory traversal, file search

---

### Browser/Playwright MCP Server
| Field | Details |
|-------|---------|
| **Purpose** | Web browsing and scraping |
| **Priority** | **High** |

**Features:** Browser automation, form filling, screenshot, web scraping

**Alternatives:** Puppeteer MCP, browser-control-mcp (Firefox extension)

---

### Chroma MCP / Qdrant MCP
| Field | Details |
|-------|---------|
| **Purpose** | Vector database access for RAG agents |
| **Priority** | **High** |

**Features:** Semantic search, embedding retrieval, knowledge base queries

---

### n8n MCP Server
| Field | Details |
|-------|---------|
| **Purpose** | Trigger and manage n8n workflows from AI agents |
| **Priority** | **High** — core integration |

**Features:** Workflow triggering, status monitoring, data passing between agents and automations

---

### Notion MCP Server
| Field | Details |
|-------|---------|
| **Purpose** | Read/write Notion databases and pages |
| **Priority** | **High** — project management integration |

**Features:** Page creation, database queries, task management via AI

---

### Slack / Discord MCP
| Field | Details |
|-------|---------|
| **Purpose** | Team communication integration |
| **Priority** | **Medium** |

---

### Docker MCP
| Field | Details |
|-------|---------|
| **Purpose** | Container management from AI agents |
| **Priority** | **Medium** |

**Features:** Container start/stop, log inspection, image management

---

### YouTube Transcript MCP
| Field | Details |
|-------|---------|
| **Purpose** | Extract video transcripts for AI analysis |
| **Priority** | **Low-Medium** |

---

### dbt Semantic Layer MCP
| Field | Details |
|-------|---------|
| **Purpose** | Data modeling and analytics access |
| **Priority** | **Advanced** |

---

### Building Custom MCP Servers
Use official SDKs: `@modelcontextprotocol/sdk` (TypeScript), `mcp` (Python). Any REST API can become an MCP server in ~50 lines of code.

---

## 4. AI Frameworks & Orchestration

> The scaffolding that turns single LLM calls into complex, stateful applications.

---

### ⭐ LangChain
| Field | Details |
|-------|---------|
| **Purpose** | Foundation framework for LLM applications |
| **License** | MIT |
| **GitHub Stars** | 85K+ |
| **Learning Priority** | **Beginner** — learn this first |

**Key Features:**
- Integrations with all major LLM providers
- Document loaders (PDF, CSV, web, Notion)
- Support for all major vector databases
- Chains, agents, tools ecosystem
- LangSmith integration for observability

**Use Cases:** RAG pipelines, chatbots, document QA, tool-using agents

---

### ⭐ LangGraph
| Field | Details |
|-------|---------|
| **Purpose** | Graph-based stateful agent workflows |
| **License** | MIT (LangChain ecosystem) |
| **Learning Priority** | **Intermediate** — best for production agents |

**Key Features:**
- State machine with nodes, edges, conditional routing
- Durable execution — agents resume after failures
- Human-in-the-loop support
- Checkpointing and persistence
- PostgresSaver for database-backed state
- Both Python and JavaScript

**Unique Advantages:**
- Reached v1.0 in late 2025; production-hardened
- 27,100 monthly searches (highest of any framework)
- Best for branching business logic and fault-tolerant workflows

**Use Cases:** Production agents, multi-step reasoning, approvals workflows, long-running jobs

---

### LlamaIndex
| Field | Details |
|-------|---------|
| **Purpose** | RAG-first framework for enterprise data |
| **License** | MIT |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Best-in-class document parsing and indexing
- Works with Qdrant, Weaviate, Pinecone, MongoDB
- Agent capabilities over structured/unstructured data
- Multi-modal support

**Use Cases:** Document intelligence, enterprise RAG, data analysis agents

---

### Haystack (deepset)
| Field | Details |
|-------|---------|
| **Purpose** | Production RAG with built-in evaluation |
| **License** | Apache 2.0 |
| **Learning Priority** | **Advanced** |

**Key Features:**
- Built-in pipeline evaluation and monitoring
- REST API deployment ready
- Modular pipeline design

---

### Anthropic Claude Agent SDK
| Field | Details |
|-------|---------|
| **Purpose** | Official Anthropic SDK for Claude-native agents |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Native tool use and memory APIs
- Passed AutoGen in enterprise deployment count (Q1–Q2 2026)
- Memory, tool use, computer use built-in

---

### Pydantic AI
| Field | Details |
|-------|---------|
| **Purpose** | Type-safe agent framework from Pydantic team |
| **Learning Priority** | **Intermediate** — emerging best practice |

**Key Features:**
- Full type safety from model to response
- Structured outputs by default
- Clean, minimal API design

---

## 5. Multi-Agent Systems

> Orchestrate teams of specialized AI agents working together.

---

### ⭐ CrewAI
| Field | Details |
|-------|---------|
| **Purpose** | Role-based multi-agent collaboration |
| **License** | MIT (core) |
| **Learning Priority** | **Beginner** — your primary multi-agent framework |

**Key Features:**
- Define agents with roles, goals, backstories
- Sequential and parallel task execution
- Built-in tool routing for Claude/GPT/Gemini
- Async crew runner (experimental)
- A2A (Agent-to-Agent) protocol support growing

**Unique Advantages:**
- Fastest multi-agent setup (minutes to a working crew)
- Intuitive mental model — roles map to team structure
- 14,800 monthly searches

**Use Cases:** Research agents, content pipelines, automated workflows with multiple specialists

**Alternatives:** AutoGen (conversational), LangGraph (stateful), OpenAI Agents SDK

---

### Microsoft AutoGen / AG2
| Field | Details |
|-------|---------|
| **Purpose** | Conversational multi-agent problem solving |
| **License** | Apache 2.0 (AG2 community fork) / CC-BY-4.0 |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- GroupChat: agents debate and collaborate
- No-code AutoGen Studio
- .NET support for enterprise
- Best for deliberation and brainstorming workflows

**Note:** AutoGen split in 2025 — Microsoft maintains v0.4+ rewrite; community continues as AG2. Pick deliberately.

**Use Cases:** Code generation with review, debate-based reasoning, quality-sensitive offline workflows

---

### Google ADK (Agent Development Kit)
| Field | Details |
|-------|---------|
| **Purpose** | Hierarchical agent trees with A2A protocol |
| **Learning Priority** | **Advanced** |

**Key Features:**
- Root agent delegates to sub-agents recursively
- Native A2A protocol for cross-framework communication
- Integrates with Vertex AI and Gemini
- Can call LangGraph or CrewAI agents via A2A

---

### OpenAI Agents SDK
| Field | Details |
|-------|---------|
| **Purpose** | Production agent framework from OpenAI |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Handoffs: explicit agent-to-agent control transfer
- First-party tools (code interpreter, web search)
- Production-grade since March 2025

---

### MetaGPT
| Field | Details |
|-------|---------|
| **Purpose** | Software development automation via agent teams |
| **License** | Apache 2.0 |
| **Learning Priority** | **Advanced** |

**Key Features:**
- Simulates software engineering team (PM, architect, engineer, QA)
- Generates PRDs, architecture docs, and code
- Best for greenfield projects

---

## 6. LLM Providers & Local Models

---

### Cloud LLM Providers

| Provider | Best Model | Strength | Pricing |
|----------|-----------|----------|---------|
| **Anthropic** | Claude Opus 4.7 (87.6% SWE-bench) | Reasoning, coding, agents | Pay-per-token |
| **OpenAI** | GPT-5.5 / o3 | General purpose, speed | Pay-per-token |
| **Google** | Gemini 2.5 Pro | Multimodal, long context | Pay-per-token |
| **DeepSeek** | DeepSeek-V3 / R1 | Cost-effective, strong reasoning | Very cheap |
| **Groq** | Llama 3.1 70B | Ultra-fast inference | Free tier |
| **Together AI** | Multiple open models | BYOM hosting | Affordable |

---

### ⭐ Ollama (Local Models)
| Field | Details |
|-------|---------|
| **Purpose** | Run open-source LLMs locally on your laptop |
| **License** | MIT |
| **Learning Priority** | **Beginner** — install immediately |

**Key Features:**
- One command to pull and run models: `ollama pull llama3.1`
- REST API compatible with OpenAI format
- Runs Llama, Qwen, DeepSeek, Mistral, Phi locally
- Zero API cost after download
- Works offline

**Recommended Models:**
- `llama3.1:8b` — fast, fits 8GB RAM
- `qwen2.5-coder:7b` — best local coding model
- `deepseek-r1:7b` — local reasoning
- `nomic-embed-text` — local embeddings

**Use Cases:** Private/offline work, cost-free prototyping, embedding generation

---

### LiteLLM
| Field | Details |
|-------|---------|
| **Purpose** | Universal LLM gateway — one API for 100+ providers |
| **License** | MIT |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Single OpenAI-compatible API endpoint
- Automatic failover between providers
- Cost tracking and rate limiting
- Self-hostable proxy

**Use Cases:** Model routing, cost optimization, provider abstraction

---

## 7. RAG & Knowledge Systems

> Give your agents long-term memory and domain knowledge.

---

### RAG Architecture

```
Documents → Chunking → Embedding → Vector Store
                                        ↓
User Query → Embedding → Similarity Search → Retrieved Chunks
                                                    ↓
                                     LLM + Context → Answer
```

---

### ⭐ LangChain RAG Pipeline
**Learning Priority: Beginner**

The standard starting point. Combines document loaders, text splitters, embeddings, vector stores, and retrieval chains.

```python
# Quick RAG in LangChain
from langchain.document_loaders import DirectoryLoader
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain_community.vectorstores import Qdrant
from langchain.chains import RetrievalQA
```

---

### LlamaIndex
**Learning Priority: Intermediate**

Better for complex document types (PDFs with tables, code, structured data). Superior parsing.

---

### Chroma
| Field | Details |
|-------|---------|
| **Purpose** | Local-first vector database for development |
| **License** | Apache 2.0 |
| **Learning Priority** | **Beginner** — use for prototyping |

**Key Features:**
- Zero setup, runs in-process or as server
- Python and JavaScript clients
- Persistent storage on disk

**Use Cases:** Local RAG prototyping, small knowledge bases

---

### Unstructured.io
| Field | Details |
|-------|---------|
| **Purpose** | Document parsing pipeline (PDF, DOCX, HTML, etc.) |
| **License** | Apache 2.0 (open source tier) |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Handles messy real-world documents
- Table extraction, image captioning
- Chunking strategies built-in

---

### DSPy
| Field | Details |
|-------|---------|
| **Purpose** | Programmatic prompt optimization framework |
| **License** | MIT |
| **Learning Priority** | **Advanced** |

**Key Features:**
- Automatically optimizes prompts via compilation
- Replaces manual prompt engineering
- Works with any LLM

---

## 8. Vector Databases

---

### ⭐ Qdrant
| Field | Details |
|-------|---------|
| **Purpose** | High-performance vector database, self-hostable |
| **License** | Apache 2.0 |
| **Learning Priority** | **Intermediate** — your primary vector DB |

**Key Features:**
- Built in Rust — blazing fast (8ms p50 at 1M vectors)
- Best filtered vector search in the market
- Payload filtering: combine similarity + metadata conditions
- Self-host free, or Qdrant Cloud (1GB free tier)
- Docker deployment in one command

**Unique Advantages:**
- Highest RPS and lowest latency in third-party benchmarks
- Full data ownership when self-hosted
- Apache 2.0 license — truly free

**Use Cases:** Production RAG, semantic search, AI memory systems

**Command:** `docker run -p 6333:6333 qdrant/qdrant`

---

### pgvector (PostgreSQL Extension)
| Field | Details |
|-------|---------|
| **Purpose** | Vector search inside PostgreSQL |
| **License** | PostgreSQL License |
| **Learning Priority** | **Beginner** — simplest if you already use Postgres |

**Key Features:**
- No new database to manage
- Combines relational + vector queries
- Works with all PostgreSQL tools

**Use Cases:** Simple RAG, apps already on PostgreSQL, unified data layer

---

### Weaviate
| Field | Details |
|-------|---------|
| **Purpose** | AI-native vector database with hybrid search |
| **License** | BSD-3-Clause |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Hybrid search: vector similarity + BM25 keyword
- GraphQL API for complex queries
- Multi-modal data handling
- Agent Skills for agentic AI (Feb 2026)
- SOC 2 / HIPAA compliant

**Use Cases:** Enterprise RAG, multi-modal search, regulated industries

---

### Milvus
| Field | Details |
|-------|---------|
| **Purpose** | Open-source vector database at scale |
| **License** | Apache 2.0 |
| **Learning Priority** | **Advanced** |

**Key Features:**
- Built for billions of vectors
- Kubernetes-native
- Multiple index types (HNSW, IVF, etc.)

---

### Pinecone
| Field | Details |
|-------|---------|
| **Purpose** | Fully managed serverless vector database |
| **Learning Priority** | **Intermediate** — if you want zero ops |

**Pricing:** Starter free; Standard ~$50/month

**Note:** Managed only — no self-hosting option.

---

## 9. Backend Development

---

### ⭐ FastAPI
| Field | Details |
|-------|---------|
| **Purpose** | High-performance Python API framework |
| **License** | MIT |
| **Learning Priority** | **Beginner** — your primary backend |

**Key Features:**
- Automatic OpenAPI/Swagger documentation
- Native async support (asyncio)
- Type safety via Pydantic
- 38-40% Python web dev adoption (2025-2026)
- Fastest growing Python framework

**Unique Advantages:**
- Perfect pairing with AI/ML Python ecosystem
- Auto-validation of LLM structured outputs
- 1-line integration with LangChain, CrewAI

**Use Cases:** AI API endpoints, agent backends, microservices

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

@app.post("/agent/run")
async def run_agent(prompt: str):
    result = await my_agent.run(prompt)
    return {"result": result}
```

---

### Node.js / Express / Hono
| Field | Details |
|-------|---------|
| **Purpose** | JavaScript/TypeScript backend runtime |
| **Learning Priority** | **Beginner** |

**Hono** — ultra-fast, edge-compatible. Prefer over Express for new projects.
**NestJS** — opinionated, enterprise-grade TypeScript framework.

---

### Supabase
| Field | Details |
|-------|---------|
| **Purpose** | Open-source Firebase alternative — BaaS |
| **License** | Apache 2.0 |
| **Learning Priority** | **Beginner** — backend-as-a-service |

**Key Features:**
- PostgreSQL database with auto-generated REST APIs
- Authentication (email, OAuth, phone)
- Row-Level Security (RLS) policies
- Real-time subscriptions
- Edge Functions (serverless)
- File storage
- TypeScript type generation from schema

**Unique Advantages:**
- No backend server needed for many apps
- Built on standard PostgreSQL — no vendor lock-in
- Self-hostable via Docker

**Use Cases:** Full-stack apps, SaaS, auth layer, rapid prototyping

**Self-host:** `docker compose up supabase`

---

### Redis
| Field | Details |
|-------|---------|
| **Purpose** | In-memory cache, session store, message broker |
| **License** | Redis Source Available (SSPL) / Valkey (BSD) |
| **Learning Priority** | **Intermediate** |

**Use Cases:** Agent session caching, rate limiting, pub/sub for workflows, LLM response caching

**Alternative:** Valkey (BSD-3, community Redis fork)

---

## 10. Frontend Development

---

### ⭐ Next.js
| Field | Details |
|-------|---------|
| **Purpose** | React framework for full-stack web applications |
| **License** | MIT |
| **Learning Priority** | **Beginner** — your primary frontend framework |

**Key Features:**
- Server-side rendering (SSR) + static generation (SSG)
- React Server Components
- API routes built-in
- Vercel deployment in one click
- App Router (v13+) for modern patterns

**Use Cases:** SaaS frontends, AI chat UIs, dashboards, marketing sites

---

### Tailwind CSS
| Field | Details |
|-------|---------|
| **Purpose** | Utility-first CSS framework |
| **License** | MIT |
| **Learning Priority** | **Beginner** — use with every project |

**Key Features:**
- No CSS file maintenance
- Responsive design utilities built-in
- Pairs perfectly with shadcn/ui

---

### shadcn/ui
| Field | Details |
|-------|---------|
| **Purpose** | Copy-paste React component library |
| **License** | MIT |
| **Learning Priority** | **Beginner** |

**Key Features:**
- Components you own (not a package)
- Built on Radix UI primitives
- Tailwind-based styling
- AI-assistant friendly (generates great shadcn code)

---

### React / TypeScript
| Field | Details |
|-------|---------|
| **Purpose** | UI component library + type safety |
| **Learning Priority** | **Beginner** |

Standard foundation for all modern web UIs. Always use TypeScript.

---

### Vercel
| Field | Details |
|-------|---------|
| **Purpose** | Frontend deployment platform |
| **Learning Priority** | **Beginner** |

**Key Features:** Zero-config Next.js deployment, edge functions, analytics, preview deployments

**Free tier:** Generous for personal projects.

---

## 11. Databases & Storage

---

### ⭐ PostgreSQL
| Field | Details |
|-------|---------|
| **Purpose** | Primary relational database |
| **License** | PostgreSQL License (fully open source) |
| **Learning Priority** | **Beginner** — use for everything |

**Key Features:**
- ACID compliant, battle-tested at scale
- JSON/JSONB support for semi-structured data
- pgvector extension for vector search
- Full-text search built-in
- Row-Level Security
- Rich ecosystem (Prisma, SQLAlchemy, Drizzle)

**Extensions to install:**
- `pgvector` — vector similarity search
- `pg_cron` — scheduled jobs
- `pg_stat_statements` — query performance

---

### SQLite
| Field | Details |
|-------|---------|
| **Purpose** | Zero-config embedded database |
| **License** | Public Domain |
| **Learning Priority** | **Beginner** |

**Use Cases:** Local development, prototyping, small apps, agent memory stores

---

### Prisma ORM
| Field | Details |
|-------|---------|
| **Purpose** | Type-safe database ORM for TypeScript |
| **License** | Apache 2.0 |
| **Learning Priority** | **Beginner** |

**Use Cases:** Next.js + PostgreSQL, type-safe queries, schema migrations

---

### SQLAlchemy / SQLModel
| Field | Details |
|-------|---------|
| **Purpose** | Python ORM for FastAPI + PostgreSQL |
| **License** | MIT |
| **Learning Priority** | **Beginner** |

**SQLModel** = SQLAlchemy + Pydantic, built by FastAPI creator.

---

### MinIO
| Field | Details |
|-------|---------|
| **Purpose** | Self-hosted S3-compatible object storage |
| **License** | AGPL-3.0 |
| **Learning Priority** | **Intermediate** |

**Use Cases:** File uploads, model artifacts, RAG document storage, backups

---

## 12. DevOps & Deployment

---

### ⭐ Docker & Docker Compose
| Field | Details |
|-------|---------|
| **Purpose** | Container runtime and multi-service orchestration |
| **License** | Apache 2.0 (Compose) |
| **Learning Priority** | **Beginner** — use from day one |

**Key Features:**
- Reproducible environments
- `docker-compose.yml` for your entire stack
- Volume mounts for data persistence
- Networks for service isolation

**Recommended `docker-compose.yml` services:**
```yaml
services:
  postgres:
    image: pgvector/pgvector:pg16
    ports: ["5432:5432"]
  qdrant:
    image: qdrant/qdrant
    ports: ["6333:6333"]
  redis:
    image: redis:alpine
    ports: ["6379:6379"]
  n8n:
    image: n8nio/n8n
    ports: ["5678:5678"]
  ollama:
    image: ollama/ollama
    ports: ["11434:11434"]
```

---

### GitHub Actions
| Field | Details |
|-------|---------|
| **Purpose** | CI/CD pipeline automation |
| **Learning Priority** | **Beginner** |

**Key Features:**
- Free for public repos (2000 min/month private)
- Matrix builds, artifact caching
- OpenCode/Claude Code integration for PR reviews
- Docker build and push automation

**Core workflows to build:**
1. Test on PR → merge on pass
2. Build Docker image → push to registry
3. Deploy on merge to main
4. AI code review on PR

---

### Coolify
| Field | Details |
|-------|---------|
| **Purpose** | Self-hosted Heroku/Vercel alternative |
| **License** | Apache 2.0 |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- Deploy any Docker app from GitHub
- Free on your own VPS
- SSL, domains, environment variables managed
- Supports Next.js, FastAPI, n8n, Supabase

**Use Cases:** Self-hosted deployment platform on a $5-10/month VPS

---

### Kubernetes (k3s / k0s)
| Field | Details |
|-------|---------|
| **Purpose** | Container orchestration at scale |
| **Learning Priority** | **Advanced** |

**k3s** — lightweight Kubernetes for single servers and edge.

**When to use:** After you outgrow Docker Compose.

---

### Terraform / OpenTofu
| Field | Details |
|-------|---------|
| **Purpose** | Infrastructure-as-code |
| **License** | MPL-2.0 (Terraform) / MPL-2.0 (OpenTofu, open fork) |
| **Learning Priority** | **Advanced** |

**OpenTofu** is the fully open-source Terraform fork maintained by the Linux Foundation.

---

## 13. Observability & Monitoring

---

### ⭐ Langfuse
| Field | Details |
|-------|---------|
| **Purpose** | LLM tracing, prompt management, evaluation |
| **License** | MIT |
| **Learning Priority** | **Intermediate** — your primary AI observability tool |

**Key Features:**
- Full request/response tracing for LLM calls
- Prompt versioning and management
- Multi-turn conversation tracking
- Self-hosted (free) or cloud ($59/month Pro)
- Acquired by ClickHouse (Jan 2026) — infrastructure now more robust
- Works with LangChain, LlamaIndex, OpenAI, Anthropic

**Use Cases:** Debug agent failures, track costs, monitor quality regressions

**Self-host:** Docker Compose available on GitHub

---

### LangSmith
| Field | Details |
|-------|---------|
| **Purpose** | LangChain-native tracing and evaluation |
| **Learning Priority** | **Intermediate** |

**Best for:** Teams using LangChain/LangGraph. Native graph visualization.

**Note:** Commercial SaaS, no self-hosting.

---

### Arize Phoenix
| Field | Details |
|-------|---------|
| **Purpose** | OpenTelemetry-native AI observability |
| **License** | ELv2 |
| **Learning Priority** | **Advanced** |

**Key Features:**
- OTel-native — integrates with existing APM
- Strong open-source eval metrics library
- Best self-hosted alternative to Langfuse

---

### Helicone
| Field | Details |
|-------|---------|
| **Purpose** | LLM gateway with cost tracking |
| **License** | Apache 2.0 |
| **Learning Priority** | **Beginner** — fastest to add |

**Key Features:**
- One-line proxy integration
- Multi-provider cost visibility
- Caching to reduce spend
- Response replay

---

### Grafana + Prometheus
| Field | Details |
|-------|---------|
| **Purpose** | General-purpose metrics and dashboards |
| **License** | AGPL-3.0 (Grafana) / Apache 2.0 (Prometheus) |
| **Learning Priority** | **Intermediate** |

**Use Cases:** System metrics (CPU, memory, latency), custom dashboards, alerts

---

### Sentry
| Field | Details |
|-------|---------|
| **Purpose** | Application error tracking |
| **Learning Priority** | **Beginner** |

**Use Cases:** Catch runtime errors in FastAPI, Next.js, agent code

---

## 14. Automation & Workflows

---

### ⭐ n8n
| Field | Details |
|-------|---------|
| **Purpose** | Visual workflow automation with 1,400+ integrations |
| **License** | Source-available (free self-hosted) |
| **Learning Priority** | **Beginner** — your primary automation layer |

**Key Features:**
- Visual node canvas for building workflows
- 1,400+ integrations (Slack, GitHub, Gmail, Notion, Airtable, etc.)
- LLM nodes: OpenAI, Anthropic, Google, Ollama
- AI agent nodes — build agents visually
- Webhook triggers, cron jobs, event triggers
- Self-hosted on a $5 VPS = unlimited executions

**Cost advantage:** n8n Cloud Pro = €60/month for 30K executions. Self-hosted = $5/month, unlimited.

**How it works with your AI OS:**
- n8n handles SaaS plumbing and data routing
- Hermes Agent handles AI reasoning steps
- CrewAI agents can be triggered via n8n webhooks

**Use Cases:** Lead processing, report generation, code review pipelines, notification systems, data ETL

---

### ⭐ Hermes Agent
| Field | Details |
|-------|---------|
| **Purpose** | Memory-backed AI agent for judgment-heavy tasks |
| **License** | MIT |
| **Learning Priority** | **Intermediate** — pairs with n8n |

**Key Features:**
- Memory persistence across runs
- Designed for research, analysis, report generation
- Minimal dependencies — easy self-host via Docker
- Webhook and cron job support
- Security via network isolation + API auth

**When to use vs n8n:**
- Use **n8n** when: every step is predefined ("when X, do Y, then Z")
- Use **Hermes** when: the task requires judgment, research, or memory

**Use Cases:** Competitor monitoring, support ticket analysis, monthly data reports, strategic research

---

### Zapier / Make.com
| Field | Details |
|-------|---------|
| **Purpose** | Commercial automation platforms |
| **Learning Priority** | **Beginner** (use n8n instead for self-hosted) |

**When to use:** Quick integrations without self-hosting overhead.

---

### Temporal
| Field | Details |
|-------|---------|
| **Purpose** | Durable workflow execution engine |
| **License** | MIT |
| **Learning Priority** | **Advanced** |

**Use Cases:** Long-running agent tasks, retry logic, workflow versioning at scale

---

## 15. Authentication & Security

---

### ⭐ Supabase Auth
| Field | Details |
|-------|---------|
| **Purpose** | Authentication built into your database |
| **Learning Priority** | **Beginner** — use if already on Supabase |

**Key Features:**
- Email/password, OAuth (Google, GitHub), magic links
- Row-Level Security (RLS) on every table
- JWT tokens

---

### Clerk
| Field | Details |
|-------|---------|
| **Purpose** | Authentication-as-a-service for Next.js |
| **Learning Priority** | **Beginner** |

**Key Features:**
- Best developer experience for Next.js
- Pre-built UI components
- Middleware integration
- Free tier generous

**Use Cases:** SaaS apps, quick auth setup

---

### Auth.js (NextAuth)
| Field | Details |
|-------|---------|
| **Purpose** | Open-source auth for Next.js |
| **License** | ISC |
| **Learning Priority** | **Intermediate** |

**Use Cases:** Self-hosted auth with multiple providers

---

### Keycloak
| Field | Details |
|-------|---------|
| **Purpose** | Enterprise SSO and identity management |
| **License** | Apache 2.0 |
| **Learning Priority** | **Advanced** |

**Use Cases:** SAML/OIDC for enterprise clients, multi-tenant SaaS

---

### Vault (HashiCorp) / Infisical
| Field | Details |
|-------|---------|
| **Purpose** | Secrets management |
| **License** | BSL 1.1 (Vault) / MIT (Infisical) |
| **Learning Priority** | **Intermediate** |

**Infisical** — open-source, self-hostable. Preferred for teams.

---

### OWASP Best Practices (Key Points)
- Never hardcode API keys — use `.env` + Infisical
- Rate limit all LLM endpoints
- Validate and sanitize all agent tool inputs
- Use RLS in PostgreSQL
- Scan Docker images with Trivy

---

## 16. Testing & Evaluation

---

### ⭐ Pytest
| Field | Details |
|-------|---------|
| **Purpose** | Python testing framework |
| **License** | MIT |
| **Learning Priority** | **Beginner** — test everything |

**Use Cases:** FastAPI endpoints, agent functions, RAG pipeline quality

---

### DeepEval
| Field | Details |
|-------|---------|
| **Purpose** | LLM evaluation framework |
| **License** | Apache 2.0 |
| **Learning Priority** | **Intermediate** |

**Key Features:**
- 14+ evaluation metrics (faithfulness, relevancy, hallucination, toxicity)
- RAG-specific evaluators (context precision, recall)
- CI/CD integration
- Self-hosted evaluations

---

### RAGAS
| Field | Details |
|-------|---------|
| **Purpose** | RAG pipeline evaluation |
| **License** | Apache 2.0 |
| **Learning Priority** | **Intermediate** |

**Metrics:** Faithfulness, answer relevancy, context recall, context precision

---

### Playwright / Cypress
| Field | Details |
|-------|---------|
| **Purpose** | End-to-end browser testing |
| **Learning Priority** | **Intermediate** |

**Playwright** — Microsoft, cross-browser, Python + JS. Preferred.

---

### Jest / Vitest
| Field | Details |
|-------|---------|
| **Purpose** | JavaScript unit testing |
| **Learning Priority** | **Beginner** |

**Vitest** — faster, Vite-native. Preferred for new projects.

---

### Braintrust
| Field | Details |
|-------|---------|
| **Purpose** | Eval-driven development with CI/CD gates |
| **Learning Priority** | **Advanced** |

**Free tier:** 1M spans/month, 10K evals

---

## 17. Productivity & Project Management

---

### ⭐ Notion
| Field | Details |
|-------|---------|
| **Purpose** | Knowledge base, project management, AI workspace |
| **Learning Priority** | **Beginner** — your primary project hub |

**AI OS Integration:**
- Notion MCP server → AI agents read/write to Notion
- Store agent prompts, system designs, roadmaps
- Link GitHub issues to Notion tasks
- Auto-generate project docs via n8n + LLM

**Recommended Setup:**
- `Projects` database (linked to GitHub repos)
- `Prompts Library` (system prompts for agents)
- `Agent Runbooks` (how to operate each agent)
- `Decision Log` (architecture decisions)

---

### GitHub (Issues, Projects, Wiki)
| Field | Details |
|-------|---------|
| **Purpose** | Code, issues, CI/CD — the center of your dev workflow |
| **Learning Priority** | **Beginner** |

**AI OS Integration:**
- GitHub MCP → agents create PRs, review code
- GitHub Actions → automated testing, deployment
- GitHub Projects → kanban for tasks

---

### Linear
| Field | Details |
|-------|---------|
| **Purpose** | Fast, keyboard-driven project management |
| **Learning Priority** | **Beginner** |

**Use Cases:** Engineering teams, sprint planning, issue tracking

---

### Obsidian
| Field | Details |
|-------|---------|
| **Purpose** | Local-first knowledge management (Markdown) |
| **License** | Proprietary (free personal use) |
| **Learning Priority** | **Beginner** |

**AI OS Integration:** Local vault → RAG pipeline → AI answers questions about your notes

---

## 18. Recommended Tech Stacks

---

### Stack A: Personal AI OS (Your Core Setup)
**For building AI apps, agents, and automations — laptop-first**

```
Coding Agent:    OpenCode + Ollama (local) / Claude Code (cloud)
Multi-Agent:     CrewAI + LangGraph
Automation:      n8n (self-hosted) + Hermes Agent
Backend:         FastAPI (Python)
Frontend:        Next.js + Tailwind + shadcn/ui
Database:        PostgreSQL + pgvector
Vector DB:       Qdrant (Docker)
Cache:           Redis
Auth:            Supabase Auth
Observability:   Langfuse (self-hosted)
CI/CD:           GitHub Actions
Deployment:      Docker Compose → Coolify
Project Mgmt:    Notion + GitHub
LLM Local:       Ollama (llama3.1, qwen2.5-coder)
LLM Cloud:       Claude (Anthropic) via API
```

---

### Stack B: RAG Application
**For building document intelligence and knowledge systems**

```
Framework:       LlamaIndex or LangChain
Vector DB:       Qdrant (self-hosted)
Embedding:       nomic-embed-text (Ollama) or text-embedding-3-small (OpenAI)
Document Parser: Unstructured.io
Reranker:        Cohere Rerank or BGE Reranker
Backend:         FastAPI
Frontend:        Next.js
Evaluation:      RAGAS + DeepEval
Observability:   Langfuse
```

---

### Stack C: Full-Stack SaaS
**For shipping production web applications**

```
Frontend:        Next.js 14+ (App Router)
Styling:         Tailwind CSS + shadcn/ui
Backend:         Next.js API Routes or FastAPI
Database:        Supabase (PostgreSQL + Auth + Storage)
ORM:             Prisma (TS) or SQLModel (Python)
Auth:            Supabase Auth or Clerk
Payments:        Stripe
Email:           Resend
Deployment:      Vercel (frontend) + Railway/Render (backend)
Monitoring:      Sentry + Vercel Analytics
```

---

### Stack D: Autonomous Agent System
**For production multi-agent workflows**

```
Orchestration:   CrewAI or LangGraph
Runtime:         OpenHands (Docker-isolated execution)
Memory:          PostgreSQL (long-term) + Redis (short-term)
Tools:           MCP servers (GitHub, Browser, File, DB)
Automation:      n8n triggers + Hermes judgment layer
Observability:   Langfuse + Arize Phoenix
Testing:         DeepEval + RAGAS
Deployment:      Docker Compose + GitHub Actions
```

---

## 19. Learning Roadmap

---

### Phase 1 — Foundation (Weeks 1–4)
**Goal: Get your AI OS running locally**

- [ ] Install Docker Desktop and Docker Compose
- [ ] Set up Ollama with llama3.1:8b and qwen2.5-coder
- [ ] Install and configure OpenCode
- [ ] Set up PostgreSQL + pgvector via Docker
- [ ] Deploy n8n locally — build first automation
- [ ] Learn Python fundamentals + async/await
- [ ] Build first FastAPI endpoint
- [ ] Set up GitHub with Actions CI pipeline
- [ ] Configure Notion workspace for project management

**Tools to master:** Docker, Ollama, OpenCode, n8n, FastAPI basics

---

### Phase 2 — Building (Weeks 5–10)
**Goal: Ship first AI application**

- [ ] Build first RAG system with LangChain + Chroma → upgrade to Qdrant
- [ ] Create first CrewAI multi-agent system
- [ ] Deploy Langfuse and trace your first agent run
- [ ] Build a Next.js frontend with Tailwind + shadcn/ui
- [ ] Connect Next.js to FastAPI backend
- [ ] Add Supabase for authentication
- [ ] Deploy full stack via Docker Compose + Coolify
- [ ] Set up GitHub MCP server in OpenCode
- [ ] Build first n8n + Hermes Agent workflow

**Tools to master:** LangChain, CrewAI, Qdrant, Next.js, Supabase, Langfuse

---

### Phase 3 — Production (Weeks 11–18)
**Goal: Production-grade agents and systems**

- [ ] Implement LangGraph for stateful agent workflows
- [ ] Add OpenHands for autonomous code tasks
- [ ] Build evaluation pipeline with DeepEval/RAGAS
- [ ] Implement secrets management with Infisical
- [ ] Set up Grafana + Prometheus for system monitoring
- [ ] Configure GitHub Actions for full CI/CD
- [ ] Build custom MCP server for your stack
- [ ] Implement LiteLLM for model routing
- [ ] Add Redis caching for LLM responses
- [ ] Write agent evals and run in CI

**Tools to master:** LangGraph, OpenHands, DeepEval, LiteLLM, GitHub Actions

---

### Phase 4 — Scale (Weeks 19+)
**Goal: Enterprise-grade, self-sustaining system**

- [ ] Migrate to Kubernetes (k3s) for orchestration
- [ ] Implement Temporal for durable long-running workflows
- [ ] Build A2A (Agent-to-Agent) communication
- [ ] Set up DSPy for automated prompt optimization
- [ ] Add Keycloak for enterprise SSO
- [ ] Infrastructure-as-code with OpenTofu
- [ ] Multi-region deployment strategy
- [ ] Advanced agent evaluation and regression testing

---

## 20. Implementation Priorities

---

### Week 1: Must Do First
1. `docker-compose up` with PostgreSQL + Qdrant + Redis + n8n
2. Install Ollama, pull `llama3.1:8b` and `nomic-embed-text`
3. Install OpenCode, connect to Ollama
4. Create first n8n workflow (webhook → LLM → Notion)

### Month 1: Core Stack
1. FastAPI backend with PostgreSQL
2. First CrewAI multi-agent workflow
3. Langfuse for tracing
4. Next.js frontend deployed to Vercel
5. GitHub Actions CI/CD

### Month 3: Production-Ready
1. LangGraph stateful agents
2. Qdrant RAG pipeline
3. OpenHands for autonomous tasks
4. Evaluation pipeline
5. Monitoring stack

### Month 6: Full AI OS
1. Custom MCP servers for your stack
2. LiteLLM gateway for all model calls
3. n8n + Hermes as automation backbone
4. Fully automated testing and deployment

---

## Quick Reference: Tool by Category Summary

| Category | Primary | Secondary | Avoid (for now) |
|----------|---------|-----------|-----------------|
| Coding Agent | OpenCode | Claude Code, Aider | — |
| Multi-Agent | CrewAI | LangGraph, AutoGen | MetaGPT (complex) |
| Automation | n8n + Hermes | — | Zapier (costly) |
| Backend | FastAPI | Hono/Express | Django (heavy) |
| Frontend | Next.js | — | Vue (smaller ecosystem) |
| Database | PostgreSQL | SQLite | MongoDB (prefer Postgres) |
| Vector DB | Qdrant | pgvector | Pinecone (no self-host) |
| LLM (local) | Ollama | — | — |
| LLM (cloud) | Claude API | GPT, Gemini | — |
| RAG Framework | LangChain | LlamaIndex | — |
| Observability | Langfuse | Helicone | LangSmith (no self-host) |
| Auth | Supabase Auth | Clerk | Rolling your own |
| Deployment | Docker + Coolify | Vercel | AWS (complex) |
| Project Mgmt | Notion + GitHub | Linear | Jira (heavy) |
| Testing | Pytest + DeepEval | RAGAS | — |
| CI/CD | GitHub Actions | — | Jenkins (outdated) |

---

## Essential GitHub Repositories

```bash
# AI Agents
git clone https://github.com/sst/opencode
git clone https://github.com/All-Hands-AI/OpenHands
git clone https://github.com/paul-gauthier/aider
git clone https://github.com/cline/cline

# Multi-Agent Frameworks
git clone https://github.com/crewAIInc/crewAI
git clone https://github.com/langchain-ai/langgraph
git clone https://github.com/microsoft/autogen

# RAG & AI Frameworks
git clone https://github.com/langchain-ai/langchain
git clone https://github.com/run-llama/llama_index
git clone https://github.com/deepset-ai/haystack

# Vector Databases
git clone https://github.com/qdrant/qdrant
git clone https://github.com/chroma-core/chroma
git clone https://github.com/pgvector/pgvector

# Observability
git clone https://github.com/langfuse/langfuse

# Automation
git clone https://github.com/n8n-io/n8n

# Local LLMs
git clone https://github.com/ollama/ollama

# Backend
git clone https://github.com/tiangolo/fastapi

# Deployment
git clone https://github.com/coollabsio/coolify

# Secret Management
git clone https://github.com/Infisical/infisical

# LLM Gateway
git clone https://github.com/BerriAI/litellm
```

---

## Closing Notes

Your AI OS is not a product — it's a **practice**. The tools above are the scaffolding; your judgment in composing them is the architecture.

**Start small:** Docker + Ollama + n8n + OpenCode running locally is a complete, capable AI workstation in under an hour.

**Scale deliberately:** Add tools only when a real problem demands them. A $5 VPS with Docker Compose handles most personal and small-team workloads.

**Own your data:** Self-host Langfuse, Qdrant, and n8n. Your agent traces, knowledge bases, and workflows are proprietary infrastructure — keep them under your control.

**Build in public:** Share your agent workflows, Notion templates, and n8n flows. The AI OS community grows through shared patterns.

---

*Guide compiled June 2026 | Tools and versions change rapidly — verify GitHub stars and licensing before production adoption.*
