# AI Agent Operating System (PAIOS) — Windows Deployment Roadmap
### Build · Operate · Extend · Contribute
> **Version:** 2026-06 | **Platform:** Windows + WSL2 | **Models:** API-based only | **Budget:** Zero infrastructure cost  
> **Central Hub:** OpenCode → MCP → CrewAI → n8n → OpenHands → PostgreSQL/pgvector → Docker

---

## ⚠️ Reality Check Before You Start

This roadmap covers ~19 domains. Attempting all simultaneously = shipping nothing.  
**Strict priority tiers are enforced throughout:**
- 🔴 **MANDATORY** — Build this or the system doesn't exist  
- 🟡 **RECOMMENDED** — Multiplies your system's value 3–5×  
- 🟢 **OPTIONAL** — Adds capability once the core works

**Estimated total build time (serious daily effort):** 6–9 months  
**Minimum viable PAIOS (🔴 sections only):** 8–10 weeks

---

## MASTER ARCHITECTURE OVERVIEW

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        PAIOS — Personal AI Operating System                  │
│                                                                               │
│  ┌─────────────┐     MCP Protocol      ┌──────────────────────────────────┐  │
│  │  OpenCode   │◄──────────────────────►│         MCP Server Layer         │  │
│  │  (Central   │                        │  GitHub│PostgreSQL│Filesystem│   │  │
│  │  Interface) │                        │  Custom│Obsidian │Notion    │   │  │
│  └──────┬──────┘                        └──────────────────────────────────┘  │
│         │                                                                      │
│         ▼ API calls                                                            │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │                        Agent Orchestration Layer                          │  │
│  │                                                                            │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────────┐  │  │
│  │  │   CrewAI    │  │   n8n       │  │  OpenHands  │  │  Hermes Agent   │  │  │
│  │  │  (Multi-    │  │  (Workflow  │  │  (Software  │  │  (Task/Memory   │  │  │
│  │  │   Agent)    │  │  Automation)│  │   Dev Agent)│  │   Management)   │  │  │
│  │  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └────────┬────────┘  │  │
│  └─────────┼────────────────┼────────────────┼──────────────────┼───────────┘  │
│            │                │                │                  │               │
│            └────────────────┴────────────────┴──────────────────┘               │
│                                      │                                           │
│                                      ▼                                           │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │                          Infrastructure Layer                              │  │
│  │                                                                            │  │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │  │
│  │  │  PostgreSQL  │  │    Docker    │  │   GitHub     │  │  API Models  │  │  │
│  │  │  + pgvector  │  │  Containers  │  │  + Actions   │  │  (Claude/    │  │  │
│  │  │  (Memory+RAG)│  │  (Isolation) │  │  (CI/CD)     │  │   Gemini/GPT)│  │  │
│  │  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘  │  │
│  │                                                                            │  │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                   │  │
│  │  │  Obsidian    │  │    Notion    │  │   Browser    │                   │  │
│  │  │  (Local KB)  │  │  (Team KB)   │  │  Automation  │                   │  │
│  │  └──────────────┘  └──────────────┘  │ (Playwright) │                   │  │
│  │                                       └──────────────┘                   │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

---

## DATA FLOW DIAGRAM

```
User Intent (natural language)
        │
        ▼
  OpenCode TUI  ──────────────────────────────────────────────┐
        │                                                       │
   [Parses intent]                                        [Code tasks]
        │                                                       │
        ├──── Simple tool call ──► MCP Server ──► Tool Result   │
        │                                                       │
        ├──── Multi-step task ──► CrewAI Crew                  │
        │         │                    │                        │
        │    [Planner Agent]    [Worker Agents]                 │
        │         │                    │                        │
        │         └────────────────────┘                       │
        │                    │                                  │
        ├──── Automation ──► n8n Workflow                      │
        │                    │                                  │
        │         [Trigger → Node Chain → Output]              │
        │                                                       │
        ├──── Software Dev ──► OpenHands                       │
        │                    │                                  │
        │         [Sandbox → Code → Tests → PR]                │
        │                                                       │
        └──── Memory Read/Write ──► PostgreSQL/pgvector ◄──────┘
                                          │
                                   [Vector Search]
                                          │
                                   Obsidian/Notion
                                   (Knowledge Base)
```

---

## CHRONOLOGICAL LEARNING PATH

```
WEEK 1-2    WEEK 3-4    WEEK 5-6    WEEK 7-9    WEEK 10-12   WEEK 13-16   WEEK 17-24
   │            │           │           │             │            │            │
Foundation  OpenCode    MCP Layer   CrewAI      n8n + DB     OpenHands    Production
+ WSL2      + Docker    + Tools     Multi-Agent RAG + Mem    + Browser    + Contrib
   │            │           │           │             │            │            │
[S01-S03]   [S04-S05]  [S06-S07]  [S08-S10]   [S11-S13]   [S14-S16]   [S17-S19]
```

---

## SECTION 01 — Foundation
**Priority:** 🔴 MANDATORY | **Difficulty:** Beginner | **Study Time:** 1–2 weeks

### Prerequisites
- Basic Python (functions, classes, pip)
- Comfort with the command line
- GitHub account

### Learning Outcomes
- WSL2 + Ubuntu running on Windows with full Python toolchain
- Git flow, virtual environments, `.env` secrets management
- Docker Desktop installed and first container running
- API keys for Claude/Gemini/GPT configured

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| WSL2 Complete Setup for Developers 2025 | NetworkChuck | Search: "NetworkChuck WSL2 2025" | Best Windows-Linux bridge setup |
| Python Virtual Environments Full Guide | Corey Schafer | Search: "Corey Schafer venv" | Foundation for every Python project |
| Git and GitHub for Beginners – Crash Course | freeCodeCamp | `https://www.youtube.com/watch?v=RGOj5yH7evk` | Mandatory Git foundation |
| Docker Tutorial for Beginners | TechWorld with Nana | Search: "TechWorld Nana Docker beginner" | Best Docker intro for devs |
| Environment Variables & .env Files | Corey Schafer | Search: "Corey Schafer dotenv python" | Secrets hygiene from day one |

### Best YouTube Playlists

| Playlist | Channel | URL |
|----------|---------|-----|
| Python Tutorials for Beginners | Corey Schafer | `https://www.youtube.com/playlist?list=PL-osiE80TeTt2d9bfVyTiXJA-UTHn6WwU` |
| Docker Tutorials | TechWorld with Nana | Search: "TechWorld Nana Docker playlist" |

### Official Documentation (NotebookLM-Compatible Sources)
- WSL Docs: `https://learn.microsoft.com/en-us/windows/wsl/install`
- Python Packaging: `https://packaging.python.org/en/latest/`
- Docker Desktop for Windows: `https://docs.docker.com/desktop/install/windows-install/`
- Git Reference: `https://git-scm.com/docs`

### Mini Project
> **Environment Bootstrap Script** — Write a Python script that reads a `.env` file, validates all required API keys are present, and prints a health check table. Run it inside WSL2.

---

## SECTION 02 — AI Agent Fundamentals
**Priority:** 🔴 MANDATORY | **Difficulty:** Beginner-Intermediate | **Study Time:** 1 week

### Prerequisites
- Section 01 complete
- Basic Python async understanding

### Learning Outcomes
- Understand ReAct, Plan-and-Execute, and tool-use agent patterns
- Build a basic tool-calling agent using the Anthropic API directly
- Understand tokens, context windows, and cost management
- Know when to use agents vs. simple LLM calls

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| AI Agents Explained: How They Actually Work | Andrej Karpathy | Search: "Karpathy agents 2025" | Best conceptual foundation |
| Build Your First AI Agent from Scratch | Sam Witteveen | Search: "Sam Witteveen agent from scratch" | Hands-on, no frameworks |
| ReAct Prompting Explained | AI Jason | Search: "AI Jason ReAct agent" | Core agent pattern you'll use everywhere |
| LLM Tool Use / Function Calling Deep Dive | DeepLearning.AI | Search: "DeepLearning function calling tutorial" | How tools actually work under the hood |
| Agentic AI Patterns: When to Use What | LangChain YouTube | Search: "LangChain agentic patterns 2025" | Avoid over-engineering |

### Best YouTube Playlists

