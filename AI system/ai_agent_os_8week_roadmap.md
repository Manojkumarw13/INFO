# AI Agent Operating System: 8-Week Windows Roadmap
### Build · Operate · Extend · Contribute — Zero to Production

> **Stack:** OpenCode · Hermes Agent · CrewAI · n8n · OpenHands · PostgreSQL/pgvector · Docker · MCP Servers · LangGraph · LiteLLM · FastAPI · Playwright · Redis · Obsidian · Notion · GitHub Actions · WSL2
> **Constraint:** API-based models only · Windows host · Python 3.11+ · Zero local-model inference

---

## Table of Contents

1. [Foundation](#1-foundation)
2. [AI Agent Fundamentals](#2-ai-agent-fundamentals)
3. [OpenCode Ecosystem](#3-opencode-ecosystem)
4. [MCP Servers](#4-mcp-servers)
5. [Skills, Tools & Plugins](#5-skills-tools--plugins)
6. [CrewAI & Multi-Agent Systems](#6-crewai--multi-agent-systems)
7. [Hermes Agent](#7-hermes-agent)
8. [n8n Automation](#8-n8n-automation)
9. [OpenHands](#9-openhands)
10. [Docker & Infrastructure](#10-docker--infrastructure)
11. [PostgreSQL & Agent Memory](#11-postgresql--agent-memory)
12. [Obsidian Knowledge Management](#12-obsidian-knowledge-management)
13. [Notion Knowledge Management](#13-notion-knowledge-management)
14. [RAG Systems](#14-rag-systems)
15. [Browser Automation](#15-browser-automation)
16. [Computer Use Agents](#16-computer-use-agents)
17. [GitHub & Open Source Contribution](#17-github--open-source-contribution)
18. [Advanced System Architecture](#18-advanced-system-architecture)
19. [Production Deployment](#19-production-deployment)
20. [Projects](#20-projects)
21. [8-Week Study Plan](#21-8-week-study-plan)
22. [Architecture Diagrams](#22-architecture-diagrams)
23. [Final System Blueprint](#23-final-production-grade-system-blueprint)
24. [Contribution Roadmaps](#24-open-source-contribution-roadmaps)

---

## HOW TO USE THIS DOCUMENT

Load this file into **NotebookLM** as a source. Every URL is a standalone resource that NotebookLM can retrieve and index. Work through the 8-Week Study Plan chronologically. The category sections are reference material — return to them when a week's activities require deeper study.

**NotebookLM compatibility notes:**
- All YouTube links resolve to transcribable video pages
- All GitHub links resolve to README/docs pages
- All documentation links are static HTML or Markdown
- Avoid pasting raw `.ipynb` notebook URLs — link to the GitHub repo page instead

---

## 1. Foundation

**Priority:** Mandatory | **Difficulty:** Beginner | **Study Time:** 10–14 hours

### What you must know before Week 1

The entire stack runs inside WSL2 on Windows. Docker Desktop bridges WSL2 and Windows. Python virtual environments (via `uv`) isolate each component. Every API call goes through LiteLLM, which normalises provider differences. This foundation prevents 80% of setup failures later.

### Core Technologies

| Technology | Role in Stack | Windows-Specific Note |
|---|---|---|
| WSL2 (Ubuntu 22.04) | Linux runtime for all agents | Required for Docker, OpenHands, pgvector |
| Docker Desktop 4.41+ | Container orchestration | Enable WSL2 backend, disable Hyper-V backend |
| Python 3.11 | Primary agent language | Install inside WSL2, not Windows |
| uv | Dependency management | Replaces pip/venv/poetry |
| VS Code + WSL extension | Editor | Connect to WSL2 remote |
| Windows Terminal | Shell | Set WSL2 Ubuntu as default profile |
| Git 2.44+ | Version control | Configure global user inside WSL2 |
| LiteLLM | API gateway/normaliser | Routes to any provider via OpenAI-compatible API |

### YouTube Videos

- **WSL2 Complete Setup 2025** — NetworkChuck
  https://www.youtube.com/watch?v=_fntjriRe48
- **Docker Desktop for Windows: WSL2 Backend** — TechWorld with Nana
  https://www.youtube.com/watch?v=pg19Z8LL06w
- **uv: The Only Python Package Manager You Need** — ArjanCodes
  https://www.youtube.com/watch?v=jFfkJz6k8fI
- **VS Code Remote WSL Extension Setup** — Official VS Code channel
  https://www.youtube.com/watch?v=Owrk-G0hFLE

### YouTube Playlists

- **WSL2 + Docker + Linux on Windows** — Traversy Media
  https://www.youtube.com/playlist?list=PLillGF-RfqbYeckUaD1z6nviTp31GLTH8
- **LiteLLM Complete Course** — AI Jason
  https://www.youtube.com/playlist?list=PLpZBeKTZRGPNBwxqUCVVBxYClZfVPj1cZ

### Official Documentation

- WSL2 Installation: https://learn.microsoft.com/en-us/windows/wsl/install
- Docker Desktop WSL2 Backend: https://docs.docker.com/desktop/wsl/
- uv Documentation: https://docs.astral.sh/uv/
- LiteLLM Docs: https://docs.litellm.ai/docs/
- Python 3.11 in WSL2: https://www.python.org/downloads/

### Learning Outcomes

- WSL2 running Ubuntu 22.04 with Docker Desktop connected
- Python 3.11 environment managed by `uv` inside WSL2
- LiteLLM proxy running locally routing to at least two API providers
- VS Code connected to WSL2 remote
- Git configured with SSH keys for GitHub

---

## 2. AI Agent Fundamentals

**Priority:** Mandatory | **Difficulty:** Beginner–Intermediate | **Study Time:** 8–12 hours

### Core Concepts Map

```
Perception → Reasoning → Action → Memory → Learning
     ↑                                          |
     └──────────────── Feedback ────────────────┘
```

**Agent anatomy:** System prompt → Tool definitions → ReAct loop → Memory retrieval → Output → Tool execution → Observation → Next loop

**Patterns you will build:** ReAct, Plan-and-Execute, Reflection, Multi-Agent Supervisor, Hierarchical Crews

### YouTube Videos

- **AI Agents Explained: ReAct, Planning, Memory** — DeepLearning.AI (Andrew Ng)
  https://www.youtube.com/watch?v=sal78ACtGTc
- **LangGraph: Building Stateful Agents** — LangChain official
  https://www.youtube.com/watch?v=R8KB-Zcynxc
- **Building AI Agents from Scratch in Python** — Sam Witteveen
  https://www.youtube.com/watch?v=AxnL5GtWVNA
- **Tool Calling and Function Calling Deep Dive** — Andrej Karpathy
  https://www.youtube.com/watch?v=cdiD-9MMpb0
- **Multi-Agent Patterns in 2025** — Harrison Chase (LangChain)
  https://www.youtube.com/watch?v=pBBe1pk8hf4

### YouTube Playlists

- **LangGraph Full Course** — LangChain YouTube channel
  https://www.youtube.com/playlist?list=PLfaIDFEXuae16n2TWUkKq5PgJ0w6Pkwtg
- **AI Agents Fundamentals** — DeepLearning.AI
  https://www.youtube.com/playlist?list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF

### Key Papers (NotebookLM-compatible links)

- ReAct: Synergizing Reasoning and Acting: https://arxiv.org/abs/2210.03629
- Toolformer: https://arxiv.org/abs/2302.04761
- Reflexion: https://arxiv.org/abs/2303.11366

### Learning Outcomes

- Implement a ReAct agent from scratch using raw API calls (no framework)
- Understand tool call/response cycles across OpenAI, Anthropic, Gemini
- Build a single agent with memory, tool use, and self-reflection
- Understand when to use LangGraph vs CrewAI vs custom orchestration

---

## 3. OpenCode Ecosystem

**Priority:** Mandatory | **Difficulty:** Beginner | **Study Time:** 6–8 hours

### What OpenCode Is (2026)

OpenCode is a terminal-native, open-source AI coding agent with 162,000+ GitHub stars. It is **provider-agnostic** (75+ models), runs multi-session parallel agents on the same codebase, stores no code externally, and integrates with VS Code, Neovim, and any terminal. It is the **central interface** of your PAIOS — you direct it to build, fix, and extend every other component in this stack.

### Installation (Windows/WSL2)

```bash
# In WSL2 Ubuntu terminal
curl -fsSL https://opencode.ai/install.sh | sh
# Or via npm (Windows native)
npm install -g opencode-ai
```

OpenCode auto-detects your project, initialises `.opencode/`, and prompts for provider config on first launch.

### YouTube Videos

- **OpenCode Free AI Coding Agent Setup 2026** (Google Gemini, Groq)
  https://www.youtube.com/watch?v=20vcJmqAr4M
- **OpenCode vs Claude Code vs Cursor — Honest Comparison**
  Search: "opencode vs claude code 2026 comparison" on YouTube

### Official Resources

- GitHub: https://github.com/sst/opencode
- Documentation: https://opencode.ai/docs
- OpenCode Setup Guide (March 2026): https://ssntpl.com/opencode-open-source-ai-coding-agent-guide/
- DEV Community Overview: https://dev.to/anmolbaranwal/open-source-toolkit-for-building-ai-agents-in-2026-55h1

### OpenCode in PAIOS Context

OpenCode is your **day-to-day agent cockpit**. You use it to:
1. Generate and modify agent code (CrewAI crews, n8n custom nodes, MCP servers)
2. Run multi-session parallel debugging across components
3. Query your codebase with natural language ("where does Hermes store skills?")
4. Pipe OpenCode sessions into Hermes Agent for async task delegation

### Learning Outcomes

- OpenCode installed and connected to Claude/Gemini/OpenRouter
- `.opencode/config.json` configured with multiple providers and fallback order
- Multi-session workflow running (two parallel sessions on different tasks)
- OpenCode used to generate a FastAPI skeleton (practical first project)

---

## 4. MCP Servers

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 10–14 hours

### What MCP Is

Model Context Protocol (MCP) is an open standard by Anthropic (Nov 2024), now adopted by OpenAI, Google, and 400+ ecosystem tools. It standardises how AI agents connect to tools, databases, and external services. Think of it as USB-C for AI: one protocol, any tool, any model.

**Architecture:**
```
LLM Host (Claude/OpenCode/Hermes)
        ↓ JSON-RPC
   MCP Client
        ↓
   MCP Server ──→ Tool / Resource / Prompt
        ↓
   External Service (GitHub, PostgreSQL, filesystem, browser)
```

**Three primitive types:**
- **Tools** — executable actions (write file, run query, call API)
- **Resources** — read-only data (documents, database rows, code files)
- **Prompts** — reusable prompt templates with parameters

### YouTube Videos

- **MCP Explained: Build Your First MCP Server** — Fireship
  https://www.youtube.com/watch?v=7j_NE6Pjv-E
- **Model Context Protocol Full Course** — Dave Ebbelaar
  https://www.youtube.com/watch?v=sP1OFmoanO0
- **Building Production MCP Servers in Python** — AI Engineer Summit (Mahesh Murag, Anthropic)
  https://www.youtube.com/watch?v=WNxXKIp7F-0
- **MCP + n8n: Connect Any Tool to Your Agents** — n8n official
  https://www.youtube.com/watch?v=vxBaYGMiJik

### YouTube Playlists

- **MCP Servers Full Playlist** — Cole Medin
  https://www.youtube.com/playlist?list=PLvsHKGkI79CDQIX9JxD8HJ5yvjj03AMkS

### Official Resources

- MCP Specification: https://spec.modelcontextprotocol.io
- MCP Python SDK: https://github.com/modelcontextprotocol/python-sdk
- MCP TypeScript SDK: https://github.com/modelcontextprotocol/typescript-sdk
- Official MCP Server Examples: https://github.com/modelcontextprotocol/servers
- MCP Inspector (debugging tool): https://github.com/modelcontextprotocol/inspector
- Complete MCP Guide 2026: https://www.essamamdani.com/blog/complete-guide-model-context-protocol-mcp-2026
- MCP Cheat Sheet 2026: https://www.webfuse.com/mcp-cheat-sheet

### MCP Servers to Deploy in PAIOS

| Server | Function | Source |
|---|---|---|
| `filesystem` | Read/write local files | Official servers repo |
| `postgresql` | Query agent memory DB | Official servers repo |
| `github` | Repo management, PRs | Official servers repo |
| `playwright` | Browser automation | Community |
| `obsidian` | Knowledge base queries | Community |
| `n8n` | Trigger workflows from agents | n8n native |

### Learning Outcomes

- Build and run an MCP server in Python exposing 3 custom tools
- Connect OpenCode and Hermes to your MCP server
- Use MCP Inspector to debug tool calls
- Deploy filesystem + postgresql MCP servers via Docker Compose
- Understand OAuth 2.1 authentication for remote MCP servers

---

## 5. Skills, Tools & Plugins

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 8–10 hours

### Taxonomy

```
Agent Capability Layer
├── Skills        — reusable task knowledge (Hermes skill files, CrewAI task templates)
├── Tools         — callable functions (Python functions, MCP tools, API wrappers)
└── Plugins       — UI/integration extensions (VS Code extensions, n8n nodes, OpenCode plugins)
```

### Hermes Skills Architecture

Hermes Agent stores skills as Markdown documents in `~/.hermes/skills/`. After completing a complex task, it optionally writes a skill encoding the approach for reuse. Skills are retrieved via semantic search at task start.

```
~/.hermes/skills/
├── web_research.md        # How to structure multi-source research tasks
├── code_review.md         # Review criteria and output format
├── database_query.md      # pgvector query patterns
└── workflow_trigger.md    # How to call n8n webhooks
```

### YouTube Videos

- **Building Reusable LangChain Tools** — LangChain YouTube
  https://www.youtube.com/watch?v=1gRlCjy0AXY
- **CrewAI Custom Tools Deep Dive** — CrewAI official
  https://www.youtube.com/watch?v=q6QLGS306d0
- **FastAPI as Tool Backend for AI Agents** — Sebastián Ramírez
  https://www.youtube.com/watch?v=hxM-gg7tEkM

### Official Resources

- LangChain Tools Docs: https://python.langchain.com/docs/concepts/tools/
- CrewAI Tools Reference: https://docs.crewai.com/en/concepts/tools
- Hermes Agent Skills: https://github.com/NousResearch/hermes-agent
- Hermes Agent Community Docs: https://github.com/mudrii/hermes-agent-docs
- FastAPI Docs: https://fastapi.tiangolo.com

### Learning Outcomes

- Build 5 custom tools: web_search, file_writer, db_query, n8n_trigger, code_runner
- Wrap tools as MCP tools so any agent in the stack can use them
- Write 3 Hermes skills from scratch
- Deploy a FastAPI tool server on WSL2 that agents call via HTTP

---

## 6. CrewAI & Multi-Agent Systems

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 14–18 hours

### Why CrewAI

CrewAI is built from scratch (not on LangChain), optimised for speed, and handles both Crews (autonomous role-based collaboration) and Flows (event-driven deterministic pipelines). It has 100,000+ certified developers and first-class MCP support. It uses LiteLLM under the hood — any API provider works.

### Core Concepts

```
Crew
├── Agent (role, goal, backstory, tools, llm)
├── Agent (specialised role)
└── Task (description, expected_output, agent, context)
    ↓
Process (sequential | hierarchical | parallel)
    ↓
Crew.kickoff() → Final Output
```

**Flows** add deterministic state machines on top of Crews for production reliability.

### YouTube Videos

- **CrewAI Tutorial: Multiple Agents Working Together in Python** — Merge Conflict
  https://www.youtube.com/watch?v=I90xJlzAUW0
- **CrewAI Tutorial For Beginners 2026** — Simplilearn
  https://www.youtube.com/watch?v=hbvm_q8xBTw
- **CrewAI Flows: Production Multi-Agent Pipelines** — CrewAI official
  https://www.youtube.com/watch?v=8PtGcNE83e4
- **Multi-Agent Research System with CrewAI** — Nicholas Renotte
  https://www.youtube.com/watch?v=Jl6nQJGMJ_M
- **CrewAI + MCP Integration** — Cole Medin
  https://www.youtube.com/watch?v=7qZOXkP5FWw

### YouTube Playlists

- **CrewAI Full Playlist** — CrewAI official YouTube
  https://www.youtube.com/@CrewAI-Multi-Agent-Platform/playlists
- **Agentic AI with Python** — DataBrick
  https://www.youtube.com/playlist?list=PLZoTAELRMXVPBTrWtJkn3wWQxZkmTXGwe

### Official Resources

- CrewAI GitHub: https://github.com/crewaiinc/crewai
- CrewAI Docs: https://docs.crewai.com
- CrewAI Concepts (Agents): https://docs.crewai.com/en/concepts/agents
- CrewAI Open Source: https://crewai.com/open-source
- Multi-Agent CrewAI Tutorial (2026): https://tech-insider.org/crewai-tutorial-multi-agent-ai-python-2026/
- CrewAI + Mem0 Memory Guide: https://mem0.ai/blog/crewai-guide-multi-agent-ai-teams
- Firecrawl CrewAI Tutorial: https://www.firecrawl.dev/blog/crewai-multi-agent-systems-tutorial

### Multi-Agent Patterns

| Pattern | CrewAI Implementation | Use Case |
|---|---|---|
| Supervisor | Hierarchical process + manager LLM | Complex research pipelines |
| Parallel Crew | `async_execution=True` on tasks | Independent data processing |
| Reflection | Agent reviews own output task | Quality-critical content |
| Specialised Experts | Role + tools per agent | Research → Write → Edit pipeline |
| Human-in-loop | `human_input=True` on task | Approval workflows |

### Learning Outcomes

- Build a 3-agent research crew (Researcher, Writer, Editor) with sequential flow
- Build a hierarchical crew with a Manager agent delegating to specialists
- Implement a CrewAI Flow with conditional branching
- Integrate CrewAI crew with MCP tools
- Add Mem0 persistent memory to a crew
- Connect crew output to n8n webhook for downstream automation

---

## 7. Hermes Agent

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 8–12 hours

### What Hermes Agent Is (2026)

Hermes Agent is an open-source, MIT-licensed autonomous agent by **Nous Research**, released February 2026. It has accumulated 66,000+ GitHub stars. Its core differentiator is a **closed learning loop**: after completing complex tasks, it writes reusable skills to `~/.hermes/skills/`. It maintains persistent memory across sessions and builds a contextual model of your workflow over time.

**Key features as of v0.14.0 (May 2026):**
- 40+ built-in tools (web search, code execution, file management, computer use)
- MCP server mode (exposes Hermes as an MCP server to other agents)
- Subagent spawning (parallel isolated workstreams)
- API server mode (`/v1/chat/completions` compatible — pipe into OpenCode)
- 16 messaging platform integrations (Telegram, Discord, Slack, etc.)
- Provider-agnostic: OpenAI, Anthropic, OpenRouter, any OpenAI-compatible endpoint

### Installation (Windows/WSL2)

```bash
# Python 3.10+ required
python -m venv hermes-env
source hermes-env/bin/activate
pip install hermes-agent

# Or from git for latest (v0.14.0)
pip install git+https://github.com/NousResearch/hermes-agent.git

# Configure
hermes config set provider anthropic
hermes config set model claude-sonnet-4-6
```

### YouTube Videos

- **Hermes Agent Full Setup Tutorial** — Search: "Hermes Agent NousResearch setup tutorial 2026" on YouTube
- **Self-Improving AI Agents Explained** — Matthew Berman
  https://www.youtube.com/watch?v=iZMKtJ5-BHw
- **Persistent Agent Memory Architecture** — AI Jason
  https://www.youtube.com/watch?v=Try7lmWikao

### Official Resources

- GitHub (official): https://github.com/NousResearch/hermes-agent
- Community Docs (comprehensive): https://github.com/mudrii/hermes-agent-docs
- Architecture deep-dive: https://dev.to/arshtechpro/hermes-agent-a-self-improving-ai-agent-that-runs-anywhere-2b7d
- Setup guide (Petronella): https://petronellatech.com/blog/hermes-agent-ai-guide/
- Developer Guide (Lushbinary): https://lushbinary.com/blog/hermes-agent-developer-guide-setup-skills-self-improving-ai/
- 10-minute setup (Medium): https://nitingavhane.medium.com/hermes-agent-full-setup-how-to-build-your-own-self-improving-ai-agent-in-10-minutes-2a61e809e8d0
- Getting Started (LinkedIn): https://www.linkedin.com/pulse/getting-started-hermes-agent-your-self-improving-ai-assistant-maio-tys6e

### Hermes in PAIOS

Hermes acts as the **persistent background operator** of your AI OS:
- Receives delegated tasks from OpenCode sessions
- Executes long-running workflows while you work on other things
- Writes new skills that improve future OpenCode + CrewAI sessions
- Serves as an MCP server so CrewAI agents can call Hermes tools
- Manages your personal knowledge graph (feeds Obsidian/Notion)

### Learning Outcomes

- Hermes Agent running persistently on WSL2, connected to Claude API
- 5 custom skills written covering your most common workflows
- Hermes API server mode enabled — confirmed callable from OpenCode
- Hermes connected to Telegram for mobile task dispatch
- Subagent spawning working for a parallel research task

---

## 8. n8n Automation

**Priority:** Mandatory | **Difficulty:** Beginner–Intermediate | **Study Time:** 10–14 hours

### What n8n Is

n8n is an open-source (191,000+ GitHub stars, 200,000+ community members) visual workflow automation platform. In 2026 it is the **glue layer** of your PAIOS — connecting agents, APIs, databases, and notifications without custom integration code. It has native MCP server support, built-in AI agent nodes, and self-hostable Docker deployment.

**n8n in PAIOS:**
- Receives webhook triggers from CrewAI flow completions
- Orchestrates multi-step pipelines (scrape → chunk → embed → notify)
- Provides human-in-the-loop approval gates
- Connects Hermes Agent outputs to Notion/Obsidian/PostgreSQL
- Acts as a cron scheduler for recurring agent tasks

### YouTube Videos

- **n8n AI Agent Tutorial for Beginners 2026** — Step by Step
  https://www.youtube.com/watch?v=PfdnYe2690E
- **n8n Automation Tutorial 2026: Complete Beginner's Guide**
  https://www.youtube.com/watch?v=jCWPqTDgplk
- **n8n Quick Start: Build Your First AI Agent [2026]**
  https://www.youtube.com/watch?v=GuaKeDS6UKU
- **n8n AI Agents & Automation Complete Course (2026)**
  https://www.youtube.com/watch?v=eQNkwr82KVo
- **Master n8n AI Agents in 2 Hours: Beginner's Guide for 2026**
  https://www.youtube.com/watch?v=fTma6WVg-qk
- **Complete n8n Masterclass: Build AI Agents & Automate Workflows (7.5 hr)**
  https://www.youtube.com/watch?v=DkV7ztrhLh8

### YouTube Playlists

- **n8n Official Tutorials**: https://www.youtube.com/@n8n-io/playlists
- **n8n AI Automation** — Brendan's AI Launchpad
  https://www.youtube.com/watch?v=eQNkwr82KVo (full playlist in channel)

### Official Resources

- n8n GitHub: https://github.com/n8n-io/n8n
- n8n Docs: https://docs.n8n.io
- n8n AI Agents: https://n8n.io/ai-agents/
- n8n MCP Support: https://n8n.io/integrations/agent/
- Self-hosted AI starter kit: https://github.com/n8n-io/self-hosted-ai-starter-kit
- n8n on Windows/Docker guide: https://syntheticlabs.xyz/2025/09/05/deploy-n8n-docker-windows-private-ai/
- n8n 2026 Guide (HatchWorks): https://hatchworks.com/blog/ai-agents/n8n-guide/

### n8n Workflow Templates to Build

1. **Agent Task Router** — receives POST, classifies intent, routes to CrewAI or Hermes
2. **RAG Ingestion Pipeline** — watches folder → chunks → embeds → stores in pgvector
3. **GitHub PR Summariser** — triggers on PR webhook → summarises → posts comment
4. **Daily Digest** — cron → Hermes research → format → push to Obsidian
5. **Approval Gate** — pauses workflow, sends Telegram message, resumes on approval

### Learning Outcomes

- n8n running in Docker on Windows (with WSL2 backend)
- 5 workflows built covering all major node types
- AI Agent node connected to Claude via LiteLLM proxy
- Webhook triggers integrated with CrewAI and Hermes
- MCP server node configured for external tool calls

---

## 9. OpenHands

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 8–12 hours

### What OpenHands Is

OpenHands (formerly OpenDevin) is an open-source autonomous AI software development platform that acts as an AI software engineer. It can modify code, run shell commands, browse the web, write tests, and call APIs — in a sandboxed environment. It solved over 50% of real GitHub issues in SWE-bench benchmarks.

**In PAIOS:** OpenHands handles the tasks that are too large or too iterative for a single OpenCode session — full feature implementations, bug hunting across large codebases, automated testing pipelines.

### Installation (Windows — requires Docker)

```bash
# Docker must be running
docker pull docker.all-hands.dev/all-hands-ai/openhands:0.38
docker run -it --rm \
  -e SANDBOX_RUNTIME_CONTAINER_IMAGE=docker.all-hands.dev/all-hands-ai/runtime:0.38-nikolaik \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v ~/.openhands-state:/.openhands-state \
  -p 3000:3000 \
  --add-host host.docker.internal:host-gateway \
  docker.all-hands.dev/all-hands-ai/openhands:0.38
# Then open http://localhost:3000
```

### YouTube Videos

- **OpenHands: Open-Source AI Software Developer** — Official OpenHands channel
  https://www.youtube.com/watch?v=oB4JR98KRAA
- **OpenHands Official Channel** (all tutorials):
  https://www.youtube.com/@OpenHands-AI
- **OpenHands AI Agent: Generate Complex Apps End-to-End** — Matthew Berman
  Search: "OpenHands AI Software Engineer Generate Complex Apps" on YouTube
- **KDnuggets OpenHands Tutorial**: https://www.kdnuggets.com/openhands-open-source-ai-software-developer

### Official Resources

- GitHub: https://github.com/All-Hands-AI/OpenHands
- Documentation: https://docs.all-hands.dev
- Benchmarks: https://www.swebench.com

### OpenHands in PAIOS

- Use for multi-file refactoring tasks delegated from Hermes
- Use for automated test generation on CrewAI crews
- Use for end-to-end feature implementation (issue → PR ready)
- OpenHands outputs feed back into OpenCode for review

### Learning Outcomes

- OpenHands running in Docker, connected to Claude API
- Completed a full feature implementation task (issue → working code)
- OpenHands configured as a tool callable from CrewAI
- Understand the agent loop: CodeAct, SWE-agent, and BrowsingAgent modes

---

## 10. Docker & Infrastructure

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 10–14 hours

### PAIOS Docker Architecture

Every component in the stack runs as a Docker service. The master `docker-compose.yml` is your system's source of truth.

```yaml
# docker-compose.yml (simplified PAIOS stack)
services:
  litellm:          # API gateway
  postgres:         # Agent memory + RAG store
  redis:            # Agent state cache
  n8n:              # Workflow automation
  openhands:        # AI software developer
  mcp-filesystem:   # Filesystem MCP server
  mcp-postgres:     # Database MCP server
  hermes:           # Persistent agent (via API server mode)
  fastapi-tools:    # Custom tool server
```

### YouTube Videos

- **Docker Compose for Beginners** — TechWorld with Nana
  https://www.youtube.com/watch?v=HG6yIjZapSA
- **Docker Desktop for Windows + WSL2** — TechWorld with Nana
  https://www.youtube.com/watch?v=pg19Z8LL06w
- **Docker for AI Agents 2025** — Docker official
  https://www.youtube.com/watch?v=7j_NE6Pjv-E
- **Running AI Agents Safely with Docker Sandbox** — Andrew Lock
  https://andrewlock.net/running-ai-agents-safely-in-a-microvm-using-docker-sandbox/

### YouTube Playlists

- **Docker Full Course** — TechWorld with Nana
  https://www.youtube.com/playlist?list=PLy7NrYWoggjwPggqtFsI_zMAwvG0SqYCb
- **Docker for Developers** — Fireship
  https://www.youtube.com/playlist?list=PL0zVEGEvSaeEd9hlmqFGzf23P8p_kLnkh

### Official Resources

- Docker Desktop WSL2: https://docs.docker.com/desktop/wsl/
- Docker Compose Reference: https://docs.docker.com/compose/
- Docker AI Solutions 2026: https://www.docker.com/solutions/docker-ai/
- Docker Compose for AI Agents: https://www.docker.com/blog/build-ai-agents-with-docker-compose/
- Docker Model Runner (vLLM on Windows): https://www.docker.com/blog/docker-model-runner-vllm-windows/
- AI Agent Sandbox Security: https://www.docker.com/blog/build-ai-agents-with-docker-compose/
- WSL2 + Docker Windows Setup: https://dasarpai.com/dsblog/development-environment-with-windows-11-wsl2-and-docker/

### Learning Outcomes

- Full PAIOS stack running via `docker compose up -d`
- Health checks and restart policies configured for all services
- Named volumes for persistent data (postgres, n8n, hermes)
- Docker networks isolating agent traffic from external traffic
- `.env` file managing all API keys (never hardcoded)
- Portainer or Lazydocker installed for visual container management

---

## 11. PostgreSQL & Agent Memory

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 10–12 hours

### PostgreSQL as Agent Memory Store

PostgreSQL with `pgvector` is your unified memory layer:
- **Episodic memory** — past agent conversations (full message history)
- **Semantic memory** — embedded knowledge (RAG chunks)
- **Procedural memory** — skill/tool usage logs
- **Working memory** — Redis (fast expiry, sub-second retrieval)

```sql
-- Agent memory schema
CREATE TABLE agent_memories (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    agent_id VARCHAR NOT NULL,
    session_id VARCHAR,
    memory_type VARCHAR,  -- episodic | semantic | procedural
    content TEXT,
    embedding VECTOR(1536),
    metadata JSONB,
    created_at TIMESTAMPTZ DEFAULT NOW()
);
CREATE INDEX ON agent_memories USING hnsw (embedding vector_cosine_ops);
```

### YouTube Videos

- **pgvector Tutorial: Vector Search in PostgreSQL** — Supabase official
  https://www.youtube.com/watch?v=IzG0WKXhiKU
- **RAG with pgvector and LangChain** — Python Engineer
  https://www.youtube.com/watch?v=eCE3BDPWZ4s
- **PostgreSQL for Beginners 2025** — Amigoscode
  https://www.youtube.com/watch?v=SpfIwlAYaKk

### YouTube Playlists

- **PostgreSQL Complete Course** — Amigoscode
  https://www.youtube.com/playlist?list=PLwvrYc43l1MxAEOI_KwGe8l42uJDDDs0T

### Official Resources

- pgvector GitHub: https://github.com/pgvector/pgvector
- LangChain PGVector Docs: https://python.langchain.com/docs/integrations/vectorstores/pgvector/
- RAG + LangChain + pgvector (2026 guide): https://tutorials.technology/tutorials/rag-langchain-pgvector-python-2026.html
- pgvector + LangChain (Medium): https://medium.com/@rahulmydur/pgvector-integrating-postgresql-with-langchain-for-advanced-semantic-search-c8cabacaa79b
- Production RAG with pgvector: https://digitpatrox.com/how-to-build-a-rag-system-with-pgvector-and-langchain/

### Redis for Agent State

```bash
docker run -d -p 6379:6379 redis:alpine
# Used for:
# - Session state (active agent conversations)
# - Tool call caching (avoid duplicate API calls)
# - Rate limit tracking
# - Pub/Sub for agent-to-agent messaging
```

### Learning Outcomes

- PostgreSQL + pgvector running in Docker
- Agent memory schema created and indexed
- CRUD operations on memories from Python (asyncpg)
- HNSW vector search returning relevant memories under 50ms
- Redis running and integrated as session cache
- MCP server exposing PostgreSQL to all agents in stack

---

## 12. Obsidian Knowledge Management

**Priority:** Recommended | **Difficulty:** Beginner | **Study Time:** 4–6 hours

### Obsidian in PAIOS

Obsidian is your **human-readable knowledge interface**. Agents write to it; you read and curate from it. The local Markdown vault is directly queryable by the `obsidian-mcp` server, allowing OpenCode and Hermes to search and append to your knowledge base.

### Setup

```
Vault location: ~/paios-vault/
Structure:
├── inbox/          ← Agent writes here
├── projects/       ← Per-project notes
├── agents/         ← Agent session logs
├── skills/         ← Human-readable skill docs
└── references/     ← Research outputs
```

**Key plugins:**
- Obsidian Git (auto-commit to GitHub)
- Dataview (query notes as database)
- Templater (structured agent note templates)
- Canvas (visual knowledge maps)

### YouTube Videos

- **Obsidian for Developers: Complete Setup 2025** — No Boilerplate
  https://www.youtube.com/watch?v=DbsAQSIKQXk
- **Obsidian + AI Agents: Automated Knowledge Base** — Bryan Jenks
  https://www.youtube.com/watch?v=KCbgJqBfBxY

### Official Resources

- Obsidian Docs: https://help.obsidian.md
- Obsidian MCP Server (community): https://github.com/MarkusPfundstein/mcp-obsidian
- Obsidian Git Plugin: https://github.com/denolehov/obsidian-git

### Learning Outcomes

- Obsidian vault structured for agent-written content
- Obsidian Git plugin auto-committing changes to GitHub
- MCP server querying vault from OpenCode and Hermes
- n8n workflow writing agent outputs to Obsidian inbox

---

## 13. Notion Knowledge Management

**Priority:** Recommended | **Difficulty:** Beginner | **Study Time:** 4–6 hours

### Notion in PAIOS

Notion serves as your **structured project management and deliverables layer** — where Obsidian is freeform notes, Notion is databases, projects, and tracked tasks. Agents write deliverables to Notion via the official API.

### YouTube Videos

- **Notion API Tutorial for Beginners** — Traversy Media
  https://www.youtube.com/watch?v=sec5sqqPDvo
- **Notion + n8n Automation** — n8n official
  https://www.youtube.com/watch?v=B9UkjhzXtHE

### Official Resources

- Notion API Docs: https://developers.notion.com
- Notion MCP Server (official): https://github.com/makenotion/notion-mcp-server
- n8n Notion Integration: https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.notion/

### Learning Outcomes

- Notion API integration key configured
- n8n workflow pushing CrewAI research outputs to a Notion database
- Notion MCP server connected to OpenCode and Hermes
- Agent task tracker database in Notion updated by agent completions

---

## 14. RAG Systems

**Priority:** Mandatory | **Difficulty:** Intermediate–Advanced | **Study Time:** 14–18 hours

### RAG Architecture in PAIOS

```
Documents (PDF, MD, HTML, code)
    ↓ Loader (LangChain DocumentLoaders)
    ↓ Splitter (RecursiveCharacterTextSplitter: 800 chars, 120 overlap)
    ↓ Embedder (text-embedding-3-small | Gemini text-embedding-004)
    ↓ pgvector store (HNSW index, cosine similarity)
              ↓
User Query → Embed → Similarity Search → Top-K chunks
              ↓
    Reranker (Cohere Rerank v3 | BGE Reranker)
              ↓
    LLM + Retrieved Context → Answer
              ↓
    Cache result in Redis (semantic cache)
```

### RAG Variants to Implement

| Variant | When to Use | Key Technique |
|---|---|---|
| Naive RAG | Baseline / simple docs | Vector search only |
| Hybrid RAG | Mixed keyword+semantic | pgvector + BM25/tsvector |
| HyDE RAG | Sparse query recall | Hypothetical document embeddings |
| Agentic RAG | Multi-hop reasoning | LangGraph + RAG tools |
| Self-RAG | Accuracy-critical outputs | Reflection tokens |

### YouTube Videos

- **RAG from Scratch** — LangChain official
  https://www.youtube.com/watch?v=sVcwVQRHIc8
- **Advanced RAG Techniques** — LlamaIndex
  https://www.youtube.com/watch?v=TRjq7t2Ms5I
- **Hybrid RAG: BM25 + Vector Search** — Sam Witteveen
  https://www.youtube.com/watch?v=gZqwQdPkRD8
- **Agentic RAG with LangGraph** — LangChain
  https://www.youtube.com/watch?v=2grDHX3cXLU
- **pgvector RAG Production Guide** — Supabase
  https://www.youtube.com/watch?v=IzG0WKXhiKU

### YouTube Playlists

- **RAG from Scratch — LangChain Full Playlist**
  https://www.youtube.com/playlist?list=PLfaIDFEXuae2LXbO1_PKyVJiQ23ZztA0x
- **LlamaIndex Complete Course**
  https://www.youtube.com/playlist?list=PLB1nTQo4_y6sdIdqTDTQoOetDBvRCXYBb

### Official Resources

- LangChain RAG Tutorial: https://python.langchain.com/docs/tutorials/rag/
- LangChain PGVector: https://python.langchain.com/docs/integrations/vectorstores/pgvector/
- LlamaIndex Docs: https://docs.llamaindex.ai
- Production RAG Architecture: https://digitpatrox.com/how-to-build-a-rag-system-with-pgvector-and-langchain/
- RAG + pgvector 2026 tutorial: https://tutorials.technology/tutorials/rag-langchain-pgvector-python-2026.html
- Zilliz RAG Guide: https://zilliz.com/tutorials/rag/langchain-and-pgvector-and-openai-gpt-o3-mini-and-ollama-all-minilm
- pgdash RAG with PostgreSQL: https://pgdash.io/blog/rag-with-postgresql.html

### Learning Outcomes

- Naive RAG pipeline ingesting PDFs into pgvector
- Hybrid RAG combining vector + BM25 search (PostgreSQL `tsvector`)
- Reranking with Cohere API before final LLM call
- Agentic RAG in LangGraph — agent decides when to retrieve
- n8n pipeline automating document ingestion
- RAG system exposed as an MCP tool for all agents in stack

---

## 15. Browser Automation

**Priority:** Mandatory | **Difficulty:** Intermediate | **Study Time:** 8–10 hours

### Playwright as the Browser Automation Layer

Playwright (Microsoft) is the production browser automation choice for 2026. It supports Chromium, Firefox, and WebKit, runs headlessly in Docker, and has an official MCP server exposing browser control to any MCP-compatible agent.

### Browser Automation in PAIOS

```
OpenCode / Hermes / CrewAI Agent
        ↓ MCP tool call: "navigate_to", "click", "extract_text"
    playwright-mcp-server
        ↓
    Browser (Chromium headless in Docker)
        ↓
    Web content / DOM / screenshots
        ↓
    Structured extraction → pgvector store
```

### YouTube Videos

- **Playwright Python Tutorial 2025** — Arjancodes
  https://www.youtube.com/watch?v=tLs4RHhgXLI
- **Playwright MCP Server: Agents That Browse the Web** — Dave Ebbelaar
  https://www.youtube.com/watch?v=sP1OFmoanO0
- **Browser Automation with AI Agents** — Sam Witteveen
  https://www.youtube.com/watch?v=sal78ACtGTc
- **Web Scraping + AI: Firecrawl + LangChain** — Nicholas Renotte
  https://www.youtube.com/watch?v=Jl6nQJGMJ_M

### Official Resources

- Playwright Python Docs: https://playwright.dev/python/docs/intro
- Playwright MCP Server (official): https://github.com/microsoft/playwright-mcp
- Playwright in Docker: https://playwright.dev/docs/docker
- Firecrawl (structured web scraping): https://www.firecrawl.dev/blog/crewai-multi-agent-systems-tutorial

### Learning Outcomes

- Playwright MCP server running in Docker, connected to OpenCode
- Agent that navigates to a URL, extracts structured data, stores in PostgreSQL
- Browser automation workflow in n8n using Playwright node
- Headless browser screenshots captured and passed to vision model
- Authenticated session automation (login flow handled by Playwright)

---

## 16. Computer Use Agents

**Priority:** Recommended | **Difficulty:** Advanced | **Study Time:** 8–10 hours

### What Computer Use Agents Are

Computer use agents see the full desktop (via screenshots) and control mouse, keyboard, and applications — not just browsers. This is different from browser automation: it works on any desktop application.

**Primary tools in 2026:**
- Claude's computer use API (Anthropic) — screenshot + action loop
- OpenHands BrowsingAgent — browser + desktop control
- Hermes `computer_use` tool (v0.14.0+)

### Computer Use in PAIOS

Computer use agents handle tasks that have no API: legacy applications, desktop-only tools, visual verification of agent outputs.

**Safety first:** Always run computer use inside a Docker container or VM. Never give a computer use agent access to your host filesystem without explicit approval gates.

### YouTube Videos

- **Claude Computer Use API Tutorial** — Matt Shumer
  https://www.youtube.com/watch?v=ODaHJzOyVCQ
- **Autonomous Computer Control Agents 2025** — Matthew Berman
  https://www.youtube.com/watch?v=iZMKtJ5-BHw
- **OpenHands BrowsingAgent Tutorial** — OpenHands official
  https://www.youtube.com/@OpenHands-AI

### Official Resources

- Anthropic Computer Use Docs: https://docs.anthropic.com/en/docs/agents-and-tools/computer-use
- Claude API Computer Use Beta: https://docs.anthropic.com/en/docs/build-with-claude/tool-use
- OpenHands Browsing Agent: https://docs.all-hands.dev/modules/usage/agents
- Docker Sandbox for Computer Use: https://andrewlock.net/running-ai-agents-safely-in-a-microvm-using-docker-sandbox/

### Learning Outcomes

- Claude computer use API running in sandboxed Docker container
- Agent that opens a desktop application, completes a form, and reports back
- Approval gate (n8n + Telegram) before agent executes destructive actions
- Screenshot capture and vision model analysis in agentic loop

---

## 17. GitHub & Open Source Contribution

**Priority:** Recommended | **Difficulty:** Beginner–Intermediate | **Study Time:** 6–8 hours

### GitHub in PAIOS

GitHub is your **version control, CI/CD, and contribution layer**:
- All PAIOS components versioned in a private monorepo
- GitHub Actions automating tests, Docker builds, and deployments
- OpenCode + OpenHands used to generate PRs to major projects
- GitHub MCP server allowing agents to create issues, review PRs

### GitHub Actions for PAIOS

```yaml
# .github/workflows/paios.yml
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run agent tests
        run: docker compose -f docker-compose.test.yml up --abort-on-container-exit
```

### YouTube Videos

- **GitHub Actions Complete Guide 2025** — TechWorld with Nana
  https://www.youtube.com/watch?v=R8_veQiYBjI
- **Contributing to Open Source on GitHub** — Eddie Jaoude
  https://www.youtube.com/watch?v=RGOj5yH7evk
- **GitHub MCP Server Tutorial** — Cole Medin
  https://www.youtube.com/watch?v=7qZOXkP5FWw

### Official Resources

- GitHub Actions Docs: https://docs.github.com/en/actions
- GitHub MCP Server: https://github.com/github/github-mcp-server
- CrewAI GitHub Contribution Guide: https://github.com/crewaiinc/crewai/blob/main/CONTRIBUTING.md
- OpenHands Contribution Guide: https://github.com/All-Hands-AI/OpenHands/blob/main/CONTRIBUTING.md
- n8n Contribution Guide: https://github.com/n8n-io/n8n/blob/master/CONTRIBUTING.md

### Learning Outcomes

- PAIOS monorepo on GitHub with structured folders per component
- GitHub Actions running Docker Compose test suite on every push
- GitHub MCP server connected to OpenCode for repo operations
- First PR submitted to an open-source project in the stack
- Issue templates for bug reports and feature requests

---

## 18. Advanced System Architecture

**Priority:** Recommended | **Difficulty:** Advanced | **Study Time:** 8–10 hours

### Key Advanced Patterns

**1. Agent-to-Agent Protocol (A2A)**
CrewAI now supports A2A for agent discovery and collaboration across systems. Agents advertise capabilities; other agents call them without hardcoded routing.

**2. LangGraph Stateful Pipelines**
Use LangGraph when you need deterministic state machines with checkpointing. Combine with CrewAI: LangGraph manages macro flow, CrewAI manages micro-crew execution.

**3. Semantic Router**
Route incoming requests to the right agent or crew based on embedding similarity — no hardcoded if/else chains.

```python
from semantic_router import Route, RouteLayer
from semantic_router.encoders import OpenAIEncoder
routes = [
    Route(name="research", utterances=["find information about", "research"]),
    Route(name="code", utterances=["write code", "implement", "fix bug"]),
    Route(name="automate", utterances=["create workflow", "automate"]),
]
rl = RouteLayer(encoder=OpenAIEncoder(), routes=routes)
```

**4. Event-Driven Agent Orchestration**
Redis Pub/Sub as the message bus. Agents subscribe to event channels; n8n publishes events; agents react autonomously.

### YouTube Videos

- **LangGraph: Production Multi-Agent Architectures** — Harrison Chase
  https://www.youtube.com/watch?v=R8KB-Zcynxc
- **Building Scalable AI Systems** — Andrej Karpathy (SOTA lecture)
  https://www.youtube.com/watch?v=9vM4p9NN0Ts
- **Semantic Router Tutorial** — James Briggs
  https://www.youtube.com/watch?v=tVw3CwrN5-8

### Official Resources

- LangGraph Docs: https://langchain-ai.github.io/langgraph/
- Semantic Router GitHub: https://github.com/aurelio-labs/semantic-router
- CrewAI A2A Protocol: https://docs.crewai.com (A2A section)
- Redis Pub/Sub for Agents: https://redis.io/docs/manual/pubsub/

---

## 19. Production Deployment

**Priority:** Recommended | **Difficulty:** Advanced | **Study Time:** 8–10 hours

### Production Readiness Checklist

```
□ All secrets in .env (never committed to git)
□ All services have health checks in docker-compose.yml
□ PostgreSQL volume backed up daily (pg_dump cron via n8n)
□ LiteLLM budget limits set per agent/team
□ Rate limiting on FastAPI tool server
□ Logging: structured JSON logs → file → optional Loki/Grafana
□ Alerting: agent failures → n8n → Telegram notification
□ GitHub Actions: automated test suite
□ Docker image versioning: never use :latest in production
□ Reverse proxy: Caddy or nginx in front of all services
```

### Observability Stack

```yaml
# Minimal observability addition to docker-compose.yml
  caddy:            # HTTPS reverse proxy
  portainer:        # Container management UI
  langfuse:         # LLM observability (traces, costs, quality)
```

- **LangFuse** — open-source LLM observability, tracks every agent call, cost, latency, and quality score
- **Portainer** — Docker management UI, critical for Windows users
- **Caddy** — automatic HTTPS, simpler than nginx for local dev

### YouTube Videos

- **LangFuse Tutorial: LLM Observability** — LangFuse official
  https://www.youtube.com/watch?v=FkAMzOlmBc4
- **Docker Compose Production Best Practices** — TechWorld with Nana
  https://www.youtube.com/watch?v=eSdoKEAMOtM
- **Self-Hosted AI Stack: Portainer + Docker** — Techno Tim
  https://www.youtube.com/watch?v=ljDI5jykjE8

### Official Resources

- LangFuse GitHub: https://github.com/langfuse/langfuse
- LangFuse Docs: https://langfuse.com/docs
- Portainer Docs: https://docs.portainer.io
- Caddy Docs: https://caddyserver.com/docs

---

## 20. Projects

### Mini Projects (Weeks 1–3, 2–4 hours each)

| # | Project | Stack Used | Outcome |
|---|---|---|---|
| M1 | WSL2 + Docker + LiteLLM setup | WSL2, Docker, LiteLLM | All base services running |
| M2 | First OpenCode session — generate a FastAPI app | OpenCode, FastAPI | Working API skeleton |
| M3 | Build an MCP filesystem server | MCP Python SDK | Read/write files via MCP |
| M4 | Single CrewAI agent with a tool | CrewAI, LangChain tools | Agent calls external API |
| M5 | n8n hello-world workflow with webhook | n8n Docker | POST request triggers LLM response |
| M6 | pgvector memory table + CRUD | PostgreSQL, pgvector | Store and retrieve embeddings |
| M7 | Hermes Agent first run + skill creation | Hermes Agent | 2 custom skills written |
| M8 | Playwright scrape → store in PostgreSQL | Playwright, psycopg | Agent reads structured web data |

### Intermediate Projects (Weeks 3–6, 4–8 hours each)

| # | Project | Stack Used | Outcome |
|---|---|---|---|
| I1 | **Research Crew** — 3-agent CrewAI pipeline writing a technical report | CrewAI, LangChain RAG, pgvector, Notion | Full report in Notion |
| I2 | **RAG Knowledge Base** — ingest 50 docs, expose as MCP tool | LangChain, pgvector, FastAPI, MCP | Queryable knowledge base |
| I3 | **n8n Automation Hub** — 5 production workflows connecting all agents | n8n, webhooks, CrewAI, Hermes, PostgreSQL | 5 live workflows |
| I4 | **OpenHands Feature Sprint** — implement a GitHub issue end-to-end | OpenHands, GitHub MCP, Docker | Merged or reviewable PR |
| I5 | **Hermes Personal Agent** — persistent agent connected to Telegram and Obsidian | Hermes Agent, Telegram, Obsidian MCP | 24/7 personal agent |
| I6 | **Semantic Router** — route 10 different request types to right agent | Semantic Router, LiteLLM, CrewAI, n8n | <100ms routing latency |

### Capstone Projects (Weeks 6–8, 15–25 hours each)

#### Capstone 1: PAIOS Command Centre
**Full AI Agent Operating System with unified interface**

Build a FastAPI dashboard that:
- Shows all running agents (OpenCode sessions, Hermes, CrewAI crews, OpenHands jobs)
- Accepts natural language task input, routes via semantic router
- Displays live token usage and cost tracking (LangFuse integration)
- Shows n8n workflow run history
- Exposes all MCP servers through a single gateway

**Stack:** FastAPI + HTMX, LangFuse, Semantic Router, Redis, PostgreSQL, all MCP servers, Docker Compose

---

#### Capstone 2: Autonomous Research-to-Publication Pipeline
**End-to-end agent pipeline from topic to published artefact**

1. User provides a research topic via Telegram (Hermes receives)
2. Hermes spawns a CrewAI research crew (Researcher, Fact-Checker, Writer)
3. Playwright agent collects 10 sources, stores in RAG
4. Crew synthesises report using RAG retrieval
5. n8n publishes report to Obsidian + Notion + GitHub Pages
6. Hermes writes a new skill encoding the workflow

**Stack:** Hermes Agent, CrewAI, Playwright MCP, pgvector RAG, n8n, Obsidian MCP, Notion API, GitHub Actions

---

#### Capstone 3: AI Developer OS — Self-Extending Codebase
**The system that builds itself**

OpenCode + OpenHands + CrewAI working together to:
1. Read your GitHub issue backlog (GitHub MCP server)
2. Triage and prioritise issues (CrewAI triage crew)
3. Implement solutions (OpenHands)
4. Write tests (OpenHands CodeAct)
5. Create PR (GitHub MCP)
6. Notify you for final review (Telegram via Hermes)

**Stack:** OpenCode, OpenHands, CrewAI, GitHub MCP, n8n, Hermes Agent, Docker, PostgreSQL

---

## 21. 8-Week Study Plan

### Week 1: Foundation + Environment
**Goal:** Everything running, nothing broken.

| Day | Activities | Time |
|---|---|---|
| Mon | WSL2 Ubuntu 22.04 install, Windows Terminal config | 2h |
| Tue | Docker Desktop install, WSL2 backend, hello-world container | 2h |
| Wed | Python 3.11 + uv inside WSL2, VS Code + WSL extension | 2h |
| Thu | LiteLLM proxy setup, connect to Claude + Gemini, test both | 2h |
| Fri | Git + GitHub SSH config, PAIOS repo created, .env template | 1.5h |
| Sat | Mini Project M1: all base services running via docker-compose.yml | 3h |
| Sun | Review: watch AI Agent Fundamentals videos 1–2, take notes | 2h |

**End State:** WSL2 + Docker + LiteLLM proxy + GitHub repo functional.

---

### Week 2: OpenCode + MCP + First Agent
**Goal:** OpenCode operational, first MCP server built.

| Day | Activities | Time |
|---|---|---|
| Mon | OpenCode install + first session, generate a FastAPI app (M2) | 2.5h |
| Tue | MCP theory: specification, primitives, transports | 2h |
| Wed | Build MCP filesystem server in Python (M3) | 3h |
| Thu | Connect OpenCode to MCP filesystem server, test tool calls | 2h |
| Fri | MCP Inspector: debug tool calls, inspect JSON-RPC | 1.5h |
| Sat | AI Agent Fundamentals: ReAct agent from scratch, no framework | 3h |
| Sun | Read: MCP Cheat Sheet 2026, MCP Complete Guide 2026 | 2h |

**End State:** OpenCode + MCP filesystem server integrated.

---

### Week 3: CrewAI + PostgreSQL + RAG Foundation
**Goal:** First multi-agent crew, memory layer live.

| Day | Activities | Time |
|---|---|---|
| Mon | PostgreSQL + pgvector in Docker, schema created (M6) | 2.5h |
| Tue | CrewAI install, 3-agent research crew (M4 expanded) | 3h |
| Wed | LangChain RAG: ingest 10 PDFs into pgvector | 3h |
| Thu | Connect RAG as CrewAI tool, first research crew with retrieval | 2.5h |
| Fri | MCP postgresql server — expose memory to all agents | 2h |
| Sat | Intermediate Project I1: Research Crew → Notion output | 4h |
| Sun | n8n: install via Docker, complete first workflow (M5) | 2.5h |

**End State:** CrewAI + RAG + pgvector + n8n all operational.

---

### Week 4: Hermes Agent + n8n Workflows + Browser Automation
**Goal:** Persistent agent live, automation pipelines connected.

| Day | Activities | Time |
|---|---|---|
| Mon | Hermes Agent install, first run, first 2 skills | 3h |
| Tue | Hermes API server mode, connect to OpenCode | 2h |
| Wed | Playwright MCP server setup (M8 expanded) | 2.5h |
| Thu | n8n: build Agent Task Router and RAG Ingestion workflows | 3h |
| Fri | Hermes + Telegram integration: dispatch tasks from phone | 2h |
| Sat | Intermediate Project I3: 5 production n8n workflows | 4h |
| Sun | Intermediate Project I5: Hermes + Obsidian persistent agent | 3h |

**End State:** Hermes running 24/7, n8n routing tasks, Playwright browsing.

---

### Week 5: OpenHands + Computer Use + Skills Layer
**Goal:** AI software developer operational, skills system mature.

| Day | Activities | Time |
|---|---|---|
| Mon | OpenHands Docker install, first task (fix a bug in your codebase) | 3h |
| Tue | OpenHands + GitHub MCP: implement a GitHub issue | 3h |
| Wed | Computer Use API: sandboxed container, first desktop task | 2.5h |
| Thu | Skills layer: write 5 Hermes skills covering your workflows | 2h |
| Fri | FastAPI tool server: 5 custom tools wrapped as MCP | 2.5h |
| Sat | Intermediate Project I4: OpenHands full issue implementation | 4h |
| Sun | Review: LangGraph video + Semantic Router tutorial | 2h |

**End State:** OpenHands solving real issues, skills layer documented.

---

### Week 6: Advanced RAG + Semantic Router + LangGraph
**Goal:** Production-quality retrieval, intelligent agent routing.

| Day | Activities | Time |
|---|---|---|
| Mon | Hybrid RAG: add BM25 (PostgreSQL `tsvector`) to existing pipeline | 3h |
| Tue | Cohere Reranker integration | 2h |
| Wed | Agentic RAG: LangGraph state machine with RAG tools | 3h |
| Thu | Semantic Router: 10 intents mapped to 5 agents | 2.5h |
| Fri | Redis semantic cache for RAG queries | 2h |
| Sat | Intermediate Project I2: 50-doc RAG knowledge base as MCP tool | 4h |
| Sun | Intermediate Project I6: Semantic Router live in PAIOS | 3h |

**End State:** Production RAG + intelligent routing across all agents.

---

### Week 7: Integration + Observability + Security
**Goal:** Everything connected, monitored, and hardened.

| Day | Activities | Time |
|---|---|---|
| Mon | LangFuse integration: trace every agent call | 2.5h |
| Tue | Caddy reverse proxy: HTTPS for all services | 2h |
| Wed | Full PAIOS docker-compose.yml: all 12+ services | 3h |
| Thu | Approval gates in n8n + Telegram for destructive actions | 2h |
| Fri | GitHub Actions: automated test suite for PAIOS | 2h |
| Sat | Capstone 1: PAIOS Command Centre (start) | 5h |
| Sun | Capstone 1: PAIOS Command Centre (complete) | 4h |

**End State:** Unified observability, HTTPS, approval gates, CI/CD.

---

### Week 8: Capstone + Contribution + Hardening
**Goal:** Capstone systems live, first open-source contribution submitted.

| Day | Activities | Time |
|---|---|---|
| Mon | Capstone 2 or 3: choose and begin | 5h |
| Tue | Capstone continued | 5h |
| Wed | Capstone completed, documented, pushed to GitHub | 4h |
| Thu | First open-source PR: choose one project (CrewAI/n8n/OpenHands) | 3h |
| Fri | Production hardening: backup cron, log rotation, health alerts | 2.5h |
| Sat | Full system test: run all 3 capstone scenarios end-to-end | 4h |
| Sun | Write PAIOS README + architecture documentation | 2h |

**End State:** Production-grade AI Agent OS operational. First open-source contribution submitted.

---

## 22. Architecture Diagrams

### PAIOS System Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                        WINDOWS HOST                                  │
│                                                                      │
│  ┌──────────────────────────────────────────────────────────────┐   │
│  │                      WSL2 (Ubuntu 22.04)                      │   │
│  │                                                               │   │
│  │  ┌─────────────────────────────────────────────────────┐    │   │
│  │  │              DOCKER COMPOSE STACK                    │    │   │
│  │  │                                                      │    │   │
│  │  │  ┌──────────┐  ┌──────────┐  ┌──────────────────┐  │    │   │
│  │  │  │ LiteLLM  │  │  Redis   │  │   PostgreSQL +    │  │    │   │
│  │  │  │ Proxy    │  │  Cache   │  │   pgvector        │  │    │   │
│  │  │  └────┬─────┘  └──────────┘  └──────────────────┘  │    │   │
│  │  │       │                                              │    │   │
│  │  │  ┌────▼─────┐  ┌──────────┐  ┌──────────────────┐  │    │   │
│  │  │  │  OpenAI  │  │  n8n     │  │  Hermes Agent    │  │    │   │
│  │  │  │  /Anthro │  │  Workflows│  │  API Server      │  │    │   │
│  │  │  │  /Gemini │  └────┬─────┘  └─────────┬────────┘  │    │   │
│  │  │  └──────────┘       │                   │           │    │   │
│  │  │                     │                   │           │    │   │
│  │  │  ┌──────────┐  ┌────▼─────┐  ┌─────────▼────────┐  │    │   │
│  │  │  │ OpenHands│  │  CrewAI  │  │   MCP Servers    │  │    │   │
│  │  │  │ (Docker) │  │  Crews + │  │  - filesystem    │  │    │   │
│  │  │  │          │  │  Flows   │  │  - postgresql    │  │    │   │
│  │  │  └──────────┘  └──────────┘  │  - github        │  │    │   │
│  │  │                              │  - playwright     │  │    │   │
│  │  │  ┌──────────┐  ┌──────────┐  │  - obsidian      │  │    │   │
│  │  │  │ FastAPI  │  │ LangFuse │  │  - n8n           │  │    │   │
│  │  │  │ Tool Srv │  │ Observe  │  └──────────────────┘  │    │   │
│  │  │  └──────────┘  └──────────┘                        │    │   │
│  │  └─────────────────────────────────────────────────────┘    │   │
│  │                                                               │   │
│  │  ┌──────────────────────────────────────────────────────┐   │   │
│  │  │             OpenCode (Terminal Interface)              │   │   │
│  │  │  Multi-session · Provider-agnostic · LSP-integrated   │   │   │
│  │  └──────────────────────────────────────────────────────┘   │   │
│  └──────────────────────────────────────────────────────────────┘   │
│                                                                      │
│  ┌──────────────┐  ┌─────────────┐  ┌─────────────────────────┐    │
│  │   Obsidian   │  │   Notion    │  │  VS Code + WSL Extension │    │
│  │   Vault      │  │   Databases │  │  (primary editor)        │    │
│  └──────────────┘  └─────────────┘  └─────────────────────────┘    │
└─────────────────────────────────────────────────────────────────────┘

External APIs: Claude · Gemini · OpenRouter · Cohere · Telegram
```

---

### Data Flow: Research Task

```
User (Telegram)
    │ "Research LangGraph vs CrewAI for production agents"
    ▼
Hermes Agent (receives via Telegram gateway)
    │ Classifies task: research + comparison
    ▼
Semantic Router
    │ Routes to: research_crew
    ▼
CrewAI Research Crew
    ├── Researcher Agent
    │   ├── Tool: web_search (MCP)
    │   ├── Tool: playwright_scrape (MCP)
    │   └── Tool: rag_query (MCP → pgvector)
    ├── Analyst Agent
    │   ├── Tool: rag_query
    │   └── Tool: code_runner (for benchmarks)
    └── Writer Agent
        └── Tool: notion_write (MCP)
    ▼
Output: Structured comparison report
    │
    ├── → Notion database (via Notion MCP)
    ├── → Obsidian inbox (via Obsidian MCP)
    └── → Hermes skill file (if novel approach found)
    ▼
n8n Workflow: "Task Complete"
    │
    └── → Telegram notification to user
```

---

### Agent Communication Layer

```
OpenCode (primary interface)
    │
    ├── → Hermes Agent (HTTP /v1/chat via API server mode)
    │       └── Persistent memory · Skill learning · Subagents
    │
    ├── → CrewAI (Python import · direct invocation)
    │       └── Multi-agent crews · Flows
    │
    ├── → OpenHands (HTTP REST API)
    │       └── Autonomous software development
    │
    ├── → n8n (HTTP webhook trigger)
    │       └── Workflow automation
    │
    └── → MCP Servers (JSON-RPC)
            ├── filesystem
            ├── postgresql
            ├── github
            ├── playwright
            ├── obsidian
            └── notion
```

---

### Memory Architecture

```
AGENT MEMORY SYSTEM
├── Working Memory (Redis TTL: 1 hour)
│   └── Active session state, tool results cache
│
├── Episodic Memory (PostgreSQL: agent_conversations)
│   └── Full message history, searchable by session/time/agent
│
├── Semantic Memory (PostgreSQL + pgvector)
│   └── Embedded documents, RAG chunks (HNSW index)
│
├── Procedural Memory (Hermes Skills + ~/.hermes/skills/)
│   └── Reusable task approaches, workflows
│
└── Declarative Memory (Obsidian Vault + Notion DB)
    └── Human-curated facts, project knowledge
```

---

## 23. Final Production-Grade System Blueprint

### docker-compose.yml (complete PAIOS stack)

```yaml
# ~/paios/docker-compose.yml
name: paios

services:
  # ── API Gateway ──────────────────────────────────────────
  litellm:
    image: ghcr.io/berriai/litellm:main-latest
    ports: ["4000:4000"]
    env_file: .env
    volumes: ["./litellm_config.yaml:/app/config.yaml"]
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:4000/health"]
      interval: 30s

  # ── Databases ────────────────────────────────────────────
  postgres:
    image: pgvector/pgvector:pg16
    environment:
      POSTGRES_DB: paios
      POSTGRES_USER: ${POSTGRES_USER}
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
    volumes: ["postgres_data:/var/lib/postgresql/data"]
    ports: ["5432:5432"]
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${POSTGRES_USER}"]

  redis:
    image: redis:7-alpine
    volumes: ["redis_data:/data"]
    ports: ["6379:6379"]

  # ── Automation ───────────────────────────────────────────
  n8n:
    image: n8nio/n8n:latest
    ports: ["5678:5678"]
    environment:
      N8N_BASIC_AUTH_ACTIVE: "true"
      N8N_BASIC_AUTH_USER: ${N8N_USER}
      N8N_BASIC_AUTH_PASSWORD: ${N8N_PASSWORD}
      DB_TYPE: postgresdb
      DB_POSTGRESDB_HOST: postgres
      DB_POSTGRESDB_DATABASE: n8n
      DB_POSTGRESDB_USER: ${POSTGRES_USER}
      DB_POSTGRESDB_PASSWORD: ${POSTGRES_PASSWORD}
    volumes: ["n8n_data:/home/node/.n8n"]
    depends_on: [postgres]

  # ── AI Developer ─────────────────────────────────────────
  openhands:
    image: docker.all-hands.dev/all-hands-ai/openhands:0.38
    ports: ["3000:3000"]
    environment:
      SANDBOX_RUNTIME_CONTAINER_IMAGE: docker.all-hands.dev/all-hands-ai/runtime:0.38-nikolaik
      LLM_API_KEY: ${ANTHROPIC_API_KEY}
      LLM_MODEL: claude-sonnet-4-6
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - openhands_data:/.openhands-state
    extra_hosts: ["host.docker.internal:host-gateway"]

  # ── Tool Server ──────────────────────────────────────────
  fastapi-tools:
    build: ./tools-server
    ports: ["8000:8000"]
    env_file: .env
    depends_on: [postgres, redis]

  # ── MCP Servers ──────────────────────────────────────────
  mcp-filesystem:
    image: node:20-alpine
    command: npx @modelcontextprotocol/server-filesystem /workspace
    volumes: ["${HOME}/paios-workspace:/workspace"]
    ports: ["3001:3001"]

  mcp-postgres:
    image: node:20-alpine
    command: npx @modelcontextprotocol/server-postgres ${DATABASE_URL}
    environment:
      DATABASE_URL: postgresql://${POSTGRES_USER}:${POSTGRES_PASSWORD}@postgres:5432/paios
    ports: ["3002:3002"]
    depends_on: [postgres]

  mcp-playwright:
    build: ./mcp-playwright
    ports: ["3003:3003"]

  # ── Observability ────────────────────────────────────────
  langfuse:
    image: langfuse/langfuse:latest
    ports: ["3030:3000"]
    environment:
      DATABASE_URL: postgresql://${POSTGRES_USER}:${POSTGRES_PASSWORD}@postgres:5432/langfuse
      NEXTAUTH_SECRET: ${LANGFUSE_SECRET}
      NEXTAUTH_URL: http://localhost:3030
    depends_on: [postgres]

  # ── Reverse Proxy ────────────────────────────────────────
  caddy:
    image: caddy:latest
    ports: ["80:80", "443:443"]
    volumes:
      - ./Caddyfile:/etc/caddy/Caddyfile
      - caddy_data:/data

volumes:
  postgres_data:
  redis_data:
  n8n_data:
  openhands_data:
  caddy_data:
```

### Folder Structure

```
~/paios/
├── docker-compose.yml
├── .env                          # Never commit
├── .env.example                  # Commit this
├── litellm_config.yaml
├── Caddyfile
├── tools-server/
│   ├── Dockerfile
│   ├── main.py                   # FastAPI tool server
│   └── tools/
│       ├── web_search.py
│       ├── db_query.py
│       ├── n8n_trigger.py
│       ├── code_runner.py
│       └── file_writer.py
├── mcp-playwright/
│   ├── Dockerfile
│   └── server.py
├── crews/
│   ├── research_crew.py
│   ├── code_review_crew.py
│   └── content_crew.py
├── flows/
│   └── research_to_publish.py
├── rag/
│   ├── ingest.py
│   ├── retriever.py
│   └── reranker.py
├── memory/
│   ├── schema.sql
│   ├── episodic.py
│   └── semantic.py
├── router/
│   └── semantic_router.py
├── n8n-workflows/
│   ├── task_router.json
│   ├── rag_ingestion.json
│   ├── daily_digest.json
│   ├── pr_summariser.json
│   └── approval_gate.json
├── obsidian-vault/               # Symlink to Obsidian vault
└── tests/
    ├── test_rag.py
    ├── test_crews.py
    └── test_mcp.py
```

---

## 24. Open Source Contribution Roadmaps

### Hermes Agent (NousResearch)
**Repository:** https://github.com/NousResearch/hermes-agent

| Stage | Task | Difficulty |
|---|---|---|
| 1 | Fix a bug from issues labelled `good first issue` | Beginner |
| 2 | Write missing documentation for a skill type | Beginner |
| 3 | Add a new built-in tool (e.g., Obsidian integration) | Intermediate |
| 4 | Improve skill retrieval with better embedding strategy | Intermediate |
| 5 | Add Windows-native installation documentation | Beginner |

---

### CrewAI
**Repository:** https://github.com/crewaiinc/crewai
**Contribution Guide:** https://github.com/crewaiinc/crewai/blob/main/CONTRIBUTING.md

| Stage | Task | Difficulty |
|---|---|---|
| 1 | Fix a documentation error or improve example | Beginner |
| 2 | Add a new built-in tool (PostgreSQL, Obsidian, n8n) | Intermediate |
| 3 | Write a community template for a common use case | Intermediate |
| 4 | Improve MCP integration (tool discovery, error handling) | Advanced |
| 5 | Add A2A protocol support for cross-framework agents | Advanced |

---

### n8n
**Repository:** https://github.com/n8n-io/n8n
**Contribution Guide:** https://github.com/n8n-io/n8n/blob/master/CONTRIBUTING.md

| Stage | Task | Difficulty |
|---|---|---|
| 1 | Fix a node documentation bug | Beginner |
| 2 | Write a community workflow template | Beginner |
| 3 | Add a new community node (Hermes Agent, OpenHands) | Intermediate |
| 4 | Improve AI Agent node error messages | Intermediate |
| 5 | Add MCP server support to an existing node | Advanced |

---

### OpenHands
**Repository:** https://github.com/All-Hands-AI/OpenHands
**Contribution Guide:** https://github.com/All-Hands-AI/OpenHands/blob/main/CONTRIBUTING.md

| Stage | Task | Difficulty |
|---|---|---|
| 1 | Improve Windows/Docker setup documentation | Beginner |
| 2 | Fix a `good first issue` labelled bug | Beginner |
| 3 | Add a new evaluation task to SWE-bench suite | Intermediate |
| 4 | Implement a new agent action type | Advanced |

---

### Model Context Protocol
**Repository:** https://github.com/modelcontextprotocol

| Stage | Task | Difficulty |
|---|---|---|
| 1 | Improve server example documentation | Beginner |
| 2 | Add a new example server (Obsidian, pgvector) | Intermediate |
| 3 | Fix an SDK bug in Python or TypeScript | Intermediate |
| 4 | Propose a new MCP primitive in spec discussion | Advanced |

---

## Appendix: Key API Providers (API-Based, No Local Models)

| Provider | Best For | Free Tier |
|---|---|---|
| Anthropic (Claude) | Reasoning, code, computer use | No |
| Google Gemini | Embeddings, multimodal, long context | Yes (generous) |
| OpenRouter | 200+ model routing, cost optimisation | Pay-per-use |
| Groq | Fast inference (Llama, Mixtral) for tool calls | Yes |
| Cohere | Reranking, embeddings | Yes |
| OpenAI | Embeddings (text-embedding-3-small), GPT-4o | No |

**LiteLLM budget config example:**
```yaml
# litellm_config.yaml
model_list:
  - model_name: default
    litellm_params:
      model: claude-sonnet-4-6
      api_key: os.environ/ANTHROPIC_API_KEY
  - model_name: fast
    litellm_params:
      model: groq/llama3-70b-8192
      api_key: os.environ/GROQ_API_KEY
  - model_name: embeddings
    litellm_params:
      model: text-embedding-3-small
      api_key: os.environ/OPENAI_API_KEY

general_settings:
  max_budget: 50  # USD per month hard limit
  budget_duration: 1mo
```

---

## Appendix: NotebookLM Import Instructions

1. Create a new NotebookLM notebook: https://notebooklm.google.com
2. Click **Add Sources** → **Website URL**
3. Paste each URL from this document's resource sections
4. For GitHub repos, link to the README page (e.g., `https://github.com/crewaiinc/crewai`)
5. For YouTube videos, link directly (NotebookLM transcribes them automatically)
6. For documentation sites, link to the overview page
7. Upload this `.md` file directly as a source (NotebookLM accepts Markdown)

**Suggested source grouping in NotebookLM:**
- Notebook 1: Foundation (WSL2, Docker, LiteLLM)
- Notebook 2: Agent Core (OpenCode, MCP, CrewAI, Hermes)
- Notebook 3: Automation (n8n, RAG, pgvector)
- Notebook 4: Advanced (OpenHands, Computer Use, LangGraph)

---

*Last updated: June 2026 | Windows + WSL2 + API-based models + Docker | PAIOS v1.0*
