# 🧠 Personal AI Operating System
## A Unified, Free, Self-Hosted AI Automation Ecosystem on a Laptop

> **Target User:** B.Tech AI & Data Science Student  
> **Goal:** Build a free personal AI OS where OpenCode is the single control interface for coding, automation, agent orchestration, knowledge management, task execution, and project management.  
> **Stack:** OpenCode · Hermes Agent · n8n · CrewAI · OpenHands · Notion · PostgreSQL · GitHub · Docker

---

## Table of Contents

1. [System Overview](#1-system-overview)
2. [Architecture Diagram](#2-architecture-diagram)
3. [Component Explanations](#3-component-explanations)
4. [Agent Architecture](#4-agent-architecture)
5. [Memory Architecture](#5-memory-architecture)
6. [Knowledge Management](#6-knowledge-management)
7. [Task Orchestration](#7-task-orchestration)
8. [Development Workflow](#8-development-workflow)
9. [Monitoring and Logging](#9-monitoring-and-logging)
10. [OpenCode as Command Center](#10-opencode-as-command-center)
11. [Folder Structure](#11-folder-structure)
12. [Docker Setup](#12-docker-setup)
13. [MCP Server Configuration](#13-mcp-server-configuration)
14. [Environment Variables](#14-environment-variables)
15. [Database Schema](#15-database-schema)
16. [Workflow Examples](#16-workflow-examples)
17. [Installation Roadmap](#17-installation-roadmap)
18. [Security Practices](#18-security-practices)
19. [Backup Strategy](#19-backup-strategy)
20. [Troubleshooting Guide](#20-troubleshooting-guide)
21. [Scaling Path](#21-scaling-path)

---

## 1. System Overview

This document defines a **Personal AI Operating System (PAIOS)** — a fully self-hosted, free, laptop-first ecosystem where every AI tool is unified under a single control surface: **OpenCode**.

### Core Philosophy

```
One Interface → Multiple Agents → One Brain → One Database → One Workflow Engine
```

| Layer | Purpose | Tools |
|-------|---------|-------|
| **Control** | Single command interface | OpenCode |
| **Agents** | Autonomous task execution | Hermes, CrewAI, OpenHands |
| **Orchestration** | Workflow automation | n8n |
| **Memory** | Persistent knowledge store | PostgreSQL + pgvector |
| **Knowledge** | Structured notes & docs | Notion (self-hosted alt: AppFlowy) |
| **Code** | Version control & CI | GitHub |
| **Runtime** | Isolated environments | Docker |

### Design Principles

- **Zero licensing cost** — every tool is free and open-source
- **Laptop-first** — runs on 8GB+ RAM; optimized for resource constraints
- **Offline-capable** — local LLMs via Ollama for air-gapped use
- **Upgrade-ready** — same compose files work on a VPS or home server
- **Single pane of glass** — OpenCode MCP connections touch every service

---

## 2. Architecture Diagram

### High-Level System Architecture

```
╔══════════════════════════════════════════════════════════════════════════╗
║                        OPENCODE (Command Center)                         ║
║              Terminal IDE + MCP Client + Natural Language Router          ║
╚══════════════════════╤═══════════════════════════════════════════════════╝
                       │  MCP Protocol (JSON-RPC over stdio/HTTP)
        ┌──────────────┼──────────────────────────────────┐
        │              │                                  │
        ▼              ▼                                  ▼
┌──────────────┐ ┌──────────────┐               ┌──────────────────┐
│  MCP Server  │ │  MCP Server  │               │   MCP Server     │
│  PostgreSQL  │ │   GitHub     │               │     n8n          │
└──────┬───────┘ └──────┬───────┘               └────────┬─────────┘
       │                │                                │
       ▼                ▼                                ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                         DOCKER NETWORK (ai-os-net)                       │
│                                                                           │
│  ┌─────────────┐  ┌──────────────┐  ┌────────────┐  ┌────────────────┐  │
│  │  PostgreSQL  │  │    Redis     │  │   Ollama   │  │   AppFlowy /   │  │
│  │  + pgvector │  │  (Queue/     │  │  (Local    │  │   Notion Sync  │  │
│  │  + pg_cron  │  │   Cache)     │  │   LLMs)    │  │   Service      │  │
│  └──────┬──────┘  └──────┬───────┘  └─────┬──────┘  └───────┬────────┘  │
│         │                │                │                  │            │
│  ┌──────▼──────────────────────────────────▼──────────────────▼────────┐  │
│  │                    AGENT LAYER                                        │  │
│  │                                                                       │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌──────────────┐                 │  │
│  │  │ Hermes Agent│  │   CrewAI    │  │  OpenHands   │                 │  │
│  │  │ (Reasoning/ │  │ (Multi-Agent│  │  (Code Gen/  │                 │  │
│  │  │  Planning)  │  │  Teams)     │  │  Execution)  │                 │  │
│  │  └──────┬──────┘  └──────┬──────┘  └──────┬───────┘                 │  │
│  │         └────────────────┼────────────────┘                          │  │
│  │                          │                                            │  │
│  │              ┌───────────▼──────────┐                                │  │
│  │              │    n8n Orchestrator   │                                │  │
│  │              │  (Workflow Engine)    │                                │  │
│  │              │  Webhooks/HTTP/Cron   │                                │  │
│  │              └──────────────────────┘                                │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                           │
└─────────────────────────────────────────────────────────────────────────┘
                       │                │
                       ▼                ▼
              ┌──────────────┐  ┌──────────────┐
              │    GitHub    │  │   Notion /   │
              │   (Remote)   │  │  AppFlowy    │
              └──────────────┘  └──────────────┘
```

### Data Flow Diagram

```
User Types in OpenCode
        │
        ▼
[Intent Classification via LLM]
        │
   ┌────┴─────┐
   │          │
   ▼          ▼
Code Task   Automation Task
   │          │
   ▼          ▼
OpenHands   n8n Webhook Trigger
   │          │
   ▼          ▼
CrewAI     Hermes Agent
(Research) (Reasoning)
   │          │
   └────┬─────┘
        │
        ▼
   PostgreSQL
   (Store result + vector embed)
        │
        ▼
   Notion Sync
   (Structured knowledge)
        │
        ▼
   GitHub Commit
   (Version control)
        │
        ▼
   OpenCode Response
```

### Communication Protocol Map

```
OpenCode ──[MCP/stdio]──► MCP Servers
OpenCode ──[MCP/HTTP]───► n8n Webhook
n8n      ──[HTTP REST]──► Hermes Agent API
n8n      ──[HTTP REST]──► CrewAI API
n8n      ──[HTTP REST]──► OpenHands API
Agents   ──[pg driver]──► PostgreSQL
Agents   ──[REST API]───► Notion / AppFlowy
n8n      ──[GitHub API]─► GitHub Repos
All      ──[Redis PubSub]► Event Bus
```

---

## 3. Component Explanations

### 3.1 OpenCode — The Command Center

**Role:** Primary human interface. The only window you need open.

OpenCode is a terminal-based AI coding assistant that supports the **Model Context Protocol (MCP)**. This means it can connect to any MCP-compliant server and expose tools from PostgreSQL, GitHub, n8n, file systems, and custom agents — all accessible via natural language inside one terminal session.

**Key capabilities used in PAIOS:**
- Issue natural language commands that route to agents
- Read/write database via MCP-PostgreSQL server
- Trigger n8n workflows via MCP-HTTP server
- Browse and commit code via MCP-GitHub server
- Access project knowledge via MCP-filesystem server

---

### 3.2 Hermes Agent — Reasoning & Planning Engine

**Role:** The "brain" for complex multi-step reasoning tasks.

Hermes (based on the Hermes series by Nous Research, e.g., `Hermes-3-Llama-3.1`) is a fine-tuned local LLM optimized for:
- Function calling
- Chain-of-thought reasoning
- Agentic planning
- Structured JSON output

**Deployment:** Served via **Ollama** locally. Accessed by n8n and CrewAI agents via HTTP.

```
Ollama ──serves──► Hermes Model
n8n    ──calls──► http://ollama:11434/api/generate
CrewAI ──calls──► Ollama OpenAI-compatible endpoint
```

---

### 3.3 n8n — Workflow Orchestration Engine

**Role:** The nervous system. Connects everything via visual workflows.

n8n is a self-hosted workflow automation tool. In PAIOS it acts as:
- **Trigger hub:** Webhooks, cron jobs, database change events
- **Agent router:** Decides which agent handles a task
- **Integration glue:** Connects GitHub, Notion, PostgreSQL, Slack (optional), email
- **Error handler:** Catches agent failures and retries or alerts

**Exposed interface:** REST API + Webhook URLs that OpenCode can call via MCP-HTTP.

---

### 3.4 CrewAI — Multi-Agent Teams

**Role:** Orchestrates teams of specialized agents for complex projects.

CrewAI allows you to define **crews** — groups of agents with different roles (researcher, writer, coder, reviewer) that collaborate on a shared task.

**In PAIOS, example crews:**
- **Research Crew:** Research Agent + Summarizer Agent + Note-Taking Agent
- **Dev Crew:** Planner Agent + Coder Agent + Reviewer Agent
- **Data Crew:** Collector Agent + Analyst Agent + Visualizer Agent

**Deployment:** FastAPI wrapper exposing CrewAI as an HTTP service.

---

### 3.5 OpenHands — Code Generation & Execution

**Role:** Autonomous software engineer. Writes, runs, and debugs code.

OpenHands (formerly OpenDevin) is an open-source AI software agent that can:
- Write entire files and applications
- Execute code in sandboxed Docker containers
- Browse documentation
- Fix bugs autonomously
- Run terminal commands

**Integration:** n8n triggers OpenHands via its REST API when a coding task is detected.

---

### 3.6 Notion — Knowledge Management

**Role:** Structured knowledge base for projects, notes, and documentation.

Notion is used as the human-readable layer of the knowledge base. Agents write summaries, research outputs, and project plans here via the Notion API.

**Free alternative (fully self-hosted):** **AppFlowy** — an open-source Notion alternative that runs in Docker with zero licensing cost.

---

### 3.7 PostgreSQL — The System Brain Database

**Role:** Central persistent store for all agent memory, task history, embeddings, and metadata.

Extensions used:
- **pgvector** — stores and searches vector embeddings for semantic memory
- **pg_cron** — schedules database maintenance tasks
- **pg_stat_statements** — query performance monitoring

---

### 3.8 GitHub — Code Repository & CI/CD

**Role:** Version control for all projects managed by the AI OS.

Used by:
- OpenHands to commit generated code
- n8n workflows to trigger on push/PR events
- OpenCode's MCP-GitHub server for direct repo management

---

### 3.9 Docker — Container Runtime

**Role:** Runs the entire PAIOS stack in isolated, reproducible containers.

Every service runs in Docker. A single `docker-compose.yml` starts the entire OS.

---

## 4. Agent Architecture

### 4.1 Agent Hierarchy

```
┌─────────────────────────────────────────────────────┐
│                  ORCHESTRATOR LAYER                   │
│            n8n (Workflow Engine / Router)             │
└───────────────────────┬─────────────────────────────┘
                        │
        ┌───────────────┼───────────────┐
        ▼               ▼               ▼
┌──────────────┐ ┌─────────────┐ ┌──────────────┐
│ PLANNING     │ │  EXECUTION  │ │  KNOWLEDGE   │
│ AGENT        │ │  AGENT      │ │  AGENT       │
│              │ │             │ │              │
│ Hermes LLM   │ │  OpenHands  │ │  CrewAI      │
│ - Break down │ │  - Write    │ │  Research    │
│   tasks      │ │    code     │ │  Crew        │
│ - Make plan  │ │  - Run code │ │  - Gather    │
│ - Prioritize │ │  - Fix bugs │ │    data      │
│              │ │  - Commit   │ │  - Summarize │
└──────┬───────┘ └──────┬──────┘ └──────┬───────┘
       │                │               │
       └────────────────┴───────────────┘
                        │
                        ▼
              ┌─────────────────┐
              │  MEMORY LAYER   │
              │  PostgreSQL     │
              │  + pgvector     │
              └─────────────────┘
```

### 4.2 Agent Responsibilities

| Agent | Model | Trigger | Responsibility | Output |
|-------|-------|---------|---------------|--------|
| **Planner** | Hermes-3 (Ollama) | Any new task | Break task into subtasks, create execution plan | JSON task plan → PostgreSQL |
| **Coder** | OpenHands + GPT/Claude | Code subtask | Write, test, debug, commit code | Git commit + test results |
| **Researcher** | CrewAI + Hermes | Research subtask | Web search, summarize, extract facts | Markdown report → Notion |
| **Reviewer** | CrewAI | After code/research | Quality check, fact-check, suggest improvements | Review notes → PostgreSQL |
| **Notifier** | n8n built-in | Task completion | Send summary to user via terminal/email/Slack | Notification |
| **Archivist** | n8n + pg functions | Nightly cron | Embed and archive completed task data | pgvector embeddings |

### 4.3 Agent Communication Protocol

Agents communicate via:

1. **Direct HTTP calls** (synchronous, short tasks)
2. **Redis pub/sub** (asynchronous, event-driven)
3. **PostgreSQL task queue** (persistent, durable)

```python
# Task Queue Schema (used by all agents)
# agent publishes a task:
{
    "task_id": "uuid",
    "type": "code|research|plan|review",
    "priority": 1-5,
    "payload": { ... },
    "assigned_to": "openhands|crewai|hermes",
    "status": "pending|running|done|failed",
    "created_at": "timestamp",
    "parent_task_id": "uuid|null"
}
```

---

## 5. Memory Architecture

### 5.1 Memory Types

```
┌─────────────────────────────────────────────────────────┐
│                    MEMORY SYSTEM                         │
│                                                          │
│  ┌────────────────┐  ┌──────────────┐  ┌─────────────┐  │
│  │  WORKING       │  │  EPISODIC    │  │  SEMANTIC   │  │
│  │  MEMORY        │  │  MEMORY      │  │  MEMORY     │  │
│  │                │  │              │  │             │  │
│  │  Redis         │  │  PostgreSQL  │  │  pgvector   │  │
│  │  (In-flight    │  │  tasks +     │  │  (Embedded  │  │
│  │   context)     │  │  history     │  │   knowledge │  │
│  │  TTL: 1 hour   │  │  tables      │  │   chunks)   │  │
│  └────────────────┘  └──────────────┘  └─────────────┘  │
│                                                          │
│  ┌────────────────┐  ┌──────────────────────────────┐   │
│  │  PROCEDURAL    │  │  EXTERNAL                    │   │
│  │  MEMORY        │  │  MEMORY                      │   │
│  │                │  │                              │   │
│  │  n8n Workflows │  │  GitHub (code history)       │   │
│  │  (How-to-do    │  │  Notion (structured notes)   │   │
│  │   patterns)    │  │  Files (filesystem)          │   │
│  └────────────────┘  └──────────────────────────────┘   │
└─────────────────────────────────────────────────────────┘
```

### 5.2 Vector Memory (Semantic Search)

All agent outputs are embedded and stored in pgvector for semantic retrieval:

```sql
-- Agents call this function to remember something
SELECT store_memory(
    content := 'FastAPI handles async routes with async def',
    memory_type := 'technical_fact',
    source := 'research_agent',
    project_id := 'proj_abc123'
);

-- Agents call this to recall relevant context
SELECT * FROM recall_memory(
    query := 'how to handle async in Python web frameworks',
    limit_n := 5,
    project_filter := 'proj_abc123'
);
```

### 5.3 Context Window Management

Each agent call constructs its context from:

```
[System Prompt]
     +
[Recalled Memories (top-5 semantic matches)]
     +
[Recent Task History (last 10 from PostgreSQL)]
     +
[Current Task Details]
     +
[Available Tools (MCP tool list)]
```

This ensures agents always have relevant context without hitting token limits.

---

## 6. Knowledge Management

### 6.1 Knowledge Flow

```
Raw Input (web/file/conversation)
        │
        ▼
  Chunking Service (n8n)
  [Split into 512-token chunks]
        │
        ▼
  Embedding (Ollama nomic-embed-text)
        │
        ▼
  pgvector Storage
        │
    ┌───┴───┐
    ▼       ▼
Notion   PostgreSQL
(human   (machine
readable) queryable)
```

### 6.2 Knowledge Categories

| Category | Storage | Access Pattern |
|----------|---------|---------------|
| Project documentation | Notion/AppFlowy | Human reading + API |
| Code snippets | GitHub | Git + search |
| Research findings | PostgreSQL + Notion | Semantic search + browse |
| Agent decisions | PostgreSQL | Query by task/date |
| Personal notes | Notion/AppFlowy | Manual + API |
| System configs | Files + GitHub | Git versioned |

### 6.3 Notion Integration (via n8n)

```
Agent Output
    │
    ▼
n8n Notion Node
    │ (Notion API v1)
    ▼
┌─────────────────────────────────┐
│  Notion Workspace               │
│                                 │
│  📁 Projects/                   │
│     📄 [Project Name]           │
│        🗒️ Research Notes        │
│        💻 Code Decisions        │
│        ✅ Task Tracker          │
│                                 │
│  📁 Agent Memory/               │
│     📄 Daily Logs               │
│     📄 Important Facts          │
│                                 │
│  📁 Knowledge Base/             │
│     📄 Technical Reference      │
│     📄 How-To Guides            │
└─────────────────────────────────┘
```

**AppFlowy (Self-hosted Notion alternative):**
If you want 100% self-hosted with no Notion account, replace Notion with AppFlowy:

```yaml
# In docker-compose.yml
appflowy:
  image: appflowyinc/appflowy_cloud:latest
  ports:
    - "8080:8080"
  environment:
    - APPFLOWY_DATABASE_URL=postgres://ai_os:${POSTGRES_PASSWORD}@postgres:5432/appflowy
```

---

## 7. Task Orchestration

### 7.1 Task Lifecycle

```
[Task Created] ──► [Queued in PostgreSQL] ──► [Planner analyzes]
       │
       ▼
[Subtasks generated] ──► [Assigned to agents] ──► [Executed]
       │
       ▼
[Results aggregated] ──► [Review pass] ──► [Stored in memory]
       │
       ▼
[Notion updated] ──► [GitHub committed] ──► [User notified]
```

### 7.2 n8n Master Workflow

The master n8n workflow handles all routing:

```
Webhook: POST /webhook/task
    │
    ▼
[Parse task JSON]
    │
    ▼
[Switch node: task.type]
    │
    ├──► "code"     ──► [OpenHands API call]
    ├──► "research" ──► [CrewAI Research Crew API]
    ├──► "plan"     ──► [Hermes Ollama API]
    ├──► "write"    ──► [Hermes Ollama API]
    └──► "default"  ──► [Hermes Ollama API]
    │
    ▼
[Wait for result]
    │
    ▼
[Store in PostgreSQL]
    │
    ▼
[Update Notion page]
    │
    ▼
[Emit completion event via Redis]
    │
    ▼
[Return result to caller]
```

### 7.3 Priority Queue (PostgreSQL-based)

```sql
-- Get next task to process
SELECT * FROM task_queue
WHERE status = 'pending'
  AND assigned_to = $1  -- agent name
ORDER BY priority DESC, created_at ASC
LIMIT 1
FOR UPDATE SKIP LOCKED;
```

This allows multiple agent processes to safely pull from the same queue without conflicts.

---

## 8. Development Workflow

### 8.1 Typical Dev Session

```
1. Open terminal → launch OpenCode
2. Describe task in natural language:
   "Implement a FastAPI endpoint for user authentication with JWT"

3. OpenCode routes to Planner Agent via n8n
   → Planner breaks into subtasks:
     a. Design DB schema
     b. Write auth utilities
     c. Write endpoint
     d. Write tests
     e. Update README

4. OpenHands executes subtasks sequentially
   → Writes files
   → Runs tests
   → Auto-fixes failures

5. Results committed to GitHub
6. Summary written to Notion
7. OpenCode shows completion report
```

### 8.2 Git Workflow

```
main (protected)
  └── develop
        ├── feature/agent-generated-xxx
        ├── feature/agent-generated-yyy
        └── hotfix/agent-fix-zzz
```

All agent commits go to `feature/` branches. You review and merge to `develop`, then `main`.

### 8.3 CI Pipeline (GitHub Actions — Free Tier)

```yaml
# .github/workflows/ai-os-ci.yml
name: PAIOS CI
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run tests
        run: docker compose -f docker-compose.test.yml up --abort-on-container-exit
      - name: Notify n8n
        run: |
          curl -X POST ${{ secrets.N8N_WEBHOOK_URL }}/ci-result \
            -H "Content-Type: application/json" \
            -d '{"status": "${{ job.status }}", "repo": "${{ github.repository }}"}'
```

---

## 9. Monitoring and Logging

### 9.1 Monitoring Stack (All Free)

| Tool | Purpose | Port |
|------|---------|------|
| **Grafana** | Dashboards and alerts | 3001 |
| **Prometheus** | Metrics collection | 9090 |
| **Loki** | Log aggregation | 3100 |
| **Promtail** | Log shipping | — |
| **cAdvisor** | Container metrics | 8081 |

### 9.2 Key Metrics to Track

```
Agent Metrics:
  - tasks_completed_total (counter)
  - task_duration_seconds (histogram)
  - task_failure_total (counter)
  - agent_queue_depth (gauge)

System Metrics:
  - cpu_usage_percent
  - memory_usage_bytes
  - ollama_inference_seconds
  - postgres_query_duration_seconds

n8n Metrics:
  - workflow_executions_total
  - workflow_error_total
  - webhook_latency_seconds
```

### 9.3 Logging Architecture

```
All Services
    │
    ▼ (stdout/stderr → Docker logs)
Promtail (log shipper)
    │
    ▼
Loki (log store)
    │
    ▼
Grafana (log explorer + alerts)
```

All agent decisions are also logged to PostgreSQL for searchable audit trail:

```sql
-- Agent decision log
INSERT INTO agent_logs (agent_name, task_id, action, reasoning, timestamp)
VALUES ('hermes_planner', $1, 'created_subtask', $2, NOW());
```

---

## 10. OpenCode as Command Center

### 10.1 MCP Server Map

OpenCode connects to these MCP servers simultaneously:

```json
{
  "mcpServers": {
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres"],
      "env": {
        "POSTGRES_CONNECTION_STRING": "postgresql://ai_os:password@localhost:5432/ai_os_db"
      }
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/home/user/projects"]
    },
    "n8n-http": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-http"],
      "env": {
        "BASE_URL": "http://localhost:5678",
        "API_KEY": "${N8N_API_KEY}"
      }
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "brave-search": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "${BRAVE_API_KEY}"
      }
    }
  }
}
```

### 10.2 What You Can Say to OpenCode

```bash
# Task delegation
"Create a new n8n workflow that monitors my GitHub PRs and summarizes them daily"

# Direct database queries  
"Show me all tasks that failed in the last 24 hours"

# Agent coordination
"Start a research crew to find the best vector database options in 2025"

# Code generation
"Build a REST API for the task queue schema we designed"

# Knowledge retrieval
"What did we decide about authentication last week?"

# System status
"How many workflows ran today? Any failures?"

# Git operations
"Show me what files the OpenHands agent changed in the last commit"
```

### 10.3 Custom MCP Server for PAIOS

Build a dedicated MCP server that exposes PAIOS-specific tools to OpenCode:

```python
# mcp_servers/paios_server.py
from mcp.server import Server
from mcp.server.models import InitializationOptions
import mcp.types as types
import httpx

server = Server("paios")

@server.list_tools()
async def list_tools():
    return [
        types.Tool(
            name="trigger_agent",
            description="Trigger an AI agent with a task",
            inputSchema={
                "type": "object",
                "properties": {
                    "agent": {"type": "string", "enum": ["planner", "coder", "researcher", "reviewer"]},
                    "task": {"type": "string"},
                    "priority": {"type": "integer", "default": 3}
                },
                "required": ["agent", "task"]
            }
        ),
        types.Tool(
            name="get_task_status",
            description="Get status of a task by ID",
            inputSchema={
                "type": "object",
                "properties": {
                    "task_id": {"type": "string"}
                },
                "required": ["task_id"]
            }
        ),
        types.Tool(
            name="search_memory",
            description="Search the AI OS memory for relevant information",
            inputSchema={
                "type": "object",
                "properties": {
                    "query": {"type": "string"},
                    "limit": {"type": "integer", "default": 5}
                },
                "required": ["query"]
            }
        ),
        types.Tool(
            name="list_workflows",
            description="List all n8n workflows and their status",
            inputSchema={"type": "object", "properties": {}}
        )
    ]

@server.call_tool()
async def call_tool(name: str, arguments: dict):
    async with httpx.AsyncClient() as client:
        if name == "trigger_agent":
            resp = await client.post(
                "http://localhost:5678/webhook/task",
                json=arguments,
                headers={"X-API-Key": N8N_API_KEY}
            )
            return [types.TextContent(type="text", text=resp.text)]
        
        elif name == "search_memory":
            resp = await client.post(
                "http://localhost:8000/api/memory/search",
                json={"query": arguments["query"], "limit": arguments.get("limit", 5)}
            )
            return [types.TextContent(type="text", text=resp.text)]
```

---

## 11. Folder Structure

```
~/ai-os/
├── 📄 docker-compose.yml          # Main compose file
├── 📄 docker-compose.dev.yml      # Dev overrides
├── 📄 docker-compose.test.yml     # Test environment
├── 📄 .env                        # Environment variables (gitignored)
├── 📄 .env.example                # Template for env vars
├── 📄 Makefile                    # Shortcut commands
├── 📄 README.md                   # This file
│
├── 📁 mcp_servers/                # Custom MCP servers
│   ├── 📄 paios_server.py         # PAIOS master MCP server
│   ├── 📄 requirements.txt
│   └── 📄 Dockerfile
│
├── 📁 agents/
│   ├── 📁 crewai/                 # CrewAI crews and agents
│   │   ├── 📄 crews.py            # Crew definitions
│   │   ├── 📄 agents.py           # Agent definitions
│   │   ├── 📄 tasks.py            # Task definitions
│   │   ├── 📄 tools.py            # Custom tools
│   │   ├── 📄 api.py              # FastAPI wrapper
│   │   ├── 📄 requirements.txt
│   │   └── 📄 Dockerfile
│   │
│   ├── 📁 hermes/                 # Hermes agent service
│   │   ├── 📄 api.py              # FastAPI wrapper
│   │   ├── 📄 planner.py          # Planning logic
│   │   ├── 📄 memory.py           # Memory interface
│   │   ├── 📄 requirements.txt
│   │   └── 📄 Dockerfile
│   │
│   └── 📁 openhands/              # OpenHands config
│       └── 📄 config.toml
│
├── 📁 n8n/
│   ├── 📁 workflows/              # Exported n8n workflows (JSON)
│   │   ├── 📄 master_router.json
│   │   ├── 📄 github_monitor.json
│   │   ├── 📄 notion_sync.json
│   │   └── 📄 daily_digest.json
│   └── 📁 credentials/            # n8n credentials backup (encrypted)
│
├── 📁 database/
│   ├── 📄 init.sql                # Database initialization
│   ├── 📄 schema.sql              # Full schema
│   ├── 📄 migrations/             # Schema migrations
│   └── 📄 seeds/                  # Test data
│
├── 📁 monitoring/
│   ├── 📄 prometheus.yml          # Prometheus config
│   ├── 📁 grafana/
│   │   ├── 📄 datasources.yml
│   │   └── 📁 dashboards/
│   │       ├── 📄 ai-os-overview.json
│   │       └── 📄 agent-performance.json
│   └── 📄 loki-config.yml
│
├── 📁 scripts/
│   ├── 📄 setup.sh                # First-time setup
│   ├── 📄 backup.sh               # Backup script
│   ├── 📄 restore.sh              # Restore script
│   └── 📄 health-check.sh         # System health check
│
├── 📁 projects/                   # Your actual work (AI-managed)
│   └── 📁 [project-name]/
│       ├── 📄 .paios.yml          # Project config for agents
│       └── ...
│
└── 📁 data/                       # Persistent data (gitignored)
    ├── 📁 postgres/
    ├── 📁 redis/
    ├── 📁 n8n/
    ├── 📁 ollama/
    ├── 📁 grafana/
    └── 📁 loki/
```

---

## 12. Docker Setup

### 12.1 Main docker-compose.yml

```yaml
# ~/ai-os/docker-compose.yml
version: '3.9'

networks:
  ai-os-net:
    driver: bridge

volumes:
  postgres_data:
  redis_data:
  n8n_data:
  ollama_data:
  grafana_data:
  loki_data:

services:

  # ─────────────────────────────────────────
  # CORE DATABASE
  # ─────────────────────────────────────────
  postgres:
    image: pgvector/pgvector:pg16
    container_name: ai-os-postgres
    restart: unless-stopped
    environment:
      POSTGRES_USER: ${POSTGRES_USER:-ai_os}
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
      POSTGRES_DB: ${POSTGRES_DB:-ai_os_db}
    volumes:
      - postgres_data:/var/lib/postgresql/data
      - ./database/init.sql:/docker-entrypoint-initdb.d/init.sql
    ports:
      - "5432:5432"
    networks:
      - ai-os-net
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${POSTGRES_USER:-ai_os}"]
      interval: 10s
      timeout: 5s
      retries: 5

  # ─────────────────────────────────────────
  # CACHE / MESSAGE BUS
  # ─────────────────────────────────────────
  redis:
    image: redis:7-alpine
    container_name: ai-os-redis
    restart: unless-stopped
    command: redis-server --requirepass ${REDIS_PASSWORD} --maxmemory 512mb --maxmemory-policy allkeys-lru
    volumes:
      - redis_data:/data
    ports:
      - "6379:6379"
    networks:
      - ai-os-net
    healthcheck:
      test: ["CMD", "redis-cli", "-a", "${REDIS_PASSWORD}", "ping"]
      interval: 10s
      timeout: 5s
      retries: 5

  # ─────────────────────────────────────────
  # WORKFLOW ORCHESTRATOR
  # ─────────────────────────────────────────
  n8n:
    image: n8nio/n8n:latest
    container_name: ai-os-n8n
    restart: unless-stopped
    environment:
      DB_TYPE: postgresdb
      DB_POSTGRESDB_HOST: postgres
      DB_POSTGRESDB_PORT: 5432
      DB_POSTGRESDB_DATABASE: n8n_db
      DB_POSTGRESDB_USER: ${POSTGRES_USER:-ai_os}
      DB_POSTGRESDB_PASSWORD: ${POSTGRES_PASSWORD}
      N8N_ENCRYPTION_KEY: ${N8N_ENCRYPTION_KEY}
      N8N_HOST: ${N8N_HOST:-localhost}
      N8N_PORT: 5678
      N8N_PROTOCOL: http
      WEBHOOK_URL: http://${N8N_HOST:-localhost}:5678/
      EXECUTIONS_PROCESS: main
      N8N_LOG_LEVEL: info
      QUEUE_BULL_REDIS_HOST: redis
      QUEUE_BULL_REDIS_PORT: 6379
      QUEUE_BULL_REDIS_PASSWORD: ${REDIS_PASSWORD}
    volumes:
      - n8n_data:/home/node/.n8n
      - ./n8n/workflows:/workflows
    ports:
      - "5678:5678"
    networks:
      - ai-os-net
    depends_on:
      postgres:
        condition: service_healthy
      redis:
        condition: service_healthy

  # ─────────────────────────────────────────
  # LOCAL LLM SERVER
  # ─────────────────────────────────────────
  ollama:
    image: ollama/ollama:latest
    container_name: ai-os-ollama
    restart: unless-stopped
    volumes:
      - ollama_data:/root/.ollama
    ports:
      - "11434:11434"
    networks:
      - ai-os-net
    # Uncomment for GPU support:
    # deploy:
    #   resources:
    #     reservations:
    #       devices:
    #         - driver: nvidia
    #           count: 1
    #           capabilities: [gpu]

  # ─────────────────────────────────────────
  # CREWAI AGENT SERVICE
  # ─────────────────────────────────────────
  crewai:
    build:
      context: ./agents/crewai
      dockerfile: Dockerfile
    container_name: ai-os-crewai
    restart: unless-stopped
    environment:
      OPENAI_API_BASE: http://ollama:11434/v1
      OPENAI_API_KEY: ollama
      POSTGRES_URL: postgresql://${POSTGRES_USER:-ai_os}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB:-ai_os_db}
      REDIS_URL: redis://:${REDIS_PASSWORD}@redis:6379/0
    ports:
      - "8001:8001"
    networks:
      - ai-os-net
    depends_on:
      - postgres
      - redis
      - ollama

  # ─────────────────────────────────────────
  # HERMES AGENT SERVICE
  # ─────────────────────────────────────────
  hermes:
    build:
      context: ./agents/hermes
      dockerfile: Dockerfile
    container_name: ai-os-hermes
    restart: unless-stopped
    environment:
      OLLAMA_BASE_URL: http://ollama:11434
      POSTGRES_URL: postgresql://${POSTGRES_USER:-ai_os}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB:-ai_os_db}
      REDIS_URL: redis://:${REDIS_PASSWORD}@redis:6379/0
      MODEL_NAME: ${HERMES_MODEL:-hermes3:8b}
    ports:
      - "8002:8002"
    networks:
      - ai-os-net
    depends_on:
      - ollama
      - postgres

  # ─────────────────────────────────────────
  # OPENHANDS CODE AGENT
  # ─────────────────────────────────────────
  openhands:
    image: ghcr.io/all-hands-ai/openhands:latest
    container_name: ai-os-openhands
    restart: unless-stopped
    environment:
      SANDBOX_RUNTIME_CONTAINER_IMAGE: docker.all-hands.dev/all-hands-ai/runtime:0.47-nikolaik
      LLM_BASE_URL: http://ollama:11434/v1
      LLM_API_KEY: ollama
      LLM_MODEL: ${OPENHANDS_MODEL:-hermes3:8b}
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - ./projects:/opt/workspace
      - ./agents/openhands/config.toml:/app/config.toml
    ports:
      - "3000:3000"
    networks:
      - ai-os-net
    depends_on:
      - ollama

  # ─────────────────────────────────────────
  # PAIOS MCP SERVER
  # ─────────────────────────────────────────
  paios-mcp:
    build:
      context: ./mcp_servers
      dockerfile: Dockerfile
    container_name: ai-os-mcp
    restart: unless-stopped
    environment:
      N8N_BASE_URL: http://n8n:5678
      N8N_API_KEY: ${N8N_API_KEY}
      POSTGRES_URL: postgresql://${POSTGRES_USER:-ai_os}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB:-ai_os_db}
      HERMES_URL: http://hermes:8002
      CREWAI_URL: http://crewai:8001
      OPENHANDS_URL: http://openhands:3000
    ports:
      - "8000:8000"
    networks:
      - ai-os-net

  # ─────────────────────────────────────────
  # MONITORING STACK
  # ─────────────────────────────────────────
  prometheus:
    image: prom/prometheus:latest
    container_name: ai-os-prometheus
    restart: unless-stopped
    command:
      - '--config.file=/etc/prometheus/prometheus.yml'
      - '--storage.tsdb.path=/prometheus'
      - '--storage.tsdb.retention.time=15d'
    volumes:
      - ./monitoring/prometheus.yml:/etc/prometheus/prometheus.yml
    ports:
      - "9090:9090"
    networks:
      - ai-os-net

  grafana:
    image: grafana/grafana:latest
    container_name: ai-os-grafana
    restart: unless-stopped
    environment:
      GF_SECURITY_ADMIN_PASSWORD: ${GRAFANA_PASSWORD}
      GF_AUTH_ANONYMOUS_ENABLED: false
      GF_INSTALL_PLUGINS: grafana-loki-datasource
    volumes:
      - grafana_data:/var/lib/grafana
      - ./monitoring/grafana/datasources.yml:/etc/grafana/provisioning/datasources/datasources.yml
      - ./monitoring/grafana/dashboards:/etc/grafana/provisioning/dashboards
    ports:
      - "3001:3000"
    networks:
      - ai-os-net
    depends_on:
      - prometheus

  loki:
    image: grafana/loki:latest
    container_name: ai-os-loki
    restart: unless-stopped
    command: -config.file=/etc/loki/local-config.yaml
    volumes:
      - loki_data:/loki
      - ./monitoring/loki-config.yml:/etc/loki/local-config.yaml
    ports:
      - "3100:3100"
    networks:
      - ai-os-net

  cadvisor:
    image: gcr.io/cadvisor/cadvisor:latest
    container_name: ai-os-cadvisor
    restart: unless-stopped
    privileged: true
    volumes:
      - /:/rootfs:ro
      - /var/run:/var/run:ro
      - /sys:/sys:ro
      - /var/lib/docker/:/var/lib/docker:ro
    ports:
      - "8081:8080"
    networks:
      - ai-os-net
```

### 12.2 CrewAI Dockerfile

```dockerfile
# agents/crewai/Dockerfile
FROM python:3.11-slim

WORKDIR /app

RUN pip install --no-cache-dir \
    crewai \
    crewai-tools \
    fastapi \
    uvicorn \
    asyncpg \
    redis \
    psycopg2-binary

COPY . .

CMD ["uvicorn", "api:app", "--host", "0.0.0.0", "--port", "8001"]
```

### 12.3 Hermes Agent Dockerfile

```dockerfile
# agents/hermes/Dockerfile
FROM python:3.11-slim

WORKDIR /app

RUN pip install --no-cache-dir \
    fastapi \
    uvicorn \
    httpx \
    asyncpg \
    redis \
    pgvector \
    sentence-transformers

COPY . .

CMD ["uvicorn", "api:app", "--host", "0.0.0.0", "--port", "8002"]
```

### 12.4 Makefile Shortcuts

```makefile
# ~/ai-os/Makefile

.PHONY: up down restart logs pull-models status

up:
	docker compose up -d

down:
	docker compose down

restart:
	docker compose restart

logs:
	docker compose logs -f --tail=100

pull-models:
	docker exec ai-os-ollama ollama pull hermes3:8b
	docker exec ai-os-ollama ollama pull nomic-embed-text
	docker exec ai-os-ollama ollama pull llama3.2:3b

status:
	docker compose ps
	@echo "\n=== System Resources ==="
	docker stats --no-stream --format "table {{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}"

backup:
	./scripts/backup.sh

health:
	./scripts/health-check.sh

init-db:
	docker exec -i ai-os-postgres psql -U ai_os -d ai_os_db < database/init.sql

n8n-import:
	for f in n8n/workflows/*.json; do \
		curl -X POST http://localhost:5678/api/v1/workflows \
			-H "X-N8N-API-KEY: $(N8N_API_KEY)" \
			-H "Content-Type: application/json" \
			-d @$$f; \
	done
```

---

## 13. MCP Server Configuration

### 13.1 OpenCode Config File

```json
// ~/.config/opencode/config.json
{
  "model": "anthropic/claude-sonnet-4-5",
  "fallback_model": "ollama/hermes3:8b",
  "theme": "catppuccin",
  "mcpServers": {
    "paios": {
      "command": "python",
      "args": ["/home/user/ai-os/mcp_servers/paios_server.py"],
      "env": {
        "N8N_API_KEY": "${N8N_API_KEY}",
        "POSTGRES_URL": "postgresql://ai_os:${POSTGRES_PASSWORD}@localhost:5432/ai_os_db"
      }
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", 
               "postgresql://ai_os:${POSTGRES_PASSWORD}@localhost:5432/ai_os_db"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem",
               "/home/user/projects",
               "/home/user/ai-os/n8n/workflows"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  },
  "keybindings": {
    "submit": "ctrl+enter",
    "new_session": "ctrl+n",
    "toggle_sidebar": "ctrl+b"
  }
}
```

### 13.2 Custom PAIOS MCP Server — Full Implementation

```python
# mcp_servers/paios_server.py
import asyncio
import json
import os
from typing import Any
import httpx
import asyncpg
from mcp.server import Server
from mcp.server.stdio import stdio_server
import mcp.types as types

# Config from environment
N8N_BASE_URL = os.environ.get("N8N_BASE_URL", "http://localhost:5678")
N8N_API_KEY = os.environ.get("N8N_API_KEY", "")
POSTGRES_URL = os.environ.get("POSTGRES_URL", "")

server = Server("paios")
db_pool = None

async def get_db():
    global db_pool
    if db_pool is None:
        db_pool = await asyncpg.create_pool(POSTGRES_URL)
    return db_pool

@server.list_tools()
async def list_tools() -> list[types.Tool]:
    return [
        types.Tool(
            name="trigger_task",
            description="Send a task to the AI OS for execution by agents",
            inputSchema={
                "type": "object",
                "properties": {
                    "task": {"type": "string", "description": "Task description"},
                    "type": {
                        "type": "string",
                        "enum": ["code", "research", "plan", "write", "analyze"],
                        "default": "plan"
                    },
                    "priority": {"type": "integer", "default": 3, "minimum": 1, "maximum": 5},
                    "project": {"type": "string", "description": "Project name (optional)"}
                },
                "required": ["task"]
            }
        ),
        types.Tool(
            name="get_task",
            description="Get status and result of a task",
            inputSchema={
                "type": "object",
                "properties": {
                    "task_id": {"type": "string"}
                },
                "required": ["task_id"]
            }
        ),
        types.Tool(
            name="list_tasks",
            description="List recent tasks with their status",
            inputSchema={
                "type": "object",
                "properties": {
                    "status": {"type": "string", "enum": ["pending", "running", "done", "failed", "all"], "default": "all"},
                    "limit": {"type": "integer", "default": 10}
                }
            }
        ),
        types.Tool(
            name="search_memory",
            description="Search the AI OS knowledge base for relevant information",
            inputSchema={
                "type": "object",
                "properties": {
                    "query": {"type": "string"},
                    "limit": {"type": "integer", "default": 5},
                    "project": {"type": "string"}
                },
                "required": ["query"]
            }
        ),
        types.Tool(
            name="trigger_workflow",
            description="Trigger a specific n8n workflow by name",
            inputSchema={
                "type": "object",
                "properties": {
                    "workflow_name": {"type": "string"},
                    "payload": {"type": "object"}
                },
                "required": ["workflow_name"]
            }
        ),
        types.Tool(
            name="system_status",
            description="Get the current status of all PAIOS components",
            inputSchema={"type": "object", "properties": {}}
        )
    ]

@server.call_tool()
async def call_tool(name: str, arguments: dict[str, Any]) -> list[types.TextContent]:
    async with httpx.AsyncClient(timeout=30) as client:

        if name == "trigger_task":
            resp = await client.post(
                f"{N8N_BASE_URL}/webhook/task",
                json={
                    "task": arguments["task"],
                    "type": arguments.get("type", "plan"),
                    "priority": arguments.get("priority", 3),
                    "project": arguments.get("project", "default")
                },
                headers={"X-API-Key": N8N_API_KEY}
            )
            result = resp.json()
            return [types.TextContent(
                type="text",
                text=f"Task queued! ID: {result.get('task_id')}\nStatus: {result.get('status')}"
            )]

        elif name == "get_task":
            pool = await get_db()
            async with pool.acquire() as conn:
                row = await conn.fetchrow(
                    "SELECT * FROM task_queue WHERE task_id = $1",
                    arguments["task_id"]
                )
            if row:
                return [types.TextContent(type="text", text=json.dumps(dict(row), default=str, indent=2))]
            return [types.TextContent(type="text", text="Task not found")]

        elif name == "list_tasks":
            pool = await get_db()
            async with pool.acquire() as conn:
                status = arguments.get("status", "all")
                limit = arguments.get("limit", 10)
                if status == "all":
                    rows = await conn.fetch(
                        "SELECT task_id, type, status, priority, created_at, summary FROM task_queue ORDER BY created_at DESC LIMIT $1",
                        limit
                    )
                else:
                    rows = await conn.fetch(
                        "SELECT task_id, type, status, priority, created_at, summary FROM task_queue WHERE status=$1 ORDER BY created_at DESC LIMIT $2",
                        status, limit
                    )
            tasks = [dict(r) for r in rows]
            return [types.TextContent(type="text", text=json.dumps(tasks, default=str, indent=2))]

        elif name == "search_memory":
            pool = await get_db()
            async with pool.acquire() as conn:
                # Use pgvector similarity search
                rows = await conn.fetch("""
                    SELECT content, memory_type, source, project_id,
                           1 - (embedding <=> (
                               SELECT embedding FROM memory_store 
                               WHERE content = $1 LIMIT 1
                           )) as similarity
                    FROM memory_store
                    ORDER BY embedding <=> (
                        SELECT embedding FROM memory_store WHERE content = $1 LIMIT 1
                    )
                    LIMIT $2
                """, arguments["query"], arguments.get("limit", 5))
            results = [dict(r) for r in rows]
            return [types.TextContent(type="text", text=json.dumps(results, default=str, indent=2))]

        elif name == "system_status":
            status = {}
            services = {
                "n8n": f"{N8N_BASE_URL}/healthz",
                "hermes": "http://hermes:8002/health",
                "crewai": "http://crewai:8001/health",
                "openhands": "http://openhands:3000/api/health"
            }
            for svc, url in services.items():
                try:
                    r = await client.get(url, timeout=3)
                    status[svc] = "✅ online" if r.status_code == 200 else f"⚠️ {r.status_code}"
                except Exception:
                    status[svc] = "❌ offline"
            return [types.TextContent(type="text", text=json.dumps(status, indent=2))]

async def main():
    async with stdio_server() as (read, write):
        await server.run(read, write, InitializationOptions(
            server_name="paios",
            server_version="1.0.0",
            capabilities=server.get_capabilities(
                notification_options=None,
                experimental_capabilities={}
            )
        ))

if __name__ == "__main__":
    asyncio.run(main())
```

---

## 14. Environment Variables

```bash
# ~/ai-os/.env
# ─────────────────────────────────────
# SECURITY: Never commit this file to git
# Copy .env.example to .env and fill in values
# ─────────────────────────────────────

# ── PostgreSQL ──────────────────────
POSTGRES_USER=ai_os
POSTGRES_PASSWORD=change_me_strong_password_here
POSTGRES_DB=ai_os_db

# ── Redis ───────────────────────────
REDIS_PASSWORD=change_me_redis_password

# ── n8n ─────────────────────────────
N8N_ENCRYPTION_KEY=change_me_32_char_encryption_key_
N8N_HOST=localhost
N8N_API_KEY=change_me_n8n_api_key

# ── Ollama Models ───────────────────
HERMES_MODEL=hermes3:8b
OPENHANDS_MODEL=hermes3:8b
EMBED_MODEL=nomic-embed-text

# ── GitHub ──────────────────────────
GITHUB_TOKEN=ghp_your_github_personal_access_token
GITHUB_USERNAME=your_username

# ── Notion (Optional) ───────────────
NOTION_API_KEY=secret_your_notion_integration_token
NOTION_DATABASE_ID=your_notion_database_id

# ── Monitoring ──────────────────────
GRAFANA_PASSWORD=change_me_grafana_admin_password

# ── External LLMs (Optional) ────────
# Only needed if not using Ollama exclusively
ANTHROPIC_API_KEY=sk-ant-your-key-here
OPENAI_API_KEY=sk-your-key-here

# ── App Settings ────────────────────
LOG_LEVEL=info
ENVIRONMENT=development
TZ=Asia/Kolkata
```

---

## 15. Database Schema

```sql
-- database/init.sql

-- Enable required extensions
CREATE EXTENSION IF NOT EXISTS vector;
CREATE EXTENSION IF NOT EXISTS pg_stat_statements;
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

-- ─────────────────────────────────────────────────
-- CORE TABLES
-- ─────────────────────────────────────────────────

-- Projects
CREATE TABLE IF NOT EXISTS projects (
    project_id    UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
    name          TEXT NOT NULL UNIQUE,
    description   TEXT,
    status        TEXT DEFAULT 'active' CHECK (status IN ('active','paused','done','archived')),
    notion_page_id TEXT,
    github_repo   TEXT,
    metadata      JSONB DEFAULT '{}',
    created_at    TIMESTAMPTZ DEFAULT NOW(),
    updated_at    TIMESTAMPTZ DEFAULT NOW()
);

-- Task Queue (the heart of orchestration)
CREATE TABLE IF NOT EXISTS task_queue (
    task_id       UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
    project_id    UUID REFERENCES projects(project_id),
    parent_task_id UUID REFERENCES task_queue(task_id),
    type          TEXT NOT NULL CHECK (type IN ('code','research','plan','write','analyze','review','notify')),
    title         TEXT NOT NULL,
    description   TEXT,
    priority      INTEGER DEFAULT 3 CHECK (priority BETWEEN 1 AND 5),
    status        TEXT DEFAULT 'pending' CHECK (status IN ('pending','running','done','failed','cancelled')),
    assigned_to   TEXT,                    -- agent name
    payload       JSONB DEFAULT '{}',      -- input data
    result        JSONB,                   -- output data
    summary       TEXT,                    -- human-readable result summary
    error_message TEXT,
    started_at    TIMESTAMPTZ,
    completed_at  TIMESTAMPTZ,
    created_at    TIMESTAMPTZ DEFAULT NOW(),
    retry_count   INTEGER DEFAULT 0,
    max_retries   INTEGER DEFAULT 3
);

-- Vector Memory Store
CREATE TABLE IF NOT EXISTS memory_store (
    memory_id     UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
    project_id    UUID REFERENCES projects(project_id),
    task_id       UUID REFERENCES task_queue(task_id),
    content       TEXT NOT NULL,
    embedding     vector(768),             -- nomic-embed-text dimension
    memory_type   TEXT DEFAULT 'general'   -- technical_fact, decision, research, code, conversation
                  CHECK (memory_type IN ('technical_fact','decision','research','code','conversation','general')),
    source        TEXT,                    -- which agent created this
    importance    FLOAT DEFAULT 0.5,       -- 0-1 importance score
    access_count  INTEGER DEFAULT 0,
    last_accessed TIMESTAMPTZ,
    created_at    TIMESTAMPTZ DEFAULT NOW(),
    expires_at    TIMESTAMPTZ              -- null = never expires
);

-- Agent Execution Logs
CREATE TABLE IF NOT EXISTS agent_logs (
    log_id        UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
    task_id       UUID REFERENCES task_queue(task_id),
    agent_name    TEXT NOT NULL,
    action        TEXT NOT NULL,
    reasoning     TEXT,
    tool_calls    JSONB,
    tokens_used   INTEGER,
    duration_ms   INTEGER,
    timestamp     TIMESTAMPTZ DEFAULT NOW()
);

-- n8n Workflow Execution Tracking
CREATE TABLE IF NOT EXISTS workflow_runs (
    run_id        UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
    workflow_name TEXT NOT NULL,
    n8n_exec_id   TEXT,
    task_id       UUID REFERENCES task_queue(task_id),
    status        TEXT DEFAULT 'running',
    started_at    TIMESTAMPTZ DEFAULT NOW(),
    completed_at  TIMESTAMPTZ,
    error         TEXT
);

-- Knowledge Base (structured facts)
CREATE TABLE IF NOT EXISTS knowledge_base (
    kb_id         UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
    project_id    UUID REFERENCES projects(project_id),
    title         TEXT NOT NULL,
    content       TEXT NOT NULL,
    embedding     vector(768),
    category      TEXT,
    tags          TEXT[],
    source_url    TEXT,
    notion_page_id TEXT,
    created_at    TIMESTAMPTZ DEFAULT NOW(),
    updated_at    TIMESTAMPTZ DEFAULT NOW()
);

-- ─────────────────────────────────────────────────
-- INDEXES
-- ─────────────────────────────────────────────────

-- Task queue indexes
CREATE INDEX idx_task_status ON task_queue(status);
CREATE INDEX idx_task_assigned ON task_queue(assigned_to, status);
CREATE INDEX idx_task_project ON task_queue(project_id);
CREATE INDEX idx_task_created ON task_queue(created_at DESC);

-- Vector similarity search indexes (HNSW for speed)
CREATE INDEX idx_memory_embedding ON memory_store 
    USING hnsw (embedding vector_cosine_ops)
    WITH (m = 16, ef_construction = 64);

CREATE INDEX idx_kb_embedding ON knowledge_base
    USING hnsw (embedding vector_cosine_ops)
    WITH (m = 16, ef_construction = 64);

-- ─────────────────────────────────────────────────
-- HELPER FUNCTIONS
-- ─────────────────────────────────────────────────

-- Function to store a memory
CREATE OR REPLACE FUNCTION store_memory(
    p_content TEXT,
    p_memory_type TEXT DEFAULT 'general',
    p_source TEXT DEFAULT 'system',
    p_project_id UUID DEFAULT NULL,
    p_task_id UUID DEFAULT NULL,
    p_importance FLOAT DEFAULT 0.5
) RETURNS UUID AS $$
DECLARE
    v_memory_id UUID;
BEGIN
    INSERT INTO memory_store (content, memory_type, source, project_id, task_id, importance)
    VALUES (p_content, p_memory_type, p_source, p_project_id, p_task_id, p_importance)
    RETURNING memory_id INTO v_memory_id;
    RETURN v_memory_id;
END;
$$ LANGUAGE plpgsql;

-- Function to get next task for an agent
CREATE OR REPLACE FUNCTION claim_next_task(p_agent_name TEXT)
RETURNS task_queue AS $$
DECLARE
    v_task task_queue;
BEGIN
    SELECT * INTO v_task
    FROM task_queue
    WHERE status = 'pending'
      AND (assigned_to = p_agent_name OR assigned_to IS NULL)
    ORDER BY priority DESC, created_at ASC
    LIMIT 1
    FOR UPDATE SKIP LOCKED;

    IF FOUND THEN
        UPDATE task_queue
        SET status = 'running',
            assigned_to = p_agent_name,
            started_at = NOW()
        WHERE task_id = v_task.task_id;
    END IF;
    RETURN v_task;
END;
$$ LANGUAGE plpgsql;

-- ─────────────────────────────────────────────────
-- VIEWS
-- ─────────────────────────────────────────────────

CREATE OR REPLACE VIEW v_task_dashboard AS
SELECT
    t.task_id,
    t.type,
    t.title,
    t.status,
    t.priority,
    t.assigned_to,
    p.name AS project_name,
    t.created_at,
    t.completed_at,
    EXTRACT(EPOCH FROM (COALESCE(t.completed_at, NOW()) - t.started_at)) AS duration_seconds
FROM task_queue t
LEFT JOIN projects p ON t.project_id = p.project_id
ORDER BY t.created_at DESC;

CREATE OR REPLACE VIEW v_agent_stats AS
SELECT
    assigned_to AS agent,
    COUNT(*) FILTER (WHERE status = 'done') AS completed,
    COUNT(*) FILTER (WHERE status = 'failed') AS failed,
    COUNT(*) FILTER (WHERE status = 'running') AS running,
    AVG(EXTRACT(EPOCH FROM (completed_at - started_at))) FILTER (WHERE status = 'done') AS avg_duration_sec
FROM task_queue
WHERE created_at > NOW() - INTERVAL '7 days'
GROUP BY assigned_to;
```

---

## 16. Workflow Examples

### 16.1 Example: "Build me a REST API" Workflow

```
User in OpenCode:
"Build a FastAPI CRUD API for a todo app with PostgreSQL"

↓ OpenCode calls PAIOS MCP tool: trigger_task

↓ n8n Webhook receives:
{
  "task": "Build FastAPI CRUD API for todo app",
  "type": "code",
  "priority": 4
}

↓ n8n → Hermes Agent (Planning)
  Hermes responds with plan:
  {
    "subtasks": [
      {"id": 1, "title": "Design DB schema", "agent": "hermes"},
      {"id": 2, "title": "Write Pydantic models", "agent": "openhands"},
      {"id": 3, "title": "Write CRUD endpoints", "agent": "openhands"},
      {"id": 4, "title": "Write tests", "agent": "openhands"},
      {"id": 5, "title": "Write README", "agent": "crewai"}
    ]
  }

↓ n8n inserts subtasks into task_queue

↓ n8n triggers OpenHands for subtask 2:
  OpenHands writes:
  - models.py
  - database.py
  - main.py
  - test_main.py
  → Commits to GitHub branch feature/todo-api

↓ n8n triggers CrewAI for README:
  Writer agent creates comprehensive README.md
  → Saves to Notion + commits to GitHub

↓ All subtasks complete
↓ n8n sends completion summary to Redis
↓ OpenCode polls and displays: "API complete! 4 files created, tests passing ✅"
```

### 16.2 Example: Daily Research Digest (Cron Workflow)

```yaml
# n8n cron workflow (daily at 8 AM)
Trigger: Schedule (cron: 0 8 * * *)
  │
  ▼
HTTP Node: GET recent GitHub activity for tracked repos
  │
  ▼
Hermes Agent: Summarize changes and their significance
  │
  ▼
CrewAI Research Crew: Find related news/blog posts
  │
  ▼
Merge Node: Combine GitHub + research summaries
  │
  ▼
PostgreSQL Node: Store full report
  │
  ▼
Notion Node: Create daily digest page
  │
  ▼
Redis Publish: "daily_digest_ready"
  │
  ▼
(OpenCode picks up on next user interaction)
```

### 16.3 Example: GitHub PR Auto-Review

```
GitHub PR opened → GitHub webhook → n8n
  │
  ▼
n8n fetches PR diff via GitHub API
  │
  ▼
CrewAI Code Review Crew:
  - Security Agent: Check for vulnerabilities
  - Style Agent: Check code style
  - Logic Agent: Check for bugs/edge cases
  │
  ▼
n8n posts review comment to GitHub PR
  │
  ▼
Store review in PostgreSQL
  │
  ▼
Update Notion project page
```

### 16.4 n8n Workflow JSON Snippet (Master Router)

```json
{
  "name": "PAIOS Master Task Router",
  "nodes": [
    {
      "name": "Task Webhook",
      "type": "n8n-nodes-base.webhook",
      "parameters": {
        "path": "task",
        "responseMode": "responseNode",
        "httpMethod": "POST"
      }
    },
    {
      "name": "Parse and Validate",
      "type": "n8n-nodes-base.code",
      "parameters": {
        "jsCode": "const task = $input.first().json;\nif (!task.task) throw new Error('task field required');\ntask.task_id = require('crypto').randomUUID();\ntask.status = 'pending';\ntask.created_at = new Date().toISOString();\nreturn [{ json: task }];"
      }
    },
    {
      "name": "Route by Type",
      "type": "n8n-nodes-base.switch",
      "parameters": {
        "value": "={{ $json.type }}",
        "rules": {
          "rules": [
            {"value": "code", "output": 0},
            {"value": "research", "output": 1},
            {"value": "plan", "output": 2}
          ]
        },
        "fallbackOutput": 2
      }
    }
  ]
}
```

---

## 17. Installation Roadmap

### Phase 0: Prerequisites (Day 1)

```bash
# 1. Install Docker Desktop (or Docker Engine on Linux)
curl -fsSL https://get.docker.com | bash
sudo usermod -aG docker $USER
newgrp docker

# 2. Install Node.js (for MCP servers)
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo bash
sudo apt install nodejs -y

# 3. Install OpenCode
curl -fsSL https://opencode.ai/install | bash

# 4. Install Python 3.11+
sudo apt install python3.11 python3.11-pip python3.11-venv -y

# 5. Clone PAIOS repo
git clone https://github.com/yourusername/ai-os.git ~/ai-os
cd ~/ai-os
cp .env.example .env
# Edit .env with your values
nano .env
```

### Phase 1: Core Infrastructure (Day 1–2)

```bash
cd ~/ai-os

# Start database and cache
docker compose up -d postgres redis

# Wait for postgres to be ready
sleep 5

# Initialize database schema
make init-db

# Verify
docker exec ai-os-postgres psql -U ai_os -d ai_os_db -c "\dt"
```

**Expected output:** List of tables: task_queue, memory_store, projects, agent_logs, etc.

### Phase 2: Local LLM Setup (Day 2)

```bash
# Start Ollama
docker compose up -d ollama

# Pull required models (this takes time — ~5GB total)
make pull-models

# Verify models are loaded
docker exec ai-os-ollama ollama list

# Test inference
docker exec ai-os-ollama ollama run hermes3:8b "Hello! Are you working?"

# Test embedding model
curl http://localhost:11434/api/embeddings -d '{
  "model": "nomic-embed-text",
  "prompt": "test embedding"
}'
```

**Recommended models by RAM:**

| RAM | Models |
|-----|--------|
| 8GB | hermes3:3b, nomic-embed-text |
| 16GB | hermes3:8b, nomic-embed-text, llama3.2:3b |
| 32GB+ | hermes3:8b, llama3.1:70b (quantized), nomic-embed-text |

### Phase 3: n8n Setup (Day 3)

```bash
# Start n8n
docker compose up -d n8n

# Open browser
xdg-open http://localhost:5678

# In n8n UI:
# 1. Create admin account
# 2. Settings → API → Create API Key → copy to .env N8N_API_KEY
# 3. Import workflows:
make n8n-import

# Test webhook
curl -X POST http://localhost:5678/webhook/task \
  -H "Content-Type: application/json" \
  -d '{"task": "test task", "type": "plan", "priority": 3}'
```

### Phase 4: Agent Services (Day 4)

```bash
# Build and start CrewAI
docker compose up -d crewai

# Test CrewAI
curl http://localhost:8001/health
curl -X POST http://localhost:8001/crew/research \
  -H "Content-Type: application/json" \
  -d '{"topic": "vector databases", "depth": "shallow"}'

# Build and start Hermes
docker compose up -d hermes

# Test Hermes
curl http://localhost:8002/health
curl -X POST http://localhost:8002/plan \
  -H "Content-Type: application/json" \
  -d '{"task": "Build a REST API", "context": {}}'

# Start OpenHands
docker compose up -d openhands
xdg-open http://localhost:3000
```

### Phase 5: OpenCode + MCP (Day 5)

```bash
# Install MCP server dependencies
npm install -g @modelcontextprotocol/server-postgres
npm install -g @modelcontextprotocol/server-github
npm install -g @modelcontextprotocol/server-filesystem
npm install -g @modelcontextprotocol/server-memory

# Install PAIOS MCP server dependencies
cd ~/ai-os/mcp_servers
pip3 install -r requirements.txt

# Copy OpenCode config
cp opencode.config.json ~/.config/opencode/config.json
# Edit to add your API keys

# Start OpenCode
opencode

# Test MCP connection (inside OpenCode)
# Type: "What is the status of all PAIOS services?"
```

### Phase 6: Monitoring (Day 6)

```bash
# Start monitoring stack
docker compose up -d prometheus grafana loki cadvisor

# Open Grafana
xdg-open http://localhost:3001
# Login: admin / your GRAFANA_PASSWORD

# Import dashboards (pre-built JSON files in monitoring/grafana/dashboards/)
# Grafana → Dashboards → Import → Upload JSON
```

### Phase 7: Full Stack Verification (Day 7)

```bash
# Run full health check
make health

# Expected output:
# ✅ PostgreSQL: online
# ✅ Redis: online  
# ✅ n8n: online
# ✅ Ollama: online (models: hermes3:8b, nomic-embed-text)
# ✅ CrewAI: online
# ✅ Hermes: online
# ✅ OpenHands: online
# ✅ Grafana: online
# ✅ Prometheus: online

# Run end-to-end test
cd ~/ai-os
python3 scripts/e2e_test.py
```

---

## 18. Security Practices

### 18.1 Secrets Management

```bash
# NEVER commit .env to git
echo ".env" >> .gitignore
echo "data/" >> .gitignore

# Use strong, unique passwords for each service
openssl rand -base64 32  # Generate strong passwords

# Rotate secrets every 90 days
# Use a password manager to store them
```

### 18.2 Network Security

```yaml
# In docker-compose.yml — never expose internal services to host
# BAD:
postgres:
  ports:
    - "5432:5432"  # exposes to all interfaces

# GOOD (development only — change for production):
postgres:
  ports:
    - "127.0.0.1:5432:5432"  # only localhost

# For VPS deployment — use firewall rules:
# ufw allow 22/tcp    # SSH only
# ufw allow 80/tcp    # Nginx reverse proxy
# ufw allow 443/tcp   # HTTPS
# ufw deny all        # Block everything else
```

### 18.3 n8n Security

```bash
# Enable n8n authentication
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=strong_password

# Use webhook authentication
# In n8n: add Header Auth to all webhooks
# Header: X-API-Key: ${N8N_API_KEY}
```

### 18.4 PostgreSQL Security

```sql
-- Create a read-only user for monitoring
CREATE USER ai_os_readonly WITH PASSWORD 'readonly_password';
GRANT CONNECT ON DATABASE ai_os_db TO ai_os_readonly;
GRANT USAGE ON SCHEMA public TO ai_os_readonly;
GRANT SELECT ON ALL TABLES IN SCHEMA public TO ai_os_readonly;

-- Limit agent user permissions (principle of least privilege)
REVOKE CREATE ON SCHEMA public FROM ai_os;
```

### 18.5 GitHub Token Scopes

```
Required scopes for PAIOS GitHub token:
✅ repo (full repo access)
✅ workflow (to trigger GitHub Actions)
❌ admin:org (NOT needed)
❌ delete_repo (NOT needed)
```

### 18.6 OpenHands Sandboxing

OpenHands runs code in sandboxed Docker containers — never on the host directly. This is the default behavior. Verify:

```bash
# Confirm sandbox is enabled in config
cat agents/openhands/config.toml | grep sandbox
# sandbox_container_image = "docker.all-hands.dev/all-hands-ai/runtime:latest"
```

---

## 19. Backup Strategy

### 19.1 Automated Backup Script

```bash
#!/bin/bash
# scripts/backup.sh

BACKUP_DIR=~/ai-os-backups
DATE=$(date +%Y%m%d_%H%M%S)
BACKUP_PATH="$BACKUP_DIR/$DATE"

mkdir -p "$BACKUP_PATH"

echo "🔄 Starting PAIOS backup: $DATE"

# 1. PostgreSQL dump
echo "📦 Backing up PostgreSQL..."
docker exec ai-os-postgres pg_dump \
    -U ai_os \
    -d ai_os_db \
    --format=custom \
    --compress=9 \
    > "$BACKUP_PATH/postgres.dump"

# 2. n8n data
echo "📦 Backing up n8n..."
docker run --rm \
    -v ai-os_n8n_data:/source \
    -v "$BACKUP_PATH":/backup \
    alpine tar czf /backup/n8n_data.tar.gz -C /source .

# 3. n8n workflows (via API)
echo "📦 Exporting n8n workflows..."
curl -s http://localhost:5678/api/v1/workflows \
    -H "X-N8N-API-KEY: $N8N_API_KEY" \
    > "$BACKUP_PATH/n8n_workflows.json"

# 4. Environment variables (without secrets — just keys)
echo "📦 Backing up config structure..."
cat .env | sed 's/=.*/=REDACTED/' > "$BACKUP_PATH/env_structure.txt"

# 5. Ollama models list
echo "📦 Recording Ollama models..."
docker exec ai-os-ollama ollama list > "$BACKUP_PATH/ollama_models.txt"

# 6. Git commit all project files
echo "📦 Committing to git..."
cd ~/ai-os
git add -A
git commit -m "Auto-backup: $DATE" || true
git push origin main || true

# 7. Compress backup
echo "🗜️  Compressing..."
tar czf "$BACKUP_DIR/paios_backup_$DATE.tar.gz" -C "$BACKUP_DIR" "$DATE"
rm -rf "$BACKUP_PATH"

# 8. Keep only last 7 days of backups
find "$BACKUP_DIR" -name "*.tar.gz" -mtime +7 -delete

echo "✅ Backup complete: paios_backup_$DATE.tar.gz"
```

### 19.2 Restore Script

```bash
#!/bin/bash
# scripts/restore.sh BACKUP_FILE
BACKUP_FILE=$1
BACKUP_DIR=/tmp/paios_restore

mkdir -p "$BACKUP_DIR"
tar xzf "$BACKUP_FILE" -C "$BACKUP_DIR"

# Restore PostgreSQL
docker exec -i ai-os-postgres pg_restore \
    -U ai_os \
    -d ai_os_db \
    --clean \
    < "$BACKUP_DIR/postgres.dump"

# Restore n8n data
docker run --rm \
    -v ai-os_n8n_data:/dest \
    -v "$BACKUP_DIR":/backup \
    alpine sh -c "cd /dest && tar xzf /backup/n8n_data.tar.gz"

echo "✅ Restore complete"
```

### 19.3 Backup Schedule (Add to crontab)

```bash
# crontab -e
# Daily backup at 2 AM
0 2 * * * /home/user/ai-os/scripts/backup.sh >> /var/log/paios-backup.log 2>&1

# Weekly full backup on Sundays
0 3 * * 0 /home/user/ai-os/scripts/full_backup.sh >> /var/log/paios-backup.log 2>&1
```

---

## 20. Troubleshooting Guide

### 20.1 Common Issues

#### Docker services not starting

```bash
# Check service logs
docker compose logs postgres
docker compose logs n8n

# Check disk space
df -h

# Check memory
free -h

# Restart specific service
docker compose restart n8n

# Nuclear option — full restart
docker compose down && docker compose up -d
```

#### Ollama models are slow

```bash
# Check if running on CPU (expected on laptop without GPU)
docker exec ai-os-ollama ollama ps

# Use smaller models on 8GB RAM
docker exec ai-os-ollama ollama pull hermes3:3b

# Check VRAM usage (if GPU available)
nvidia-smi
```

#### PostgreSQL connection refused

```bash
# Check if container is healthy
docker inspect ai-os-postgres | grep Health

# Check port binding
netstat -tlpn | grep 5432

# Connect manually to test
docker exec -it ai-os-postgres psql -U ai_os -d ai_os_db
```

#### n8n webhook not responding

```bash
# Check n8n is running
curl http://localhost:5678/healthz

# Check webhook path (must match exactly)
curl -X POST http://localhost:5678/webhook/task \
  -H "Content-Type: application/json" \
  -d '{"task": "test"}'

# Check n8n execution logs
# n8n UI → Executions → view failed executions
```

#### pgvector search returns empty results

```bash
# Check embeddings are stored
docker exec ai-os-postgres psql -U ai_os -d ai_os_db \
  -c "SELECT COUNT(*) FROM memory_store WHERE embedding IS NOT NULL;"

# If zero, the embedding service isn't writing
# Check Hermes agent logs
docker compose logs hermes | grep embed
```

#### MCP server not connecting to OpenCode

```bash
# Test MCP server standalone
python3 ~/ai-os/mcp_servers/paios_server.py

# Check OpenCode config
cat ~/.config/opencode/config.json

# Verify environment variables are set
env | grep N8N_API_KEY
env | grep POSTGRES_PASSWORD

# Check OpenCode logs
opencode --debug
```

#### CrewAI timeout on tasks

```bash
# Increase Ollama timeout
# In agents/crewai/api.py:
# timeout=120  # increase from default 30

# Use a faster/smaller model for routing
HERMES_MODEL=hermes3:3b  # in .env

# Check Ollama performance
curl http://localhost:11434/api/generate \
  -d '{"model": "hermes3:3b", "prompt": "say hi", "stream": false}'
```

### 20.2 Performance Tuning for Laptops

```bash
# Limit Docker memory usage
# In docker-compose.yml, add to each service:
deploy:
  resources:
    limits:
      memory: 2G

# Ollama: reduce context window for speed
# In .env:
OLLAMA_NUM_CTX=2048  # default is 4096

# PostgreSQL: tune for laptop (in postgres container)
# Add to docker-compose postgres service:
command: >
  postgres
  -c shared_buffers=256MB
  -c effective_cache_size=512MB
  -c work_mem=16MB
  -c max_connections=20

# Use Hermes 3B instead of 8B on 8GB RAM machines
HERMES_MODEL=hermes3:3b
```

---

## 21. Scaling Path

### Laptop → Home Server → VPS

```
Phase 1: Laptop (Current)
├── RAM: 8-16 GB
├── Storage: 256-512 GB SSD
├── Models: Hermes 3B-8B quantized
├── Concurrency: 1-2 parallel tasks
└── Availability: When laptop is on

Phase 2: Home Server
├── Hardware: Old PC / Mac Mini / Mini PC
├── RAM: 32-64 GB
├── Storage: 1-2 TB NVMe
├── Models: Llama3.1 70B quantized, multiple models
├── Concurrency: 5-10 parallel tasks
├── Availability: 24/7
└── Changes needed: Update .env POSTGRES_HOST, etc.

Phase 3: VPS (Cloud)
├── Provider: Hetzner (cheapest), Vultr, DigitalOcean
├── RAM: 16-32 GB
├── GPU: Optional (Hetzner GPU servers)
├── Models: Mix local + API
├── Concurrency: 10+ parallel tasks
├── Availability: 99.9% uptime
└── Changes needed: Add Nginx, SSL, firewall rules
```

### Laptop → Home Server Migration

```bash
# 1. On laptop: create full backup
make backup

# 2. Copy backup to home server
scp ~/ai-os-backups/paios_backup_latest.tar.gz user@homeserver:~/

# 3. On home server: clone repo and restore
git clone https://github.com/yourusername/ai-os.git ~/ai-os
cd ~/ai-os
cp .env.example .env
# Edit .env with production values

docker compose up -d postgres redis
./scripts/restore.sh ~/paios_backup_latest.tar.gz

docker compose up -d  # start everything

# 4. Update DNS (if self-hosting domain)
# Point ai-os.local → home server IP
```

### Adding Nginx Reverse Proxy (VPS/Home Server)

```nginx
# /etc/nginx/sites-available/ai-os
server {
    listen 80;
    server_name ai-os.yourdomain.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl;
    server_name ai-os.yourdomain.com;

    ssl_certificate /etc/letsencrypt/live/ai-os.yourdomain.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/ai-os.yourdomain.com/privkey.pem;

    # n8n
    location /n8n/ {
        proxy_pass http://localhost:5678/;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }

    # Grafana
    location /grafana/ {
        proxy_pass http://localhost:3001/;
    }

    # OpenHands
    location /openhands/ {
        proxy_pass http://localhost:3000/;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
    }

    # PAIOS API
    location /api/ {
        proxy_pass http://localhost:8000/;
    }
}
```

### Adding GPU Support (Home Server / VPS)

```yaml
# In docker-compose.yml
ollama:
  image: ollama/ollama:latest
  deploy:
    resources:
      reservations:
        devices:
          - driver: nvidia
            count: 1
            capabilities: [gpu]
  environment:
    - NVIDIA_VISIBLE_DEVICES=all

# Install NVIDIA Container Toolkit on host:
# curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg
# ... (follow official NVIDIA docs)
```

### Resource Requirements by Scale

| Scale | RAM | CPU | Storage | Monthly Cost |
|-------|-----|-----|---------|-------------|
| Laptop (dev) | 8 GB | 4 cores | 50 GB | $0 |
| Laptop (full) | 16 GB | 8 cores | 100 GB | $0 |
| Home Server | 32 GB | 8+ cores | 500 GB | ~$5/mo (electricity) |
| Small VPS | 16 GB | 6 vCPUs | 200 GB | ~$30/mo (Hetzner) |
| GPU VPS | 32 GB | 8 vCPUs + GPU | 500 GB | ~$100/mo |

---

## Additional Free Tools to Extend PAIOS

All of the following are **free, open-source, self-hostable, zero licensing cost:**

| Tool | Purpose | Docker Image |
|------|---------|-------------|
| **AppFlowy** | Self-hosted Notion replacement | `appflowyinc/appflowy_cloud` |
| **Gitea** | Self-hosted GitHub alternative | `gitea/gitea` |
| **MinIO** | S3-compatible file storage | `minio/minio` |
| **Qdrant** | Dedicated vector database | `qdrant/qdrant` |
| **SearXNG** | Self-hosted web search | `searxng/searxng` |
| **Memos** | Quick notes / scratchpad | `neosmemo/memos` |
| **Excalidraw** | Whiteboard / diagrams | `excalidraw/excalidraw` |
| **Portainer** | Docker management UI | `portainer/portainer-ce` |
| **Traefik** | Reverse proxy with auto-SSL | `traefik` |
| **Uptime Kuma** | Service uptime monitoring | `louislam/uptime-kuma` |

---

## Quick Reference Card

```
🚀 START EVERYTHING:    cd ~/ai-os && make up
🔍 CHECK STATUS:        make status
📋 VIEW LOGS:           make logs
🛑 STOP EVERYTHING:     make down
💾 BACKUP:              make backup
🩺 HEALTH CHECK:        make health
🤖 PULL NEW MODELS:     make pull-models
🗄️ DATABASE SHELL:      docker exec -it ai-os-postgres psql -U ai_os -d ai_os_db
📊 OPEN GRAFANA:        http://localhost:3001
🔄 OPEN N8N:            http://localhost:5678
🤝 OPEN OPENHANDS:      http://localhost:3000
🧠 OLLAMA API:          http://localhost:11434
```

---

*Document version: 1.0.0 | Generated for PAIOS — Personal AI Operating System*  
*Stack: OpenCode · Hermes · n8n · CrewAI · OpenHands · PostgreSQL · Docker · GitHub*  
*License: MIT — Free to use, modify, and distribute*