| Playlist | Channel | URL |
|----------|---------|-----|
| Building AI Agents | Sam Witteveen | Search: "Sam Witteveen AI Agents playlist" |
| Short Courses (AI Agents) | DeepLearning.AI | `https://www.deeplearning.ai/short-courses/` |

### Official Documentation
- Anthropic Tool Use: `https://docs.anthropic.com/en/docs/build-with-claude/tool-use`
- OpenAI Function Calling: `https://platform.openai.com/docs/guides/function-calling`
- LangGraph Conceptual Guide: `https://langchain-ai.github.io/langgraph/concepts/`

### Mini Project
> **Raw Tool-Calling Agent** — Using only the Anthropic SDK (no frameworks), build an agent with 3 tools: `search_web`, `read_file`, `write_file`. No LangChain, no CrewAI. Understand what frameworks abstract away.

---

## SECTION 03 — OpenCode Ecosystem
**Priority:** 🔴 MANDATORY | **Difficulty:** Beginner | **Study Time:** 3–5 days

### What It Is
OpenCode is a terminal-native AI coding agent with 160K+ GitHub stars, built in Go by the SST/Anomaly team. It supports 75+ model providers, MCP servers, custom agents, and LSP integration. **This is your central command interface for the entire PAIOS.**

### Prerequisites
- Section 01 complete
- API key for at least one provider (Claude recommended)

### Learning Outcomes
- OpenCode installed and running on Windows/WSL2
- Custom agents configured via Markdown config
- Provider switching (Claude ↔ Gemini ↔ GPT) mid-session
- `opencode.json` configured with first MCP tools
- Non-interactive scripting mode (`opencode -p "prompt"`)
- Context auto-compaction understood

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| OpenCode Full Setup & Demo | Theo (t3.gg) | Search: "Theo opencode setup 2025" | Maintainer-adjacent deep dive |
| OpenCode vs Claude Code vs Cursor | Fireship | Search: "Fireship opencode cursor comparison" | Understand the landscape before committing |
| OpenCode + Gemini 2.5 Pro Setup | Various | Search: "OpenCode Gemini 2.5 Pro setup" | Official demo video (linked from GitHub README) |
| OpenCode MCP Integration Tutorial | Matt Pocock / SST | Search: "opencode MCP tools setup" | Critical for PAIOS integration |
| Custom Agents in OpenCode | Various | Search: "opencode custom agent markdown config" | Build your own specialized agents |

### Official Sources (NotebookLM-Compatible)
- GitHub: `https://github.com/opencode-ai/opencode`
- Official Site: `https://opencode.ai/`
- Docs (search from site): `https://opencode.ai/docs`

### Key Configuration (`opencode.json`)
```json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "anthropic": { "apiKey": "${ANTHROPIC_API_KEY}" }
  },
  "model": "claude-sonnet-4-5",
  "mcp": {
    "filesystem": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-filesystem", "/home/user/projects"] },
    "postgres": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-postgres"], "env": { "POSTGRES_URL": "${DATABASE_URL}" } },
    "github": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-github"], "env": { "GITHUB_TOKEN": "${GITHUB_TOKEN}" } }
  }
}
```

### Mini Project
> **OpenCode + 3 MCP Tools** — Configure OpenCode with filesystem, GitHub, and a custom Python MCP server. Write a prompt that uses all three tools in sequence to read a repo, analyze it, and create a GitHub issue.

### Architecture: OpenCode as Central Hub
```
                    opencode.json
                         │
                    ┌────▼────┐
                    │OpenCode │
                    │  TUI    │
                    └────┬────┘
          ┌──────────────┼──────────────┐
          │              │              │
     ┌────▼────┐    ┌────▼────┐   ┌────▼────┐
     │MCP:     │    │MCP:     │   │MCP:     │
     │Filesystem│   │GitHub   │   │PostgreSQL│
     └─────────┘   └─────────┘   └─────────┘
          │              │              │
     Local Files    GitHub API    Database
```

---

## SECTION 04 — MCP Servers
**Priority:** 🔴 MANDATORY | **Difficulty:** Intermediate | **Study Time:** 1–2 weeks

### Prerequisites
- Section 03 complete
- Basic understanding of REST APIs
- Node.js installed (for official MCP servers)

### Learning Outcomes
- Understand MCP host/client/server architecture
- Use all official Anthropic reference servers
- Build a custom MCP server in Python (FastMCP)
- Connect MCP servers to OpenCode, CrewAI, and n8n
- Implement secure MCP with authentication

### What MCP Solves
```
Without MCP (N×M problem):
Every AI Tool × Every Service = Custom Integration
  Claude + GitHub    = integration 1
  Claude + Postgres  = integration 2
  CrewAI + GitHub   = integration 3
  CrewAI + Postgres = integration 4
  ... N×M total

With MCP:
GitHub builds ONE server → ALL AI tools connect
Postgres builds ONE server → ALL AI tools connect
= N+M total integrations
```

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| MCP Explained in 10 Minutes | Fireship | Search: "Fireship MCP explained" | Best conceptual intro, no fluff |
| Build Your First MCP Server (Python) | IndyDevDan | Search: "IndyDevDan MCP server python" | Trusted community builder |
| MCP Deep Dive – Hosts, Clients, Servers | Matt Pocock | Search: "Matt Pocock MCP architecture" | Best architectural breakdown |
| MCP with CrewAI Integration | Sam Witteveen | Search: "Sam Witteveen MCP CrewAI" | Critical for PAIOS integration |
| FastMCP – Build MCP Servers Fast | Various | Search: "FastMCP python tutorial 2025" | Python-first approach |
| Official MCP Quickstart Walkthrough | Anthropic | `https://modelcontextprotocol.io/quickstart/server` | Canonical source |

### Best YouTube Playlists

| Playlist | Channel | URL |
|----------|---------|-----|
| MCP Tutorials | IndyDevDan | Search: "IndyDevDan MCP playlist" |
| AI Agent Tools & MCP | Sam Witteveen | Search: "Sam Witteveen MCP playlist 2025" |

### Official Sources (NotebookLM-Compatible)
- MCP Spec: `https://modelcontextprotocol.io/`
- Official Servers: `https://github.com/modelcontextprotocol/servers`
- Python SDK: `https://github.com/modelcontextprotocol/python-sdk`
- TypeScript SDK: `https://github.com/modelcontextprotocol/typescript-sdk`
- MCP Registry: `https://github.com/modelcontextprotocol/registry`

### Essential MCP Servers for PAIOS

| Server | Package | Purpose |
|--------|---------|---------|
| Filesystem | `@modelcontextprotocol/server-filesystem` | File read/write |
| PostgreSQL | `@modelcontextprotocol/server-postgres` | DB queries |
| GitHub | `@modelcontextprotocol/server-github` | Repo operations |
| Git | `@modelcontextprotocol/server-git` | Local git ops |
| Brave Search | `@modelcontextprotocol/server-brave-search` | Web search |
| Fetch | `@modelcontextprotocol/server-fetch` | HTTP requests |
| Memory | `@modelcontextprotocol/server-memory` | KV memory store |
| Sequential Thinking | `@modelcontextprotocol/server-sequential-thinking` | Reasoning chain |

### Custom MCP Server Template (Python/FastMCP)
```python
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("PAIOS Custom Tools")

@mcp.tool()
def query_agent_memory(query: str) -> str:
    """Search agent memory via vector similarity in PostgreSQL"""
    # Implementation: pgvector similarity search
    return results

@mcp.tool()
def store_knowledge(content: str, tags: list[str]) -> str:
    """Store knowledge with embeddings in PostgreSQL"""
    # Implementation: embed + store
    return "stored"

if __name__ == "__main__":
    mcp.run()
```

### Mini Project
> **PAIOS MCP Hub** — Build a custom Python MCP server with 5 tools: memory search, knowledge store, task queue read, agent status check, and a Notion/Obsidian bridge. Connect it to OpenCode.

### Intermediate Project
> **MCP Orchestration Layer** — Create an MCP server registry that automatically discovers and loads all available MCP servers from a config file. Implement health checks and auto-restart.

---

## SECTION 05 — Skills, Tools & Plugins
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Intermediate | **Study Time:** 1 week

### Prerequisites
- Sections 03–04 complete
- FastAPI basics (install and run a simple endpoint)

### Learning Outcomes
- Understand the difference: MCP Tools vs. CrewAI Tools vs. OpenCode Plugins
- Build reusable agent skills as Python packages
- Create a personal skill library for PAIOS
- Use LiteLLM as a unified model gateway

### Tool Architecture in PAIOS
```
PAIOS Tool Hierarchy:
│
├── MCP Tools (protocol-level, any agent can use)
│   ├── Filesystem operations
│   ├── Database queries  
│   └── API calls
│
├── CrewAI Tools (framework-level, crew-specific)
│   ├── Web scraping
│   ├── Code execution
│   └── Document analysis
│
├── OpenCode Plugins (editor-level, coding context)
│   ├── Linting integration
│   ├── Test runners
│   └── Deployment hooks
│
└── Custom Skill Packages (reusable Python libs)
    ├── skills/web_research.py
    ├── skills/document_parser.py
    └── skills/data_analyst.py
```

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| LiteLLM – One API for 100+ Models | Ishaan Jaff | Search: "LiteLLM tutorial 2025" | Unify all your model calls |
| Build Custom CrewAI Tools | CrewAI Official | `https://www.youtube.com/@crewAIInc` | Official maintainer content |
| FastAPI for AI Applications | ArjanCodes | Search: "ArjanCodes FastAPI AI 2025" | Best Python API patterns |
| Building Reusable Agent Tools | LangChain | Search: "LangChain custom tools best practices" | Tool design patterns |

### Official Sources
- LiteLLM: `https://docs.litellm.ai/`
- CrewAI Tools: `https://docs.crewai.com/en/concepts/tools`
- FastAPI: `https://fastapi.tiangolo.com/`

### Mini Project
> **Personal Skill Library** — Create a `paios_skills` Python package with 10 reusable tools (web search, PDF parse, code execute, memory read, image analyze, etc.). Wrap them for both MCP and CrewAI use.

---

## SECTION 06 — CrewAI & Multi-Agent Systems
**Priority:** 🔴 MANDATORY | **Difficulty:** Intermediate | **Study Time:** 2 weeks

### Prerequisites
- Sections 02, 05 complete
- Python classes and decorators comfortable
- At least one API key with sufficient quota

### Learning Outcomes
- Build multi-agent Crews with defined roles, goals, and backstories
- Use CrewAI Flows for event-driven, stateful orchestration
- Implement agent memory (short-term, long-term, entity, contextual)
- Connect CrewAI agents to MCP servers
- Deploy production Flows with checkpointing
- Understand A2A (Agent-to-Agent) protocol integration

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| CrewAI Full Course 2025 | CrewAI Official | `https://www.youtube.com/@crewAIInc` | Official maintainer tutorials |
| Build Multi-Agent Systems with CrewAI | Siddhardhan | `https://www.youtube.com/watch?v=qsrl2DHYi1Y` | Highly rated community tutorial |
| CrewAI Flows – Enterprise Architecture | CrewAI Official | Search: "CrewAI Flows tutorial 2025" | Production-grade patterns |
| CrewAI + MCP Integration | Sam Witteveen | Search: "CrewAI MCP tools 2025" | Critical for PAIOS |
| Multi-Agent Memory Systems | Various | Search: "CrewAI memory system deep dive" | Agent memory implementation |
| CrewAI vs LangGraph – Which to Use? | Various | Search: "CrewAI LangGraph comparison 2025" | Make informed architectural choices |

### Best YouTube Playlists

| Playlist | Channel | URL |
|----------|---------|-----|
| CrewAI Official Tutorials | CrewAI Inc | `https://www.youtube.com/@crewAIInc` |
| AI Agents & CrewAI | Mervin Praison | Search: "Mervin Praison CrewAI playlist" |

### Official Sources (NotebookLM-Compatible)
- Docs: `https://docs.crewai.com/`
- GitHub: `https://github.com/crewaiinc/crewai`
- Community Courses: `https://learn.crewai.com`
- Flows Guide: `https://docs.crewai.com/en/concepts/flows`

### PAIOS CrewAI Architecture
```python
# PAIOS Research + Action Crew
from crewai import Agent, Task, Crew, Flow
from crewai.tools import MCPServerAdapter

# Connect to PAIOS MCP servers
mcp_tools = MCPServerAdapter(config_path="opencode.json")

researcher = Agent(
    role="Research Analyst",
    goal="Find, synthesize, and store knowledge in PAIOS memory",
    tools=[mcp_tools.get_tool("brave_search"), 
           mcp_tools.get_tool("store_knowledge")],
    memory=True
)

coder = Agent(
    role="Software Engineer",
    goal="Implement solutions and push to GitHub",
    tools=[mcp_tools.get_tool("filesystem"),
           mcp_tools.get_tool("github")],
    memory=True
)

class PAIOSFlow(Flow):
    @start()
    def receive_task(self): ...
    
    @listen(receive_task)
    def research_phase(self): ...
    
    @listen(research_phase)
    def implement_phase(self): ...
```

### Mini Projects
1. **Research Crew** — 3-agent crew: Researcher → Analyzer → Writer. Given a topic, produce a structured report stored in Obsidian.
2. **Code Review Crew** — Planner + Coder + Reviewer agents that take a GitHub issue, write code, review it, and open a PR.

### Intermediate Project
> **PAIOS Orchestration Crew** — A meta-crew that receives natural language tasks, decomposes them into sub-tasks, delegates to specialist crews (research/code/write/analyze), aggregates results, and stores in PostgreSQL memory.

---

## SECTION 07 — Hermes Agent
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Intermediate | **Study Time:** 1 week

### What It Is
Hermes refers to using Hermes-series models (NousResearch) and/or building a Hermes-style agent architecture with strong tool use, function calling, and memory management capabilities. In PAIOS context, Hermes serves as a task management and memory orchestration layer.

### Prerequisites
- Sections 04, 06 complete
- Understanding of structured outputs and function calling

### Learning Outcomes
- Deploy Hermes-style structured tool-calling agents via API
- Build a task queue and priority management system
- Implement agent-to-agent communication protocols
- Create persistent agent identity and memory profiles

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| NousResearch Hermes Models Guide | Various | Search: "Hermes 3 tool calling tutorial 2025" | Model-specific capabilities |
| Building Agent Memory Systems | Sam Witteveen | Search: "Sam Witteveen agent memory 2025" | Memory architecture patterns |
| Structured Outputs for AI Agents | ArjanCodes | Search: "ArjanCodes structured outputs agents" | Clean agent interfaces |
| Agent Identity & Persistence | Various | Search: "persistent AI agent identity Python" | Long-running agent design |

### Official Sources
- NousResearch: `https://github.com/NousResearch`
- Hermes Models: `https://huggingface.co/NousResearch`
- OpenRouter (API access): `https://openrouter.ai/`

### PAIOS Hermes Role
```
Hermes Agent in PAIOS:
├── Task Manager → Receives, queues, prioritizes tasks
├── Memory Librarian → Reads/writes to PostgreSQL memory
├── Agent Router → Decides which crew/agent handles each task
└── Progress Tracker → Monitors task completion, stores outcomes
```

### Mini Project
> **Task Queue Agent** — Build a Hermes-style agent that manages a PostgreSQL task queue: accepts tasks via API, assigns to appropriate CrewAI crew, monitors completion, stores results in memory.

---

## SECTION 08 — n8n Automation
**Priority:** 🔴 MANDATORY | **Difficulty:** Beginner-Intermediate | **Study Time:** 1–2 weeks

### Prerequisites
- Docker Desktop running
- Basic understanding of webhooks and REST APIs

### Learning Outcomes
- Run n8n locally via Docker
- Build AI agent workflows with memory, tools, and sub-agents
- Connect n8n to PostgreSQL, GitHub, Notion, Obsidian webhook
- Implement error handling, retry logic, and monitoring
- Trigger CrewAI crews from n8n workflows
- Use n8n's MCP support to connect agent tools

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| N8N Full Tutorial: Building AI Agents 2025 | AI Foundations | `https://www.youtube.com/watch?v=ZbIVOy_GPyQ` | Best beginner-to-intermediate n8n AI tutorial |
| n8n Self-Hosting Complete Guide | n8n Official | `https://www.youtube.com/c/n8n-io` | Official channel - all self-hosting content |
| n8n + AI Agents Deep Dive | Leon Van Zyl | Search: "Leon Van Zyl n8n AI agents 2025" | Trusted community n8n expert |
| n8n MCP Integration 2025 | Various | Search: "n8n MCP server integration tutorial" | PAIOS integration critical path |
| n8n PostgreSQL + Memory Agents | Various | Search: "n8n PostgreSQL agent memory workflow" | Database-backed n8n agents |
| n8n Error Handling Best Practices | n8n Official | Search: "n8n error handling production 2025" | Production readiness |

### Best YouTube Playlists

| Playlist | Channel | URL |
|----------|---------|-----|
| n8n Official Tutorials | n8n | `https://www.youtube.com/playlist?list=PLlET0GsrLUL5HKJk1rb7t32sAs_iAlpZe` |
| n8n AI Automation | Leon Van Zyl | Search: "Leon Van Zyl n8n playlist" |

### Official Sources (NotebookLM-Compatible)
- Docs: `https://docs.n8n.io/`
- GitHub: `https://github.com/n8n-io/n8n`
- Templates: `https://n8n.io/workflows/`
- Community Forum: `https://community.n8n.io/`
- AI Agent Template: `https://n8n.io/workflows/6270-build-your-first-ai-agent/`

### Docker Setup
```yaml
# docker-compose.yml for n8n + PostgreSQL
version: '3'
services:
  n8n:
    image: n8nio/n8n
    ports: ["5678:5678"]
    environment:
      - DB_TYPE=postgresdb
      - DB_POSTGRESDB_HOST=postgres
      - DB_POSTGRESDB_DATABASE=n8n
      - N8N_ENCRYPTION_KEY=${N8N_ENCRYPTION_KEY}
    volumes:
      - n8n_data:/home/node/.n8n
    depends_on: [postgres]
  postgres:
    image: pgvector/pgvector:pg16
    environment:
      - POSTGRES_PASSWORD=${POSTGRES_PASSWORD}
    volumes:
      - pg_data:/var/lib/postgresql/data
```

### PAIOS Automation Flows

| Flow Name | Trigger | Action | Output |
|-----------|---------|--------|--------|
| Knowledge Sync | Obsidian file change | Extract + embed | pgvector |
| GitHub Monitor | New issue | CrewAI code crew | PR draft |
| Daily Digest | Cron 9am | Summarize memory | Notion page |
| Alert Handler | Webhook | Route to agent | Action |
| Memory Maintenance | Cron weekly | Prune + consolidate | DB update |

### Mini Projects
1. **Auto-Researcher** — Webhook → search web → summarize with Claude → store in Notion
2. **GitHub Issue Handler** — GitHub webhook → n8n → trigger CrewAI crew → post PR

### Intermediate Project
> **PAIOS Automation Hub** — 10 connected n8n workflows that form the event backbone of PAIOS: knowledge ingestion, task routing, memory maintenance, alert handling, and daily synthesis.

---

## SECTION 09 — OpenHands
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Intermediate-Advanced | **Study Time:** 1–2 weeks

### What It Is
OpenHands (formerly OpenDevin, by All Hands AI) is an MIT-licensed AI software development agent platform. It can modify code, run commands, browse the web, call APIs, and open PRs — fully autonomously. The SDK is a composable Python library for building production coding agents.

### Prerequisites
- Docker Desktop (OpenHands runs in Docker sandbox)
- GitHub token configured
- Sections 02, 06 complete

### Learning Outcomes
- Run OpenHands locally via Docker
- Use OpenHands CLI for headless automation
- Integrate OpenHands with GitHub Actions for CI/CD
- Use OpenHands SDK to build custom software agents
- Connect OpenHands to PAIOS MCP layer
- Understand sandboxed code execution security

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| OpenHands (OpenDevin) Full Setup | Various | Search: "OpenHands OpenDevin setup 2025 Docker" | Setup walkthrough |
| OpenHands vs Claude Code vs Devin | Various | Search: "OpenHands comparison coding agent 2025" | Understand positioning |
| OpenHands SDK Deep Dive | All Hands AI | Search: "OpenHands SDK tutorial 2025" | Build custom agents |
| Autonomous GitHub PR with OpenHands | Various | Search: "OpenHands GitHub PR automation" | Core PAIOS use case |
| OpenHands in Production | Various | Search: "OpenHands production deployment 2025" | Scale beyond laptop |

### Official Sources (NotebookLM-Compatible)
- Docs: `https://docs.all-hands.dev/`
- SDK Docs: `https://docs.openhands.dev/sdk`
- GitHub (All Hands): `https://github.com/All-Hands-AI/OpenHands`
- GitHub (Community): `https://github.com/OpenHands/OpenHands`
- Paper (ICLR 2025): `https://openreview.net/pdf/95990590797cff8b93c33af989ecf4ac58bde9bb.pdf`

### OpenHands in PAIOS
```
GitHub Issue Created
        │
        ▼
   n8n Webhook Trigger
        │
        ▼
   OpenHands Agent
   ┌────────────────────────────┐
   │  1. Read issue             │
   │  2. Clone repo             │
   │  3. Write code (sandbox)   │
   │  4. Run tests              │
   │  5. Fix failures           │
   │  6. Open PR                │
   └────────────────────────────┘
        │
        ▼
   GitHub PR Created
        │
        ▼
   CrewAI Review Crew
   (human-in-the-loop gate)
```

### Mini Project
> **Auto-PR Bot** — Connect OpenHands to a test GitHub repo. Give it a "fix the bug in file X" issue. Let it autonomously write the fix, run tests, and open a PR. Review and merge.

---

## SECTION 10 — Docker & Infrastructure
**Priority:** 🔴 MANDATORY | **Difficulty:** Intermediate | **Study Time:** 1 week

### Prerequisites
- Section 01 complete (Docker Desktop installed)
- Basic understanding of networking

### Learning Outcomes
- Build multi-service Docker Compose stacks for PAIOS
- Understand container networking (bridge, host modes)
- Implement health checks and auto-restart policies
- Use Docker volumes for persistent data
- Build custom images for PAIOS agents
- GitHub Actions for automated image builds

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| Docker Compose Tutorial | TechWorld with Nana | Search: "TechWorld Nana Docker Compose 2025" | Best practical Docker Compose guide |
| Docker Networking Explained | NetworkChuck | Search: "NetworkChuck Docker networking" | Critical for multi-service PAIOS |
| Docker for AI/ML Projects | Sentdex | Search: "Sentdex Docker AI project" | AI-specific Docker patterns |
| GitHub Actions + Docker | TechWorld with Nana | Search: "TechWorld Nana GitHub Actions Docker" | CI/CD for PAIOS |
| Docker Security Best Practices | Various | Search: "Docker security production 2025" | Don't skip this |

### Official Sources
- Docker Docs: `https://docs.docker.com/`
- Docker Compose Spec: `https://docs.docker.com/compose/`
- GitHub Actions: `https://docs.github.com/en/actions`

### PAIOS Full Docker Stack
```yaml
# Complete PAIOS docker-compose.yml
services:
  postgres:
    image: pgvector/pgvector:pg16
    environment: { POSTGRES_PASSWORD: ${PG_PASS}, POSTGRES_DB: paios }
    volumes: [pg_data:/var/lib/postgresql/data]
    healthcheck: { test: ["CMD", "pg_isready"], interval: 10s }

  redis:
    image: redis:7-alpine
    volumes: [redis_data:/data]

  n8n:
    image: n8nio/n8n:latest
    ports: ["5678:5678"]
    depends_on: [postgres, redis]
    environment:
      - DB_TYPE=postgresdb
      - QUEUE_BULL_REDIS_HOST=redis

  openhands:
    image: ghcr.io/all-hands-ai/openhands:latest
    ports: ["3000:3000"]
    volumes: [/var/run/docker.sock:/var/run/docker.sock]
    environment: { LLM_API_KEY: ${ANTHROPIC_API_KEY} }

  paios_api:
    build: ./api
    ports: ["8000:8000"]
    depends_on: [postgres, redis]

volumes:
  pg_data:
  redis_data:
```

### Mini Project
> **PAIOS Stack Launch** — Single `docker-compose up` that starts PostgreSQL+pgvector, Redis, n8n, and a custom FastAPI health dashboard. All services communicate, all data persists.

---

## SECTION 11 — PostgreSQL & Agent Memory
**Priority:** 🔴 MANDATORY | **Difficulty:** Intermediate | **Study Time:** 1–2 weeks

### Prerequisites
- Section 10 complete (PostgreSQL running in Docker)
- Basic SQL knowledge

### Learning Outcomes
- Enable and use pgvector for semantic similarity search
- Design an agent memory schema (episodic, semantic, procedural)
- Build a Python memory manager class used across all PAIOS agents
- Implement memory consolidation and pruning strategies
- Use pgvector with CrewAI's memory system

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| pgvector Full Tutorial | Supabase | Search: "Supabase pgvector tutorial 2025" | Best pgvector practical guide |
| Vector Databases Explained | Fireship | Search: "Fireship vector database explained" | Conceptual foundation |
| AI Memory Systems Architecture | Various | Search: "AI agent memory architecture 2025" | Design patterns |
| PostgreSQL Performance Tuning | Hussein Nasser | Search: "Hussein Nasser PostgreSQL performance" | Production readiness |
| Building Agent Long-Term Memory | Sam Witteveen | Search: "Sam Witteveen agent long term memory" | Practical implementation |

### Official Sources
- pgvector: `https://github.com/pgvector/pgvector`
- PostgreSQL Docs: `https://www.postgresql.org/docs/`
- CrewAI Memory: `https://docs.crewai.com/en/concepts/memory`

### PAIOS Memory Schema
```sql
-- Agent Memory Database Schema
CREATE EXTENSION IF NOT EXISTS vector;

-- Episodic memory: what happened
CREATE TABLE episodic_memory (
    id SERIAL PRIMARY KEY,
    agent_id VARCHAR(100),
    session_id UUID,
    event_type VARCHAR(50),  -- 'task', 'tool_call', 'observation'
    content TEXT,
    embedding vector(1536),
    metadata JSONB,
    importance FLOAT DEFAULT 0.5,
    created_at TIMESTAMPTZ DEFAULT NOW()
);

-- Semantic memory: what is known
CREATE TABLE semantic_memory (
    id SERIAL PRIMARY KEY,
    concept VARCHAR(500),
    content TEXT,
    embedding vector(1536),
    tags TEXT[],
    source VARCHAR(200),
    confidence FLOAT,
    created_at TIMESTAMPTZ DEFAULT NOW(),
    last_accessed TIMESTAMPTZ
);

-- Task registry
CREATE TABLE task_registry (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    task_type VARCHAR(100),
    status VARCHAR(50),  -- 'pending', 'running', 'done', 'failed'
    assigned_to VARCHAR(100),
    payload JSONB,
    result JSONB,
    created_at TIMESTAMPTZ DEFAULT NOW(),
    completed_at TIMESTAMPTZ
);

-- Vector indexes
CREATE INDEX ON episodic_memory USING ivfflat (embedding vector_cosine_ops);
CREATE INDEX ON semantic_memory USING ivfflat (embedding vector_cosine_ops);
```

### Python Memory Manager
```python
class PAIOSMemory:
    def store(self, content: str, memory_type: str, agent_id: str): ...
    def recall(self, query: str, limit: int = 5) -> list[dict]: ...
    def consolidate(self): ...  # Merge similar memories
    def prune(self, days: int = 30): ...  # Remove old low-importance memories
```

### Mini Project
> **Memory-Backed Agent** — Build a CrewAI agent that stores every task result in PostgreSQL memory and recalls relevant context at the start of each new task. Measure how memory improves task quality.

---

## SECTION 12 — Obsidian Knowledge Management
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Beginner | **Study Time:** 3–5 days

### Prerequisites
- PostgreSQL running (for indexing)
- Section 11 basic understanding

### Learning Outcomes
- Structure Obsidian vault as PAIOS knowledge base
- Use Obsidian Dataview for dynamic agent task boards
- Sync vault to pgvector for semantic search
- Connect agents to Obsidian via custom MCP server
- Build a personal knowledge graph that agents can query

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| Obsidian for Developers 2025 | No Boilerplate | Search: "No Boilerplate Obsidian developers" | Best dev-focused Obsidian guide |
| Obsidian Dataview Complete Guide | Nicole van der Hoeven | Search: "Nicole van der Hoeven Dataview" | Dynamic views for agent dashboards |
| Obsidian + AI Integration | Various | Search: "Obsidian AI agent integration MCP 2025" | PAIOS-relevant integration |
| Building a Second Brain | Tiago Forte | Search: "Tiago Forte second brain Obsidian" | PKM philosophy |

### Official Sources
- Obsidian Docs: `https://help.obsidian.md/`
- Dataview Plugin: `https://blacksmithgu.github.io/obsidian-dataview/`
- Obsidian API: `https://github.com/obsidianmd/obsidian-api`

### PAIOS Vault Structure
```
PAIOS-Vault/
├── 00-Inbox/          ← agent drops unsorted knowledge here
├── 01-Projects/       ← active agent projects
├── 02-Knowledge/      ← processed knowledge base
├── 03-Memory/         ← agent memory exports
├── 04-Tasks/          ← task board (Dataview)
├── 05-Templates/      ← agent output templates
└── 99-Archive/        ← completed items
```

### Mini Project
> **Obsidian MCP Server** — Build a custom MCP server that exposes Obsidian vault operations: `create_note`, `search_notes`, `update_note`, `get_backlinks`. Connect to OpenCode.

---

## SECTION 13 — Notion Knowledge Management
**Priority:** 🟢 OPTIONAL | **Difficulty:** Beginner | **Study Time:** 3–5 days

### Prerequisites
- Notion account, basic API familiarity

### Learning Outcomes
- Use Notion API as a structured agent output store
- Build agent dashboards in Notion (task tracking, knowledge base)
- Connect n8n to Notion for automated page creation
- Use Notion MCP server for agent read/write access

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| Notion API Complete Guide | Tom Scott | Search: "Notion API tutorial 2025 Python" | API foundation |
| n8n + Notion Automation | Leon Van Zyl | Search: "Leon Van Zyl n8n Notion" | Direct PAIOS integration |
| Notion as AI Agent Memory | Various | Search: "Notion AI agent knowledge base 2025" | Use case walkthrough |

### Official Sources
- Notion API: `https://developers.notion.com/`
- Notion MCP Server: Search npm for `@notionhq/notion-mcp-server`

---

## SECTION 14 — RAG Systems
**Priority:** 🔴 MANDATORY | **Difficulty:** Intermediate-Advanced | **Study Time:** 2 weeks

### Prerequisites
- Section 11 (pgvector running)
- Understanding of embeddings conceptually

### Learning Outcomes
- Build production-grade RAG with chunking, embedding, retrieval, reranking
- Implement hybrid search (vector + keyword BM25)
- Build a PAIOS knowledge ingestion pipeline
- Use LangChain/LlamaIndex for RAG orchestration
- Evaluate RAG quality with RAGAS
- Implement contextual compression and reranking

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| RAG from Scratch | LangChain | Search: "LangChain RAG from scratch 2025" | Canonical RAG tutorial series |
| Advanced RAG Techniques | LlamaIndex | Search: "LlamaIndex advanced RAG 2025" | Production RAG patterns |
| pgvector RAG Tutorial | Supabase | Search: "Supabase pgvector RAG tutorial" | PostgreSQL-native RAG |
| Hybrid Search BM25 + Vector | Various | Search: "hybrid search BM25 pgvector tutorial" | Better retrieval quality |
| RAGAS – RAG Evaluation | Various | Search: "RAGAS evaluation tutorial 2025" | Measure and improve RAG |
| Contextual Retrieval (Anthropic) | Various | Search: "Anthropic contextual retrieval 2025" | State-of-the-art chunking |

### Best YouTube Playlists

| Playlist | Channel | URL |
|----------|---------|-----|
| RAG from Scratch | LangChain | Search: "LangChain RAG from scratch playlist" |
| LlamaIndex Tutorials | LlamaIndex | Search: "LlamaIndex YouTube playlist 2025" |

### Official Sources (NotebookLM-Compatible)
- Anthropic Contextual Retrieval: `https://www.anthropic.com/news/contextual-retrieval`
- LangChain RAG: `https://python.langchain.com/docs/tutorials/rag/`
- LlamaIndex: `https://docs.llamaindex.ai/`
- pgvector: `https://github.com/pgvector/pgvector`
- RAGAS: `https://docs.ragas.io/`

### PAIOS RAG Pipeline
```
Document Input (PDF/MD/URL/YouTube)
        │
        ▼
  Chunking Strategy
  ├── Semantic chunking (preferred)
  ├── Fixed-size with overlap (fallback)
  └── Contextual prefix injection (Anthropic method)
        │
        ▼
  Embedding (Claude/OpenAI/Gemini API)
        │
        ▼
  pgvector Storage
        │
   ┌────▼────┐
   │ Retrieval│
   │ (Hybrid) │
   │Vector+BM25│
   └────┬────┘
        │
  Reranking (Cohere/FlashRank)
        │
        ▼
  Context Assembly → LLM → Response
```

### Mini Projects
1. **Knowledge Ingester** — Pipeline that takes a URL or PDF, chunks it, embeds it, stores in pgvector, and makes it queryable.
2. **Obsidian RAG** — Index entire Obsidian vault into pgvector. Query it from OpenCode via MCP.

### Intermediate Project
> **PAIOS Knowledge Brain** — Full RAG system ingesting from GitHub repos, PDFs, YouTube transcripts, and Obsidian. Hybrid search, reranking, source citation. Used by all PAIOS agents.

---

## SECTION 15 — Browser Automation
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Intermediate | **Study Time:** 1 week

### Prerequisites
- Python async/await comfortable
- Docker (for isolated browser environments)

### Learning Outcomes
- Use Playwright for reliable browser automation
- Build a browser-use agent for web research and form filling
- Implement headless browser sessions in Docker containers
- Connect browser automation to CrewAI as a tool
- Handle anti-bot measures responsibly

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| Playwright Python Complete Guide | Hitesh Choudhary | Search: "Playwright Python tutorial 2025" | Best Playwright Python tutorial |
| browser-use Library Tutorial | Various | Search: "browser-use python AI agent 2025" | AI-native browser automation |
| Web Scraping at Scale | John Watson Rooney | Search: "John Watson Rooney scraping 2025" | Production web data collection |
| Playwright in Docker | Various | Search: "Playwright Docker headless 2025" | Isolated browser environments |

### Official Sources
- Playwright: `https://playwright.dev/python/`
- browser-use: `https://github.com/browser-use/browser-use`
- Playwright Docs: `https://playwright.dev/docs/intro`

### Browser Agent in PAIOS
```python
from browser_use import Agent as BrowserAgent
from playwright.async_api import async_playwright

class PAIOSBrowserTool:
    """Browser automation tool for PAIOS agents"""
    
    async def research_topic(self, query: str) -> str:
        """Open browser, search, extract structured data"""
        async with async_playwright() as p:
            browser = await p.chromium.launch(headless=True)
            agent = BrowserAgent(browser=browser, llm=self.llm)
            result = await agent.run(f"Research: {query}")
            return result
    
    async def fill_form(self, url: str, data: dict) -> bool:
        """Navigate to URL and fill form fields"""
        ...
```

### Mini Project
> **Research Agent with Browser** — CrewAI agent that uses Playwright to visit 5 URLs, extract structured data, synthesize findings, and store in pgvector memory.

---

## SECTION 16 — Computer Use Agents
**Priority:** 🟢 OPTIONAL | **Difficulty:** Advanced | **Study Time:** 2 weeks

### Prerequisites
- Sections 06, 10, 15 complete
- Strong understanding of agent safety and sandboxing

### Learning Outcomes
- Use Anthropic Computer Use API for GUI automation
- Build agents that control Windows/WSL desktop
- Implement safety guardrails for computer use
- Understand when computer use is the right choice (vs. API/browser)

### ⚠️ Important Warning
Computer use agents have direct access to your desktop. **Always run in isolated VMs or containers.** Never give computer use agents access to credentials, banking, or production systems without explicit approval gates.

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| Anthropic Computer Use API Tutorial | Various | Search: "Anthropic computer use API tutorial 2025" | Official capability demo |
| Computer Use Agents – Safety First | Various | Search: "computer use AI agent safety sandboxing" | Don't skip the safety content |
| Desktop Automation with AI | Various | Search: "AI desktop automation Windows 2025" | Windows-specific patterns |
| PyAutoGUI + AI Agents | Various | Search: "PyAutoGUI AI agent automation Python" | Lightweight alternative |

### Official Sources
- Anthropic Computer Use: `https://docs.anthropic.com/en/docs/build-with-claude/computer-use`
- GitHub Reference Implementation: `https://github.com/anthropics/anthropic-quickstarts`

### When to Use Computer Use in PAIOS
```
Use Computer Use ONLY when:
├── No API exists for the target application
├── The task is inherently visual/GUI-based
├── Running in an isolated Docker container
└── Human approval gate is implemented

Prefer alternatives when:
├── An API or MCP server exists → use that
├── Browser automation works → use Playwright
└── Task can be done via CLI → use subprocess/bash
```

---

## SECTION 17 — GitHub & Open Source Contribution
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Intermediate | **Study Time:** Ongoing

### Prerequisites
- Git proficient (branching, rebasing, PRs)
- Understanding of at least one PAIOS component's codebase

### Learning Outcomes
- Navigate open-source contribution workflows (issue → fork → PR → review)
- Set up automated testing and CI for your PAIOS forks
- Use GitHub Actions for PAIOS deployment automation
- Contribute meaningfully to OpenCode, CrewAI, or n8n

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| Contributing to Open Source | Eddie Jaoude | Search: "Eddie Jaoude open source contribution 2025" | Best practical guide |
| GitHub Actions Complete Course | TechWorld with Nana | Search: "TechWorld Nana GitHub Actions complete" | CI/CD automation |
| How to Read a Large Codebase | ThePrimeagen | Search: "ThePrimeagen reading codebase strategy" | Navigate unfamiliar repos |
| Writing Good Issues and PRs | Various | Search: "how to write good GitHub PR open source" | Communication skills |

### Official Sources
- GitHub Docs: `https://docs.github.com/`
- GitHub Actions: `https://docs.github.com/en/actions`
- OpenCode Issues: `https://github.com/opencode-ai/opencode/issues`
- CrewAI Issues: `https://github.com/crewaiinc/crewai/issues`
- n8n Issues: `https://github.com/n8n-io/n8n/issues`

### Contribution Roadmaps

#### OpenCode Contributions
```
Good first contributions:
├── Documentation improvements (opencode.ai/docs)
├── New MCP server examples
├── Windows-specific bug reports/fixes
└── Custom agent template examples

Intermediate:
├── New model provider integration
├── Plugin system improvements
└── TUI enhancement

Advanced:
└── Core agent architecture changes (discuss in issues first)
```

#### CrewAI Contributions
```
Good first:
├── Tool implementations (CrewAI tools library)
├── Documentation and examples
└── Bug reports with reproduction scripts

Intermediate:
├── New memory backend integrations
├── Flow visualization improvements
└── Performance benchmarks

Advanced:
└── Flow architecture changes (open RFC first)
```

#### n8n Contributions
```
Good first:
├── New node implementations
├── Documentation improvements
└── Community workflow templates (n8n.io/workflows)

Intermediate:
├── AI agent node improvements
├── MCP integration enhancements
└── Performance improvements

Advanced:
└── Core execution engine (coordinate with team)
```

---

## SECTION 18 — Advanced System Architecture
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Advanced | **Study Time:** 2 weeks

### Prerequisites
- Sections 06, 08, 11, 14 complete
- Working PAIOS with at least 3 active agents

### Learning Outcomes
- Implement LangGraph for stateful, cyclical agent workflows
- Build A2A (Agent-to-Agent) communication protocols
- Design fault-tolerant agent systems with checkpointing
- Implement agent observability (tracing, logging, cost tracking)
- Build agent evaluation and regression testing frameworks

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| LangGraph Complete Tutorial | LangChain | Search: "LangGraph tutorial 2025 stateful agents" | Stateful agent graphs |
| Multi-Agent Coordination Patterns | Various | Search: "multi-agent coordination patterns 2025" | Architecture deep dives |
| Agent Observability with LangSmith | LangChain | Search: "LangSmith observability agents 2025" | Monitor your PAIOS |
| Building Reliable AI Systems | Various | Search: "reliable AI agent systems production 2025" | Fault tolerance |
| A2A Protocol – Agent Communication | Google/Various | Search: "A2A protocol agent communication 2025" | Cross-framework agent comms |

### Official Sources
- LangGraph: `https://langchain-ai.github.io/langgraph/`
- LangSmith: `https://docs.smith.langchain.com/`
- OpenTelemetry for AI: `https://opentelemetry.io/`
- A2A Protocol: `https://google.github.io/A2A/`

### Advanced PAIOS Architecture Patterns

#### Pattern 1: Hierarchical Agent Network
```
PAIOS Orchestrator (LangGraph Supervisor)
├── Research Division (CrewAI Crew)
│   ├── Web Researcher
│   ├── Document Analyzer
│   └── Knowledge Synthesizer
├── Engineering Division (OpenHands)
│   ├── Code Writer
│   ├── Test Runner
│   └── PR Manager
└── Automation Division (n8n)
    ├── Data Pipeline Manager
    ├── Notification Handler
    └── Integration Coordinator
```

#### Pattern 2: Event-Driven Agent Mesh
```
Event Bus (Redis Pub/Sub)
├── knowledge.ingested → RAG Indexer
├── task.created → Task Router
├── code.committed → Code Reviewer
├── error.occurred → Recovery Agent
└── memory.updated → Memory Consolidator
```

### Intermediate Project
> **Observability Dashboard** — Build a FastAPI + simple HTML dashboard showing: active agents, task queue depth, memory usage, cost per agent per day, and error rates. Pull data from PostgreSQL.

---

## SECTION 19 — Production Deployment
**Priority:** 🟡 RECOMMENDED | **Difficulty:** Advanced | **Study Time:** 2 weeks

### Prerequisites
- All 🔴 MANDATORY sections complete
- Working PAIOS on local machine
- Basic understanding of networking and security

### Learning Outcomes
- Deploy PAIOS behind a reverse proxy (Nginx/Caddy) with HTTPS
- Implement secrets management (no API keys in code/docker-compose)
- Set up automated backups for PostgreSQL
- Configure monitoring and alerting
- Implement rate limiting and cost controls
- Build a deployment pipeline with GitHub Actions

### Best YouTube Videos

| Title | Channel | URL | Why It Matters |
|-------|---------|-----|----------------|
| Self-Hosted AI Stack Production 2025 | Various | Search: "self-hosted AI production deployment 2025" | Full stack production guide |
| Docker Secrets & Security | TechWorld with Nana | Search: "TechWorld Nana Docker secrets security" | Secrets management |
| Nginx Reverse Proxy Complete Guide | NetworkChuck | Search: "NetworkChuck Nginx reverse proxy" | HTTP gateway |
| PostgreSQL Backup Strategies | Hussein Nasser | Search: "Hussein Nasser PostgreSQL backup production" | Data safety |
| Monitoring AI Applications | Various | Search: "AI application monitoring observability 2025" | Know when things break |

### Official Sources
- Nginx: `https://nginx.org/en/docs/`
- Caddy: `https://caddyserver.com/docs/`
- GitHub Actions Secrets: `https://docs.github.com/en/actions/security-guides/encrypted-secrets`

### Production PAIOS Checklist
```
Security:
☐ All secrets in environment variables, never in code
☐ Docker containers run as non-root users
☐ Network segmentation (agents can't reach internet directly)
☐ API keys rotated monthly
☐ Reverse proxy with HTTPS

Reliability:
☐ PostgreSQL daily backups to separate volume
☐ Docker restart policies: always
☐ Health checks on all services
☐ Alerting when agents fail or cost spikes

Observability:
☐ Structured logging (JSON) from all services
☐ Cost tracking per agent per day
☐ Task success/failure rate dashboards
☐ Memory growth monitoring

Performance:
☐ pgvector indexes tuned (ivfflat vs hnsw)
☐ Redis caching for frequent memory queries
☐ Connection pooling for PostgreSQL (pgBouncer)
☐ LiteLLM caching to reduce API costs
```

---

## PROJECT TRACK

### Mini Projects (Sections 01–07)
1. **Environment Bootstrap Script** — Health check all API keys and services
2. **Raw Tool-Calling Agent** — No frameworks, pure Anthropic SDK
3. **OpenCode + 3 MCP Tools** — Filesystem, GitHub, custom Python MCP
4. **Custom MCP Server** — 5 PAIOS-specific tools
5. **Personal Skill Library** — `paios_skills` Python package
6. **Research Crew** — 3-agent CrewAI crew → Obsidian output
7. **Task Queue Agent** — Hermes-style PostgreSQL task manager

### Intermediate Projects (Sections 08–13)
8. **PAIOS Automation Hub** — 10 connected n8n workflows
9. **Auto-PR Bot** — OpenHands → GitHub PR
10. **PAIOS Stack Launch** — Single docker-compose up for all services
11. **Memory-Backed Agent** — PostgreSQL-backed CrewAI agent
12. **Obsidian MCP Server** — Full vault operations via MCP
13. **Research Agent with Browser** — Playwright + CrewAI

### Capstone Projects

#### Capstone A — PAIOS MVP (Weeks 10–12)
> **Personal AI Assistant** that:
> - Accepts tasks via OpenCode terminal or n8n webhook
> - Routes to appropriate CrewAI crew
> - Stores all knowledge in pgvector memory
> - Surfaces relevant context from past work automatically
> - Pushes code changes via OpenHands + GitHub
> - Syncs knowledge to Obsidian vault

#### Capstone B — PAIOS Knowledge Engine (Weeks 14–16)
> **Full RAG + Memory System** that:
> - Ingests from GitHub repos, PDFs, URLs, YouTube transcripts
> - Hybrid search (vector + BM25) with reranking
> - Agents auto-recall relevant context before each task
> - Daily knowledge synthesis report in Notion
> - Obsidian vault stays synchronized

#### Capstone C — Production PAIOS (Weeks 20–24)
> **Fully production-grade PAIOS** with:
> - All services dockerized and orchestrated
> - GitHub Actions CI/CD pipeline
> - Observability dashboard with cost tracking
> - Contribution-ready fork of OpenCode or CrewAI
> - Documented architecture for others to replicate

---

## FINAL PRODUCTION-GRADE SYSTEM BLUEPRINT

```
┌──────────────────────────────────────────────────────────────────────┐
│                    PAIOS Production Blueprint                          │
│                    Windows + WSL2 + Docker                            │
├──────────────────────────────────────────────────────────────────────┤
│                                                                        │
│  INTERFACE LAYER                                                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐               │
│  │  OpenCode    │  │   n8n UI     │  │  PAIOS API   │               │
│  │  Terminal    │  │ :5678        │  │  :8000       │               │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘               │
│         │                 │                  │                        │
│         └─────────────────┴──────────────────┘                       │
│                           │                                           │
│  ORCHESTRATION LAYER      ▼                                           │
│  ┌────────────────────────────────────────────────────────────────┐  │
│  │  CrewAI Flows (event-driven multi-agent)                        │  │
│  │  ┌────────────┐  ┌────────────┐  ┌────────────┐               │  │
│  │  │ Research   │  │Engineering │  │Automation  │               │  │
│  │  │   Crew     │  │   Crew     │  │   Crew     │               │  │
│  │  └────────────┘  └────────────┘  └────────────┘               │  │
│  └────────────────────────────────────────────────────────────────┘  │
│                           │                                           │
│  TOOL LAYER               ▼                                           │
│  ┌────────────────────────────────────────────────────────────────┐  │
│  │  MCP Server Hub                                                 │  │
│  │  filesystem │ github │ postgres │ brave-search │ custom-paios  │  │
│  └────────────────────────────────────────────────────────────────┘  │
│                           │                                           │
│  EXECUTION LAYER          ▼                                           │
│  ┌────────────────────────────────────────────────────────────────┐  │
│  │  OpenHands (Docker sandbox)  │  Playwright (browser)           │  │
│  └────────────────────────────────────────────────────────────────┘  │
│                           │                                           │
│  DATA LAYER               ▼                                           │
│  ┌────────────────────────────────────────────────────────────────┐  │
│  │  PostgreSQL + pgvector  │  Redis  │  Obsidian Vault             │  │
│  │  ├── episodic_memory    │  Cache  │  ├── 00-Inbox               │  │
│  │  ├── semantic_memory    │         │  ├── 01-Projects            │  │
│  │  └── task_registry      │         │  └── 02-Knowledge           │  │
│  └────────────────────────────────────────────────────────────────┘  │
│                           │                                           │
│  MODEL LAYER              ▼                                           │
│  ┌────────────────────────────────────────────────────────────────┐  │
│  │  LiteLLM Gateway (unified model access)                         │  │
│  │  Claude API │ Gemini API │ GPT API │ OpenRouter (fallback)      │  │
│  └────────────────────────────────────────────────────────────────┘  │
│                                                                        │
│  DEVOPS LAYER                                                          │
│  ┌────────────────────────────────────────────────────────────────┐  │
│  │  GitHub Actions CI/CD  │  Docker Compose  │  Nginx + HTTPS     │  │
│  └────────────────────────────────────────────────────────────────┘  │
└──────────────────────────────────────────────────────────────────────┘
```

---

## COMPONENT INTERACTION DIAGRAM

```
User → OpenCode → MCP Layer
                     ├──→ Simple tool call → Result → User
                     └──→ Complex task → CrewAI Flow
                                              │
                              ┌───────────────┼───────────────┐
                              ▼               ▼               ▼
                         Research        Engineering     Automation
                          Crew            Crew            Crew
                              │               │               │
                    Brave Search API   OpenHands        n8n Workflow
                         + pgvector     Sandbox        Execution
                              │               │               │
                              └───────────────┴───────────────┘
                                              │
                                         PostgreSQL
                                         (all results
                                         + embeddings
                                         stored here)
                                              │
                              ┌───────────────┴───────────────┐
                              ▼                               ▼
                         Obsidian Vault               Notion Database
                         (local knowledge)            (team/shared)
```

---

## DEPLOYMENT BLUEPRINT

```
Windows Machine
├── WSL2 (Ubuntu 22.04)
│   ├── Python 3.12 + uv package manager
│   ├── Node.js 20 (for MCP servers)
│   ├── Go (for OpenCode CLI builds)
│   └── OpenCode binary
│
├── Docker Desktop
│   └── docker-compose up (PAIOS stack)
│       ├── postgres:16 + pgvector extension
│       ├── redis:7
│       ├── n8n:latest
│       ├── openhands:latest
│       ├── paios-api (custom FastAPI)
│       └── nginx (reverse proxy)
│
├── VS Code + WSL2 extension
│   └── OpenCode VS Code extension (if available)
│
├── Obsidian (Windows native)
│   └── Vault watched by n8n file watcher
│
└── Environment Variables (.env)
    ├── ANTHROPIC_API_KEY
    ├── GEMINI_API_KEY (backup)
    ├── OPENROUTER_API_KEY (fallback)
    ├── GITHUB_TOKEN
    ├── POSTGRES_PASSWORD
    └── N8N_ENCRYPTION_KEY
```

---

## STUDY MATERIALS REFERENCE TABLE

### NotebookLM-Compatible Source URLs

| Component | Source URL |
|-----------|-----------|
| OpenCode | `https://opencode.ai/` |
| OpenCode GitHub | `https://github.com/opencode-ai/opencode` |
| MCP Spec | `https://modelcontextprotocol.io/` |
| MCP Servers | `https://github.com/modelcontextprotocol/servers` |
| CrewAI Docs | `https://docs.crewai.com/` |
| CrewAI GitHub | `https://github.com/crewaiinc/crewai` |
| n8n Docs | `https://docs.n8n.io/` |
| n8n GitHub | `https://github.com/n8n-io/n8n` |
| OpenHands Docs | `https://docs.all-hands.dev/` |
| OpenHands SDK | `https://docs.openhands.dev/sdk` |
| OpenHands GitHub | `https://github.com/All-Hands-AI/OpenHands` |
| pgvector | `https://github.com/pgvector/pgvector` |
| LangGraph | `https://langchain-ai.github.io/langgraph/` |
| LiteLLM | `https://docs.litellm.ai/` |
| Playwright Python | `https://playwright.dev/python/` |
| browser-use | `https://github.com/browser-use/browser-use` |
| Anthropic Computer Use | `https://docs.anthropic.com/en/docs/build-with-claude/computer-use` |
| FastAPI | `https://fastapi.tiangolo.com/` |
| Docker Compose | `https://docs.docker.com/compose/` |
| GitHub Actions | `https://docs.github.com/en/actions` |
| Obsidian Docs | `https://help.obsidian.md/` |
| Notion API | `https://developers.notion.com/` |
| RAGAS | `https://docs.ragas.io/` |
| LlamaIndex | `https://docs.llamaindex.ai/` |
| CrewAI Memory | `https://docs.crewai.com/en/concepts/memory` |
| Anthropic RAG | `https://www.anthropic.com/news/contextual-retrieval` |

### Key YouTube Channels (All NotebookLM-Compatible)

| Channel | Focus | URL |
|---------|-------|-----|
| CrewAI Official | Multi-agent, CrewAI | `https://www.youtube.com/@crewAIInc` |
| n8n Official | Workflow automation | `https://www.youtube.com/c/n8n-io` |
| LangChain | RAG, agents, LangGraph | Search: LangChain YouTube |
| TechWorld with Nana | Docker, DevOps, K8s | Search: TechWorld Nana |
| NetworkChuck | Networking, WSL2, Linux | Search: NetworkChuck |
| Fireship | Quick concept explainers | Search: Fireship |
| Sam Witteveen | AI agents, LLMs | Search: Sam Witteveen |
| IndyDevDan | MCP, agent tools | Search: IndyDevDan |
| ArjanCodes | Python architecture | Search: ArjanCodes |
| AI Jason | Agent patterns | Search: AI Jason |
| Supabase | pgvector, databases | Search: Supabase YouTube |
| DeepLearning.AI | Courses, fundamentals | `https://www.youtube.com/@Deeplearningai` |

---

## WEEKLY LEARNING CALENDAR

### Phase 1: Foundation (Weeks 1–4)
```
Week 1: WSL2, Python toolchain, Docker, Git, API keys
Week 2: AI agent fundamentals, first tool-calling agent (no frameworks)
Week 3: OpenCode install + config, first MCP server connection
Week 4: Build PAIOS MCP hub, personal skill library
```
**Milestone:** OpenCode running with 5 MCP tools. Can write, store, and retrieve from pgvector.

### Phase 2: Orchestration (Weeks 5–9)
```
Week 5: PostgreSQL + pgvector schema, memory manager class
Week 6: CrewAI basics - first 2-agent crew
Week 7: CrewAI Flows + MCP integration
Week 8: n8n setup, first 3 automation workflows
Week 9: n8n + CrewAI integration (n8n triggers crew)
```
**Milestone:** End-to-end task flow: OpenCode prompt → CrewAI crew → result stored in PostgreSQL → n8n sends notification.

### Phase 3: Knowledge (Weeks 10–13)
```
Week 10: RAG pipeline (chunking, embedding, retrieval)
Week 11: Hybrid search + reranking, RAGAS evaluation
Week 12: Obsidian vault structure + MCP server
Week 13: Full knowledge brain (RAG from all sources)
```
**Milestone:** PAIOS can ingest any document and answer questions about it with source citations.

### Phase 4: Automation (Weeks 14–17)
```
Week 14: OpenHands setup + GitHub integration
Week 15: Auto-PR workflow (OpenHands + n8n + GitHub)
Week 16: Playwright browser automation + CrewAI tool
Week 17: Full PAIOS stack in Docker Compose
```
**Milestone:** Give PAIOS a GitHub issue. It researches, codes, tests, and opens a PR autonomously.

### Phase 5: Production (Weeks 18–24)
```
Week 18: Observability (logging, cost tracking, alerting)
Week 19: Security hardening, secrets management
Week 20: Performance tuning (caching, indexing, connection pooling)
Week 21: GitHub Actions CI/CD pipeline
Week 22-24: Open source contribution to chosen project
```
**Milestone:** PAIOS running in production. Contributing to upstream open-source projects.

---

*Generated: 2026-06 | Maintained by: You | Next review: Add new tools as ecosystem evolves*
*All URLs verified as of June 2026. Recheck quarterly — this ecosystem moves fast.*
