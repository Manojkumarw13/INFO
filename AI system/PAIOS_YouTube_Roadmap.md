# PAIOS — YouTube-Only Learning Roadmap
### Windows · API Models · OpenCode as Central Interface
> **How to use this roadmap:** Every resource is a real channel/creator. Search the exact title on YouTube to find it.  
> URL format: `https://www.youtube.com/@ChannelHandle` links are verified channel pages.  
> Video URLs are search-verified — use exact titles where URLs aren't confirmed.  
> ⚠️ **Priority system:** 🔴 Mandatory · 🟡 Recommended · 🟢 Optional

---

## HOW THE ECOSYSTEM FITS TOGETHER

```
┌─────────────────────────────────────────────────────────────────────┐
│                    PAIOS — Learning Map                               │
│                                                                       │
│  LAYER 1 — Foundation (Weeks 1–2)                                    │
│  WSL2 → Python → Docker → Git → VS Code                              │
│                    ↓                                                  │
│  LAYER 2 — Agent Brain (Weeks 3–4)                                   │
│  AI Agent Fundamentals → MCP Servers → Skills/Tools                  │
│                    ↓                                                  │
│  LAYER 3 — Central Interface (Week 4)                                │
│  OpenCode ← connects everything via MCP                              │
│                    ↓                                                  │
│  LAYER 4 — Orchestration (Weeks 5–6)                                 │
│  CrewAI → Hermes → n8n → OpenHands                                   │
│                    ↓                                                  │
│  LAYER 5 — Knowledge & Memory (Weeks 7–8)                            │
│  PostgreSQL+pgvector → RAG → Obsidian → Notion                       │
│                    ↓                                                  │
│  LAYER 6 — Extended Capabilities (Weeks 9–10)                        │
│  Browser Automation → Computer Use Agents                             │
│                    ↓                                                  │
│  LAYER 7 — Production (Weeks 11–12)                                  │
│  GitHub/OSS → Advanced Architecture → Deployment                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## SYSTEM ARCHITECTURE DIAGRAM

```
┌───────────────────────────────────────────────────────────────────────────┐
│                         PAIOS Production System                            │
│                                                                             │
│  ENTRY POINTS                                                               │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                    │
│  │  OpenCode    │  │  n8n Webhook │  │  PAIOS API   │                    │
│  │  (Terminal)  │  │  Triggers    │  │  :8000       │                    │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘                    │
│         └─────────────────┴──────────────────┘                             │
│                           │                                                 │
│            ┌──────────────▼──────────────┐                                │
│            │    Hermes Task Router        │                                │
│            │  (classify → prioritize →    │                                │
│            │   assign → track)            │                                │
│            └──────────────┬──────────────┘                                │
│                           │                                                 │
│     ┌─────────────────────┼─────────────────────┐                         │
│     ▼                     ▼                     ▼                          │
│ ┌───────┐           ┌───────────┐         ┌──────────┐                    │
│ │CrewAI │           │ OpenHands │         │  n8n     │                    │
│ │Crews  │           │ (Coding   │         │ (Workflow│                    │
│ │       │           │  Sandbox) │         │  Engine) │                    │
│ └───┬───┘           └─────┬─────┘         └────┬─────┘                    │
│     └──────────┬──────────┘                    │                           │
│                ▼                               │                           │
│     ┌──────────────────┐                       │                           │
│     │   MCP Layer      │◄──────────────────────┘                          │
│     │  paios-core MCP  │                                                   │
│     │  github MCP      │                                                   │
│     │  postgres MCP    │                                                   │
│     │  obsidian MCP    │                                                   │
│     └────────┬─────────┘                                                   │
│              │                                                              │
│     ┌────────▼─────────┐    ┌────────────┐    ┌──────────┐               │
│     │  PostgreSQL       │    │  Obsidian  │    │  GitHub  │               │
│     │  + pgvector       │    │  Vault     │    │  API     │               │
│     │  (Memory + RAG)   │    │            │    │          │               │
│     └──────────────────┘    └────────────┘    └──────────┘               │
│                                                                             │
│     MODEL GATEWAY: LiteLLM → Claude / Gemini / GPT / OpenRouter           │
└───────────────────────────────────────────────────────────────────────────┘
```

---

## DATA FLOW DIAGRAM

```
User Types Task in OpenCode
          │
          ▼
OpenCode parses intent
          │
    ┌─────┴──────┐
    │            │
Simple       Complex
tool call    multi-step
    │            │
    ▼            ▼
MCP Server   Hermes API
(direct)    /classify
    │            │
    │     ┌──────┴───────┐
    │     │ Route to:    │
    │     ├─ Research    │
    │     ├─ Engineering │
    │     ├─ Content     │
    │     └─ Analysis    │
    │            │
    │         CrewAI
    │         Crew runs
    │            │
    │         Results →
    └────────────┘
         │
   PostgreSQL
   (store + embed)
         │
    Obsidian note
    created by n8n
```

---

## DEPLOYMENT BLUEPRINT

```
Windows 11
├── WSL2 (Ubuntu 22.04)
│   ├── Python 3.12 + uv
│   ├── Node.js 20 (MCP servers)
│   └── OpenCode binary
│
├── Docker Desktop
│   └── docker-compose.yml
│       ├── postgres:16-pgvector  :5432
│       ├── redis:7-alpine        :6379
│       ├── n8n:latest            :5678
│       ├── openhands:latest      :3000
│       ├── paios-api             :8000
│       └── nginx                 :80/:443
│
├── VS Code + WSL Remote Extension
├── Obsidian (Windows native)
│
└── .env
    ├── ANTHROPIC_API_KEY
    ├── GEMINI_API_KEY
    ├── GITHUB_TOKEN
    ├── POSTGRES_PASSWORD
    └── N8N_ENCRYPTION_KEY
```

---

# SECTION 01 — FOUNDATION
**Priority:** 🔴 Mandatory | **Difficulty:** Beginner | **Study Time:** 1–2 weeks  
**Prerequisites:** None

### Learning Outcomes
- WSL2 running Ubuntu on Windows with full dev toolchain
- Python 3.12 with virtual environments and package management (uv/pip)
- Docker Desktop installed, first container running
- Git workflow: branches, commits, PRs, `.gitignore`, `.env` hygiene
- VS Code configured with WSL Remote, Python, and Docker extensions

### Milestone
`docker run hello-world` succeeds. Python script runs in WSL2. Git repo pushed to GitHub. All API keys stored in `.env`, never in code.

---

#### VIDEO 01 — WSL2 Complete Setup for AI Development
- **Title to search:** "you need to learn WSL RIGHT NOW!!"
- **Channel:** NetworkChuck
- **Channel URL:** `https://www.youtube.com/@NetworkChuck`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** NetworkChuck is the most-watched practical networking/Linux channel. This WSL2 video is consistently cited as the definitive Windows-to-Linux bridge tutorial. Covers installation, file system navigation, and running Linux tools on Windows — exactly what PAIOS requires.

#### VIDEO 02 — Python Virtual Environments Explained
- **Title to search:** "Python Virtual Environments Tutorial using 'venv'"
- **Channel:** Corey Schafer
- **Channel URL:** `https://www.youtube.com/@coreyms`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Corey Schafer is the gold standard for Python tutorials. Every PAIOS project uses isolated Python environments. Understanding venv is non-negotiable before writing any agent code.

#### VIDEO 03 — Git and GitHub Full Course
- **Title to search:** "Git and GitHub for Beginners – Crash Course"
- **Channel:** freeCodeCamp.org
- **Channel URL:** `https://www.youtube.com/@freecodecamp`
- **URL:** `https://www.youtube.com/watch?v=RGOj5yH7evk`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** freeCodeCamp's crash courses are the most-watched beginner content. Six weeks of daily commits to PAIOS requires solid Git fundamentals. This 1-hour course covers everything needed.

#### VIDEO 04 — Docker Tutorial for Beginners (Full Course)
- **Title to search:** "Docker Tutorial for Beginners [FULL COURSE in 3 Hours]"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Nana Janashia (Docker Captain, AWS Container Hero) runs the highest-quality DevOps education channel. PAIOS runs entirely in Docker. This is the definitive 3-hour Docker foundation course — widely referenced across the dev community.

#### VIDEO 05 — Docker Compose Tutorial
- **Title to search:** "Docker Compose Tutorial – Run Multi-Container Applications"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** PAIOS uses Docker Compose to orchestrate 6+ services. This is the natural follow-on to the Docker basics video, from the same trusted channel. Covers the exact patterns used in the PAIOS `docker-compose.yml`.

#### VIDEO 06 — VS Code + WSL2 Setup
- **Title to search:** "VS Code WSL Tutorial – Remote development in WSL"
- **Channel:** Visual Studio Code (Official)
- **Channel URL:** `https://www.youtube.com/@code`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Official Microsoft VS Code channel. VS Code is the development environment for PAIOS and the integration between VS Code and WSL2 is a critical workflow detail not well-covered by third parties.

#### VIDEO 07 — Environment Variables and dotenv in Python
- **Title to search:** "Python Tutorial: Hiding Sensitive Data with Environment Variables"
- **Channel:** Corey Schafer
- **Channel URL:** `https://www.youtube.com/@coreyms`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Every PAIOS component reads secrets from `.env` files. API key exposure is the #1 beginner security mistake. This video establishes correct habits before touching any API.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Docker Tutorials for Beginners | NetworkChuck | `https://www.youtube.com/playlist?list=PLIhvC56v63IJlnU4k60d0oFIrsbXEivQo` | Practical Docker from networking perspective |
| Python Tutorials | Corey Schafer | `https://www.youtube.com/@coreyms/playlists` | Best Python fundamentals on YouTube |
| DevOps Bootcamp | TechWorld with Nana | `https://www.youtube.com/c/TechWorldwithNana/playlists` | Full DevOps context for PAIOS infrastructure |

---

# SECTION 02 — AI AGENT FUNDAMENTALS
**Priority:** 🔴 Mandatory | **Difficulty:** Beginner → Intermediate | **Study Time:** 1 week  
**Prerequisites:** Section 01 complete, basic Python async understanding

### Learning Outcomes
- Understand ReAct, Plan-and-Execute, and tool-use agent patterns
- Build a tool-calling agent using the Anthropic SDK directly (no frameworks)
- Understand context windows, token costs, and when NOT to use agents
- Know the difference between: LLM call / chain / agent / multi-agent

### Milestone
Build a working 3-tool agent using raw API calls: `web_search`, `read_file`, `write_file`. No LangChain, no CrewAI — understand what frameworks abstract away.

---

#### VIDEO 01 — Intro to Large Language Models
- **Title to search:** "Intro to Large Language Models"
- **Channel:** Andrej Karpathy
- **Channel URL:** `https://www.youtube.com/@AndrejKarpathy`
- **URL:** `https://www.youtube.com/watch?v=zjkBMFhNj_g`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Karpathy is the most credible AI educator alive. This 1-hour foundation lecture explains what LLMs are, how they work, and their limitations — directly informing every architectural decision in PAIOS. Mandatory before touching agents.

#### VIDEO 02 — Building AI Agents from Scratch (No Frameworks)
- **Title to search:** "Building AI Agents from Scratch – No LangChain"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Sam Witteveen (Google Developer Expert for ML) is one of the most technically rigorous AI agent educators. Building without frameworks first reveals what agents actually do — critical before adding CrewAI on top.

#### VIDEO 03 — AI Agents Explained: ReAct Pattern
- **Title to search:** "ReAct: Synergizing Reasoning and Acting in LLMs"
- **Channel:** AI Jason
- **Channel URL:** `https://www.youtube.com/@AIJasonZ`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** AI Jason produces focused, technically accurate agent content. ReAct is the foundational pattern behind every CrewAI, LangGraph, and OpenHands agent. Understanding it prevents debugging confusion later.

#### VIDEO 04 — Function Calling / Tool Use Deep Dive
- **Title to search:** "Function Calling with OpenAI API – Full Tutorial"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** MCP, CrewAI tools, and OpenHands all build on function calling. This is the mechanical foundation. Sam's depth on the API behavior is superior to most tutorials.

#### VIDEO 05 — Agentic AI Patterns: When to Use What
- **Title to search:** "Building Effective AI Agents – Key Patterns"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Cole Medin is ranked as the top AI agent educator for code-writing engineers in 2026. This architectural overview prevents over-engineering — one of the most expensive mistakes in agent development.

#### VIDEO 06 — LangGraph: Stateful Agent Workflows
- **Title to search:** "LangGraph Tutorial – Build Stateful AI Agents"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** LangGraph is used in PAIOS for complex multi-step supervisor workflows. Understanding state machines is essential for Week 6 advanced architecture. Official channel ensures accuracy.

#### VIDEO 07 — LiteLLM: Unified Model Gateway
- **Title to search:** "LiteLLM Tutorial – Call 100+ LLMs with One API"
- **Channel:** Mervin Praison (PraisonAI)
- **Channel URL:** `https://www.youtube.com/@MervinPraison`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS uses LiteLLM to abstract provider switching (Claude → Gemini → GPT). Mervin Praison covers LiteLLM practically and has strong AI tools coverage.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| AI Agents Masterclass | Cole Medin | `https://www.youtube.com/@ColeMedin/playlists` | Best end-to-end agents series for code-first developers |
| AI Agents Series | Sam Witteveen | `https://www.youtube.com/@samwitteveenai/playlists` | Deep technical agent content from Google ML Expert |

---

# SECTION 03 — OPENCODE ECOSYSTEM
**Priority:** 🔴 Mandatory | **Difficulty:** Beginner | **Study Time:** 3–5 days  
**Prerequisites:** Sections 01–02, API key for Claude or Gemini

### Learning Outcomes
- OpenCode installed and running on Windows/WSL2
- Custom agent definitions configured (Plan, Build, Review, Document, Debug)
- Provider fallback chain configured (Claude → Gemini → OpenRouter)
- MCP servers connected via `opencode.json`
- Non-interactive scripting mode working (`opencode -p "prompt"`)
- Understand how OpenCode is the unified interface for all PAIOS operations

### Milestone
5 specialized OpenCode agents accessible via Tab key. All 4 MCP connections active. Non-interactive mode completes a 3-step task.

---

#### VIDEO 01 — OpenCode Introduction and Setup
- **Title to search:** "OpenCode – The Open Source AI Coding Agent"
- **Channel:** Fireship
- **Channel URL:** `https://www.youtube.com/@Fireship`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Fireship produces the most-watched tech explainer content. Their concise format is ideal for understanding what OpenCode is and how it fits the AI coding agent landscape before deep diving into configuration.

#### VIDEO 02 — OpenCode Full Setup and Configuration
- **Title to search:** "OpenCode Full Tutorial – Setup, Agents, MCP"
- **Channel:** Theo (t3.gg)
- **Channel URL:** `https://www.youtube.com/@t3dotgg`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Theo (t3.gg) is closely connected to the SST/OpenCode ecosystem and publishes practical developer setup content. His setup videos are known for covering real configuration details that official docs miss.

#### VIDEO 03 — AI Coding Agents Compared (OpenCode vs Alternatives)
- **Title to search:** "AI Coding Agent Comparison – Claude Code, Cursor, OpenCode 2025"
- **Channel:** Fireship
- **Channel URL:** `https://www.youtube.com/@Fireship`
- **Difficulty:** Beginner
- **Priority:** 🟡 Recommended
- **Why selected:** Understanding why OpenCode is chosen over alternatives (and its trade-offs) informs configuration decisions. Fireship's landscape videos are widely cited as unbiased.

#### VIDEO 04 — Terminal AI Agents Deep Dive
- **Title to search:** "Build Anything with AI Agents in Your Terminal"
- **Channel:** IndyDevDan
- **Channel URL:** `https://www.youtube.com/@IndyDevDan`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** IndyDevDan is the leading YouTube educator specifically for MCP servers and terminal-based AI agent tools. His content is directly applicable to OpenCode + MCP workflows.

#### VIDEO 05 — Custom AI Agent Configuration Patterns
- **Title to search:** "Custom AI Agents – How to Configure for Your Workflow"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Cole Medin's focus on practical agent configuration maps directly to setting up PAIOS-specific OpenCode agents with correct tool access and role definitions.

#### VIDEO 06 — AI Coding Agents in Production
- **Title to search:** "AI Coding Agents in Production – What Actually Works"
- **Channel:** ThePrimeagen
- **Channel URL:** `https://www.youtube.com/@ThePrimeagen`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** ThePrimeagen provides direct, opinionated takes on developer tooling from a senior engineering perspective. His analysis of what works vs. what's hype is valuable before committing to OpenCode as a daily driver.

#### VIDEO 07 — VS Code Integration with AI Coding Tools
- **Title to search:** "VS Code AI Extensions – Complete Setup Guide"
- **Channel:** Visual Studio Code (Official)
- **Channel URL:** `https://www.youtube.com/@code`
- **Difficulty:** Beginner
- **Priority:** 🟡 Recommended
- **Why selected:** VS Code remains the supporting editor for PAIOS development. Official channel content ensures accurate extension configuration.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| AI Coding Tools & Agents | Fireship | `https://www.youtube.com/@Fireship` | Best short-form AI tool comparisons |
| AI Engineering Daily | IndyDevDan | `https://www.youtube.com/@IndyDevDan` | MCP + terminal agent focus |

---

# SECTION 04 — MCP SERVERS
**Priority:** 🔴 Mandatory | **Difficulty:** Intermediate | **Study Time:** 1–2 weeks  
**Prerequisites:** Sections 01–03, Node.js 20 installed

### Learning Outcomes
- Understand MCP host/client/server architecture and the N×M problem it solves
- Use all 8 essential official MCP servers (filesystem, postgres, github, git, brave, fetch, memory, sequential-thinking)
- Build a custom Python MCP server using FastMCP
- Connect MCP servers to OpenCode, CrewAI, and n8n
- Publish a custom MCP server

### Milestone
Custom Python MCP server with 5 tools running and connected to OpenCode. All official servers configured in `opencode.json`.

---

#### VIDEO 01 — MCP Explained: The New Standard
- **Title to search:** "Model Context Protocol (MCP) Explained"
- **Channel:** Fireship
- **Channel URL:** `https://www.youtube.com/@Fireship`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Fireship's MCP explainer is among the most-watched introductions. Covers the N×M problem, architecture, and why this matters — essential context before building servers.

#### VIDEO 02 — Build Your First MCP Server (Python)
- **Title to search:** "Build Your First MCP Server in Python – Complete Guide"
- **Channel:** IndyDevDan
- **Channel URL:** `https://www.youtube.com/@IndyDevDan`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** IndyDevDan is the most focused MCP educator on YouTube. Python-first approach matches PAIOS stack. This video is the go-to for hands-on MCP server construction.

#### VIDEO 03 — MCP Architecture Deep Dive
- **Title to search:** "MCP Deep Dive – Hosts, Clients, Servers Explained"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Sam Witteveen's architectural breakdown of MCP is the most technically precise on YouTube. Understanding the protocol internals prevents misconfiguration errors when connecting to OpenCode.

#### VIDEO 04 — Docker MCP Servers Tutorial
- **Title to search:** "Docker MCP Servers – Build and Deploy with Docker"
- **Channel:** NetworkChuck
- **Channel URL:** `https://www.youtube.com/@NetworkChuck`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** NetworkChuck published a Docker+MCP tutorial with a companion GitHub repo (`theNetworkChuck/docker-mcp-tutorial`). PAIOS runs MCP servers in Docker. This is the only major YouTube video covering this exact combination.

#### VIDEO 05 — MCP Servers with CrewAI Integration
- **Title to search:** "MCP Servers with CrewAI – Connect Tools to Multi-Agent Systems"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Critical integration video. CrewAI's MCPServerAdapter is the bridge between PAIOS MCP hub and CrewAI crews. Sam covers this integration with the technical precision it requires.

#### VIDEO 06 — FastMCP: Build MCP Servers Fast
- **Title to search:** "FastMCP Tutorial – Build MCP Servers Faster with Python"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** FastMCP is the Python library used to build PAIOS custom MCP servers. Cole's tutorial covers the decorator-based API that reduces server development time significantly.

#### VIDEO 07 — MCP Registry and Discovery
- **Title to search:** "MCP Servers Registry – Find and Install Tools for AI Agents"
- **Channel:** IndyDevDan
- **Channel URL:** `https://www.youtube.com/@IndyDevDan`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Understanding available MCP servers accelerates PAIOS development by avoiding rebuilding what already exists. IndyDevDan covers the ecosystem comprehensively.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| MCP Server Tutorials | IndyDevDan | `https://www.youtube.com/@IndyDevDan/playlists` | Most comprehensive MCP playlist on YouTube |
| AI Tools & MCP | Sam Witteveen | `https://www.youtube.com/@samwitteveenai/playlists` | Technically deep MCP content |

---

# SECTION 05 — SKILLS, TOOLS & PLUGINS
**Priority:** 🟡 Recommended | **Difficulty:** Intermediate | **Study Time:** 1 week  
**Prerequisites:** Sections 02–04

### Learning Outcomes
- Understand the hierarchy: MCP tools vs. CrewAI tools vs. agent skills
- Build reusable, framework-agnostic Python tool functions
- Package tools as a pip-installable library
- Use FastAPI to expose tools as HTTP endpoints (for n8n integration)

### Milestone
A `paios-skills` Python package with 10 tested tools, installable via pip.

---

#### VIDEO 01 — Building Custom AI Tools in Python
- **Title to search:** "Build Custom Tools for AI Agents – Python Tutorial"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Cole covers the practical patterns for building reusable agent tools that work across frameworks.

#### VIDEO 02 — FastAPI for AI Applications
- **Title to search:** "FastAPI Tutorial – Build APIs for AI Applications"
- **Channel:** ArjanCodes
- **Channel URL:** `https://www.youtube.com/@ArjanCodes`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** ArjanCodes is the highest-quality Python architecture channel. PAIOS exposes tools via FastAPI. Arjan's focus on clean Python architecture prevents spaghetti code in the API layer.

#### VIDEO 03 — Packaging Python Libraries for PyPI
- **Title to search:** "How to Create and Publish a Python Package to PyPI"
- **Channel:** Corey Schafer
- **Channel URL:** `https://www.youtube.com/@coreyms`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Publishing `paios-skills` to PyPI turns a personal tool into a portfolio asset. Corey Schafer's packaging guide is the most cited Python packaging tutorial.

#### VIDEO 04 — Playwright Python Tutorial
- **Title to search:** "Playwright Python Tutorial – Web Automation and Scraping"
- **Channel:** Hitesh Choudhary
- **Channel URL:** `https://www.youtube.com/@HiteshCodeLab`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Playwright is used in PAIOS browser automation tools. Hitesh Choudhary covers Playwright Python with practical web automation examples.

#### VIDEO 05 — Web Scraping at Scale with Python
- **Title to search:** "Python Web Scraping Full Course – Beautiful Soup + Requests"
- **Channel:** John Watson Rooney
- **Channel URL:** `https://www.youtube.com/@JohnWatsonRooney`
- **Difficulty:** Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** Web scraping is a core agent skill used across research, monitoring, and data extraction tools in PAIOS. John Watson Rooney is the most trusted web scraping educator on YouTube.

#### VIDEO 06 — Redis for Python Developers
- **Title to search:** "Redis Python Tutorial – Caching, Queues, and Pub/Sub"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Redis is used in PAIOS for task queues and caching. Nana's Redis tutorial covers the patterns used in the PAIOS automation layer.

#### VIDEO 07 — Building Reusable Agent Tool Patterns
- **Title to search:** "Agent Tool Design Patterns – Best Practices"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** LangChain's official channel covers tool design patterns that inform how paios-skills is architected for cross-framework compatibility.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Python Projects | Corey Schafer | `https://www.youtube.com/@coreyms/playlists` | Best Python architecture patterns |
| FastAPI Tutorials | ArjanCodes | `https://www.youtube.com/@ArjanCodes/playlists` | Clean Python API design |

---

# SECTION 06 — CREWAI & MULTI-AGENT SYSTEMS
**Priority:** 🔴 Mandatory | **Difficulty:** Intermediate | **Study Time:** 2 weeks  
**Prerequisites:** Sections 02, 05 complete, comfortable with Python classes

### Learning Outcomes
- Build multi-agent Crews with defined roles, goals, and tool access
- Use CrewAI Flows for event-driven, stateful orchestration
- Implement all four memory types (short-term, long-term, entity, contextual)
- Connect CrewAI agents to MCP servers via MCPServerAdapter
- Build and deploy production Flows with checkpointing
- Understand Agent-to-Agent (A2A) protocol basics

### Milestone
Four production crews (Research, Engineering, Content, Analysis) routing via a PAIOSFlow. End-to-end test: natural language task → correct crew → result stored.

---

#### VIDEO 01 — CrewAI Complete Crash Course
- **Title to search:** "CrewAI Tutorial: Complete Crash Course for Beginners"
- **Channel:** Brandon Hancock
- **Channel URL:** Search: "Brandon Hancock AI YouTube"
- **URL:** `https://www.youtube.com/watch?v=sPzc6hMg7So`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** One of the most-watched CrewAI tutorials. Brandon Hancock covers agents, tasks, crews, and tools from zero — the mandatory starting point before advanced content.

#### VIDEO 02 — Build a Multi-Agent System with CrewAI
- **Title to search:** "Build a Multi-Agent System with CrewAI | Agentic AI Tutorial"
- **Channel:** Siddhardhan
- **Channel URL:** `https://www.youtube.com/@Siddhardhan`
- **URL:** `https://www.youtube.com/watch?v=qsrl2DHYi1Y`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Production-oriented CrewAI tutorial with real use cases. Siddhardhan covers complete ML/AI projects end-to-end. This video is particularly strong on multi-agent coordination patterns.

#### VIDEO 03 — CrewAI Flows: Enterprise Architecture
- **Title to search:** "CrewAI Flows Tutorial – Build Event-Driven Agent Workflows"
- **Channel:** CrewAI (Official)
- **Channel URL:** `https://www.youtube.com/@crewAIInc`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Official maintainer channel. CrewAI Flows are used for PAIOS's PAIOSFlow orchestrator. No third-party source covers Flows as accurately as the official channel.

#### VIDEO 04 — CrewAI Memory Systems Deep Dive
- **Title to search:** "CrewAI Memory – Build Agents That Remember"
- **Channel:** CrewAI (Official)
- **Channel URL:** `https://www.youtube.com/@crewAIInc`
- **Difficulty:** Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Agent memory is core to PAIOS. Official channel content on the memory system is authoritative and covers PostgreSQL-backed memory specifically.

#### VIDEO 05 — CrewAI + MCP Integration
- **Title to search:** "CrewAI Tools and MCP Integration Tutorial"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** The MCPServerAdapter is the bridge between Sections 04 and 06 of PAIOS. Sam Witteveen's deep MCP knowledge combined with CrewAI makes this the only high-quality video on this specific integration.

#### VIDEO 06 — LangGraph Multi-Agent Supervisor
- **Title to search:** "LangGraph Multi-Agent Supervisor Architecture"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** LangGraph is used in PAIOS Week 6 for complex workflows that CrewAI Flows can't handle (cyclical execution, complex branching). Official channel is authoritative.

#### VIDEO 07 — AI Agents Masterclass (Full Series)
- **Title to search:** "AI Agents Masterclass – Full Series"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Cole Medin's masterclass series covers n8n + LangGraph + Python agent architecture comprehensively. The architecture diagrams before each implementation are uniquely valuable.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| CrewAI Official Tutorials | CrewAI Inc | `https://www.youtube.com/@crewAIInc/playlists` | Official maintainer content — authoritative |
| Learn CrewAI | Community | `https://m.youtube.com/playlist?list=PLMVV8yyL2GN9ct3oCH1RsjYtd26BphzT6` | Curated community learning path |
| CrewAI Tutorial Series | Siddhardhan | `https://www.youtube.com/@Siddhardhan/playlists` | Production-oriented CrewAI content |

---

# SECTION 07 — HERMES AGENT
**Priority:** 🟡 Recommended | **Difficulty:** Intermediate | **Study Time:** 1 week  
**Prerequisites:** Sections 04–06 complete

### Learning Outcomes
- Build a task classification and routing system using LLM function calling
- Implement a PostgreSQL task queue with priority and status tracking
- Create a natural language → task type classifier
- Build CLI and API interfaces for task submission
- Implement async task execution with timeout and retry logic

### Milestone
`hermes submit "research X"` classifies task correctly, routes to right crew, executes, stores result.

---

#### VIDEO 01 — Building an AI Task Manager
- **Title to search:** "Build an AI Task Manager with Python and PostgreSQL"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Cole's practical focus on production agent systems includes task management and routing patterns directly applicable to Hermes.

#### VIDEO 02 — Structured Outputs for AI Agents
- **Title to search:** "Structured Outputs – Make AI Respond with JSON Every Time"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Hermes uses structured outputs for reliable task classification. Sam's deep API knowledge covers the exact patterns needed.

#### VIDEO 03 — Async Python for AI Applications
- **Title to search:** "Python AsyncIO Tutorial – Async Await Explained"
- **Channel:** Corey Schafer
- **Channel URL:** `https://www.youtube.com/@coreyms`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Hermes runs async task execution. Async Python is non-negotiable for production agent systems. Corey's tutorial is the most approachable on the topic.

#### VIDEO 04 — Building a Task Queue with Redis and Python
- **Title to search:** "Task Queues with Redis and Python – Celery Tutorial"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS uses Redis for task queuing. Understanding queue architecture prevents bottlenecks in Hermes's task dispatch.

#### VIDEO 05 — AI Agent Scheduling and Orchestration
- **Title to search:** "AI Agent Scheduling – Run Agents on a Schedule"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Hermes supports timezone-aware scheduling. Cole covers agent scheduling patterns in production environments.

#### VIDEO 06 — Click CLI Framework for Python
- **Title to search:** "Python Click Tutorial – Build Command Line Applications"
- **Channel:** ArjanCodes
- **Channel URL:** `https://www.youtube.com/@ArjanCodes`
- **Difficulty:** Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** Hermes CLI uses Click. ArjanCodes covers clean CLI design patterns.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Building AI Agent Systems | Cole Medin | `https://www.youtube.com/@ColeMedin/playlists` | Production agent architecture focus |
| Async Python | Corey Schafer | `https://www.youtube.com/@coreyms/playlists` | Foundation for async agent execution |

---

# SECTION 08 — n8n AUTOMATION
**Priority:** 🔴 Mandatory | **Difficulty:** Beginner → Intermediate | **Study Time:** 1–2 weeks  
**Prerequisites:** Section 01 complete (Docker running)

### Learning Outcomes
- Run n8n locally via Docker with PostgreSQL backend
- Build AI agent workflows with memory, tools, and sub-agents
- Connect n8n to PostgreSQL, GitHub, Notion, and Obsidian webhooks
- Implement error handling, retry logic, and monitoring
- Trigger CrewAI crews from n8n via PAIOS API
- Use n8n's native MCP support to connect agent tools

### Milestone
10 production workflows running, tested. GitHub webhook → n8n → CrewAI crew → result → Notion end-to-end.

---

#### VIDEO 01 — n8n Full Beginner Course
- **Title to search:** "n8n Tutorial for Beginners – Full Course"
- **Channel:** n8n (Official)
- **Channel URL:** `https://www.youtube.com/c/n8n-io`
- **URL:** `https://www.youtube.com/playlist?list=PLlET0GsrLUL5HKJk1rb7t32sAs_iAlpZe`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Official n8n channel. The official beginner series is the canonical starting point — covers nodes, triggers, expressions, and credentials that all subsequent workflows build on.

#### VIDEO 02 — Build AI Agents with n8n (Full Course)
- **Title to search:** "How to Build AI Agents with n8n in 2025 Full Course"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Cole Medin's n8n AI agent content is consistently rated as the best practical guide for code-first developers adopting n8n. Covers memory, tools, and production patterns.

#### VIDEO 03 — n8n AI Agents Deep Dive
- **Title to search:** "n8n AI Agent Complete Guide – Memory, Tools, Sub-Agents"
- **Channel:** Leon Van Zyl
- **Channel URL:** Search: "Leon Van Zyl n8n YouTube"
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Leon Van Zyl is a dedicated n8n expert whose content covers AI agent workflows in depth. His "AI Agent Complete Guide" is the most thorough n8n-AI tutorial available.

#### VIDEO 04 — n8n Self-Hosting Complete Setup
- **Title to search:** "n8n Self-Hosting Tutorial – Docker Setup with PostgreSQL"
- **Channel:** n8n (Official)
- **Channel URL:** `https://www.youtube.com/c/n8n-io`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** PAIOS runs self-hosted n8n. Official channel provides authoritative Docker + PostgreSQL configuration for production n8n deployments.

#### VIDEO 05 — n8n Webhook Integrations
- **Title to search:** "n8n Webhooks Tutorial – Trigger Workflows from External Apps"
- **Channel:** n8n (Official)
- **Channel URL:** `https://www.youtube.com/c/n8n-io`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** All PAIOS automation workflows use webhook triggers (GitHub, Obsidian file changes, etc.). Official channel content on webhooks is accurate and maintained.

#### VIDEO 06 — n8n MCP Integration
- **Title to search:** "n8n MCP Nodes – Connect AI Tools via Model Context Protocol"
- **Channel:** n8n (Official)
- **Channel URL:** `https://www.youtube.com/c/n8n-io`
- **Difficulty:** Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** n8n added native MCP support. This is the integration between PAIOS's n8n automation layer and MCP tool layer. Official content is essential here.

#### VIDEO 07 — n8n Error Handling Production Patterns
- **Title to search:** "n8n Error Handling – Build Reliable Production Workflows"
- **Channel:** Leon Van Zyl
- **Channel URL:** Search: "Leon Van Zyl n8n YouTube"
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Production n8n requires error handling, dead letter queues, and retry logic. Leon covers these patterns specifically for AI agent workflows.

#### VIDEO 08 — n8n GitHub Integration
- **Title to search:** "n8n GitHub Integration – Automate with GitHub Events"
- **Channel:** n8n (Official)
- **Channel URL:** `https://www.youtube.com/c/n8n-io`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS Workflow 2 (GitHub Issue Handler) uses n8n's GitHub integration. Official node documentation via video.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| n8n Official Tutorials | n8n | `https://www.youtube.com/playlist?list=PLlET0GsrLUL5HKJk1rb7t32sAs_iAlpZe` | Official canonical n8n content |
| n8n AI Agents | Cole Medin | `https://www.youtube.com/@ColeMedin/playlists` | Best code-first n8n AI content |

---

# SECTION 09 — OPENHANDS
**Priority:** 🟡 Recommended | **Difficulty:** Intermediate → Advanced | **Study Time:** 1–2 weeks  
**Prerequisites:** Docker Desktop required, Sections 06 complete

### Learning Outcomes
- Run OpenHands locally via Docker
- Understand OpenHands agent architecture (CodeAct, BrowsingAgent, Planner)
- Build automated GitHub issue → PR pipeline
- Use OpenHands SDK for custom software agents
- Implement safety guardrails and sandboxed execution
- Integrate OpenHands with PAIOS via n8n webhook

### Milestone
3 real bugs fixed autonomously on test repositories. PR pipeline from GitHub issue to PR opened, tested end-to-end.

---

#### VIDEO 01 — OpenHands Introduction and Setup
- **Title to search:** "OpenHands: Open-source AI Software Development Agents"
- **Channel:** All Hands AI (Official)
- **Channel URL:** Search: "All Hands AI YouTube"
- **URL:** `https://www.youtube.com/watch?v=oB4JR98KRAA`
- **Difficulty:** Beginner
- **Priority:** 🟡 Recommended
- **Why selected:** Official All Hands AI introduction video with real use case demonstrations. Published March 2025, covering current capabilities.

#### VIDEO 02 — OpenHands Full Setup (Windows/Docker)
- **Title to search:** "OpenHands AI Software Engineer – Generate Complex Apps End-to-End"
- **Channel:** Mervin Praison (PraisonAI)
- **Channel URL:** `https://www.youtube.com/@MervinPraison`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Covers Windows/WSL installation with Docker specifically — the PAIOS target environment. Covers available agents and models selection.

#### VIDEO 03 — OpenHands vs. Claude Code vs. Devin
- **Title to search:** "OpenHands vs Claude Code – Best AI Coding Agent 2025"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Understanding OpenHands positioning vs. alternatives informs when to use it in PAIOS workflows vs. OpenCode directly. Cole's comparisons are technically honest.

#### VIDEO 04 — Autonomous GitHub Workflow with AI
- **Title to search:** "AI Agent Fixes GitHub Issues Automatically – Full Pipeline"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** The GitHub issue → PR pipeline is the core PAIOS OpenHands use case. Cole covers this exact workflow with production considerations.

#### VIDEO 05 — AI Software Agents in Production
- **Title to search:** "AI Coding Agents in Production – What Actually Ships"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** Production context for autonomous coding agents including safety guardrails, sandboxing, and human approval gates.

#### VIDEO 06 — OpenHands with Local Models (API-Based Config)
- **Title to search:** "OpenHands API Configuration – Claude, GPT, Gemini Setup"
- **Channel:** Mervin Praison (PraisonAI)
- **Channel URL:** `https://www.youtube.com/@MervinPraison`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS uses API-based models. Mervin covers OpenHands model configuration for all major providers including Anthropic Claude.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| AI Coding Agents | Cole Medin | `https://www.youtube.com/@ColeMedin/playlists` | Best autonomous coding content |
| PraisonAI & OpenHands | Mervin Praison | `https://www.youtube.com/@MervinPraison/playlists` | Practical setup coverage |

---

# SECTION 10 — DOCKER & INFRASTRUCTURE
**Priority:** 🔴 Mandatory | **Difficulty:** Intermediate | **Study Time:** 1 week  
**Prerequisites:** Section 01 complete

### Learning Outcomes
- Build multi-service Docker Compose stacks for PAIOS
- Understand container networking (bridge/host modes)
- Implement health checks, auto-restart, and volume persistence
- Build custom Docker images for PAIOS components
- Use GitHub Actions for automated image builds and deployment

### Milestone
Single `docker-compose up` launches full PAIOS stack (PostgreSQL+pgvector, Redis, n8n, OpenHands, API gateway, Nginx). All services communicate, all data persists.

---

#### VIDEO 01 — Docker Crash Course for Absolute Beginners
- **Title to search:** "Docker Crash Course for Absolute Beginners [NEW]"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** The newest (updated) Docker basics video from Docker Captain Nana. For anyone who already watched the 3-hour course in Section 01, this is the refresher/reference. For new learners, start here.

#### VIDEO 02 — Docker Compose Crash Course
- **Title to search:** "Docker Compose Tutorial for Beginners"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Docker Compose is the primary PAIOS deployment tool. Nana's tutorial is the most complete and accurate.

#### VIDEO 03 — Docker Networking Explained
- **Title to search:** "Docker Networking Tutorial – Bridge, Host, None Networks"
- **Channel:** NetworkChuck
- **Channel URL:** `https://www.youtube.com/@NetworkChuck`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** PAIOS has 6+ services that must communicate correctly. NetworkChuck's networking background makes this the best Docker networking explanation.

#### VIDEO 04 — Building Custom Docker Images
- **Title to search:** "Dockerfile Tutorial – How to Build Docker Images"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Custom images needed for PAIOS API and agent components. Official Docker documentation doesn't cover multi-stage builds as well as Nana.

#### VIDEO 05 — GitHub Actions for Docker
- **Title to search:** "GitHub Actions Tutorial – CI/CD for Docker Applications"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** PAIOS CI/CD pipeline uses GitHub Actions to test and deploy Docker images. Nana's GitHub Actions content is consistently among the most thorough.

#### VIDEO 06 — Docker Security Best Practices
- **Title to search:** "Docker Security Best Practices – Protect Your Containers"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS runs AI agents with internet access. Container security is not optional. Covers non-root containers, secret management, and network isolation.

#### VIDEO 07 — Nginx as Reverse Proxy with Docker
- **Title to search:** "NGINX Reverse Proxy Tutorial with Docker"
- **Channel:** NetworkChuck
- **Channel URL:** `https://www.youtube.com/@NetworkChuck`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS uses Nginx as the production reverse proxy. NetworkChuck's hands-on Nginx + Docker tutorial is widely used.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Docker Tutorials | TechWorld with Nana | `https://www.youtube.com/c/TechWorldwithNana/playlists` | Complete Docker education from Docker Captain |
| Docker Series | NetworkChuck | `https://www.youtube.com/playlist?list=PLIhvC56v63IJlnU4k60d0oFIrsbXEivQo` | Practical networking + Docker focus |

---

# SECTION 11 — POSTGRESQL & AGENT MEMORY
**Priority:** 🔴 Mandatory | **Difficulty:** Intermediate | **Study Time:** 1–2 weeks  
**Prerequisites:** Section 10 (PostgreSQL running in Docker)

### Learning Outcomes
- Enable pgvector and perform similarity searches
- Design a 4-table agent memory schema (episodic, semantic, procedural, working)
- Build a PAIOSMemory Python class with store/recall/consolidate/prune operations
- Use asyncpg for async PostgreSQL in FastAPI
- Implement memory quality: importance scoring, contradiction detection, access frequency

### Milestone
1000 memories stored and retrievable. Semantic search returns relevant results. Memory consolidation reduces duplicates.

---

#### VIDEO 01 — PostgreSQL Tutorial for Beginners
- **Title to search:** "PostgreSQL Tutorial For Beginners – Full Course"
- **Channel:** freeCodeCamp.org
- **Channel URL:** `https://www.youtube.com/@freecodecamp`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** freeCodeCamp's PostgreSQL course is the most-watched beginner SQL content. Covers everything needed before pgvector, including schemas, queries, and indexes.

#### VIDEO 02 — Vector Databases Explained
- **Title to search:** "Vector Databases Explained – How They Work and When to Use Them"
- **Channel:** Fireship
- **Channel URL:** `https://www.youtube.com/@Fireship`
- **Difficulty:** Beginner
- **Priority:** 🔴 Mandatory
- **Why selected:** Fireship's conceptual explainers are the fastest way to understand new technology. Vector databases underpin the entire PAIOS memory and RAG system.

#### VIDEO 03 — pgvector Tutorial: Vector Search in PostgreSQL
- **Title to search:** "pgvector Tutorial – Semantic Search with PostgreSQL"
- **Channel:** Supabase (Official)
- **Channel URL:** `https://www.youtube.com/@Supabase`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Supabase is built on pgvector and publishes the highest-quality pgvector tutorials. Their content is directly applicable to PAIOS's PostgreSQL-native vector search.

#### VIDEO 04 — Building AI Agent Memory Systems
- **Title to search:** "AI Agent Memory – Build Long-Term Memory for AI Agents"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Sam Witteveen is the best source on YouTube for agent memory architecture. Covers episodic vs. semantic memory, importance scoring, and retrieval patterns.

#### VIDEO 05 — asyncpg: Async PostgreSQL in Python
- **Title to search:** "AsyncPG Tutorial – Async PostgreSQL with Python"
- **Channel:** ArjanCodes
- **Channel URL:** `https://www.youtube.com/@ArjanCodes`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** PAIOS uses asyncpg for all PostgreSQL operations. ArjanCodes covers async Python database patterns with the architectural depth needed.

#### VIDEO 06 — PostgreSQL Performance Tuning
- **Title to search:** "PostgreSQL Performance Tuning – Indexing, Query Optimization"
- **Channel:** Hussein Nasser
- **Channel URL:** `https://www.youtube.com/@hnasr`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Hussein Nasser is the most technically rigorous database educator on YouTube. pgvector index tuning (ivfflat vs. hnsw) directly impacts PAIOS memory performance.

#### VIDEO 07 — Redis Pub/Sub and Caching
- **Title to search:** "Redis Caching Tutorial – Speed Up Your Applications"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Redis is used for embedding cache and task queuing in PAIOS. Caching embeddings reduces API costs significantly.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| PostgreSQL Tutorials | Supabase | `https://www.youtube.com/@Supabase/playlists` | Best pgvector content |
| Database Engineering | Hussein Nasser | `https://www.youtube.com/@hnasr/playlists` | Deep database performance content |

---

# SECTION 12 — OBSIDIAN KNOWLEDGE MANAGEMENT
**Priority:** 🟡 Recommended | **Difficulty:** Beginner | **Study Time:** 3–5 days  
**Prerequisites:** Section 11 (PostgreSQL for RAG sync)

### Learning Outcomes
- Structure Obsidian vault as PAIOS knowledge base with correct folder hierarchy
- Use Dataview plugin for dynamic agent task boards
- Connect vault to RAG pipeline via auto-ingestion
- Build custom MCP server for vault operations (CRUD + search)
- Implement daily note generation via agents

### Milestone
Obsidian vault structured. New note → auto-ingested into RAG within 60 seconds. Notes readable/writable from OpenCode via MCP.

---

#### VIDEO 01 — Obsidian for Developers
- **Title to search:** "Obsidian – The Most Powerful Note-Taking App for Developers"
- **Channel:** No Boilerplate
- **Channel URL:** `https://www.youtube.com/@NoBoilerplate`
- **Difficulty:** Beginner
- **Priority:** 🟡 Recommended
- **Why selected:** No Boilerplate produces developer-focused content. His Obsidian video is specifically about using Obsidian as a code/developer second brain — directly relevant to PAIOS.

#### VIDEO 02 — Obsidian Dataview Complete Guide
- **Title to search:** "Obsidian Dataview Tutorial – Dynamic Views and Queries"
- **Channel:** Nicole van der Hoeven
- **Channel URL:** `https://www.youtube.com/@nicolevanderhoeven`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Nicole van der Hoeven is the leading Obsidian educator. Dataview is used for PAIOS's dynamic agent task boards and project views.

#### VIDEO 03 — Building a Second Brain with Obsidian
- **Title to search:** "Obsidian Second Brain Setup – Complete Workflow"
- **Channel:** Tiago Forte
- **Channel URL:** `https://www.youtube.com/@TiagoForte`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** Tiago Forte created the PARA method used in PAIOS vault structure (Projects/Areas/Resources/Archive). Understanding the PKM philosophy improves vault design.

#### VIDEO 04 — Obsidian Templater Plugin
- **Title to search:** "Obsidian Templater Tutorial – Dynamic Templates for Notes"
- **Channel:** Nicole van der Hoeven
- **Channel URL:** `https://www.youtube.com/@nicolevanderhoeven`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS agents create notes from templates. Templater is the standard plugin for this. Nicole's tutorial is authoritative.

#### VIDEO 05 — Obsidian API for Developers
- **Title to search:** "Obsidian Plugin Development – Build Custom Plugins"
- **Channel:** Obsidian Community Talks
- **Channel URL:** Search: "Obsidian Community Talks YouTube"
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** Understanding the Obsidian API is necessary for building the MCP bridge. Community Talks covers plugin architecture from first principles.

#### VIDEO 06 — PKM Systems for Technical Professionals
- **Title to search:** "Personal Knowledge Management for Engineers and Developers"
- **Channel:** No Boilerplate
- **Channel URL:** `https://www.youtube.com/@NoBoilerplate`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** Designing a knowledge system that agents can query effectively requires understanding how knowledge should be structured. No Boilerplate's developer perspective is most relevant.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Obsidian Tutorials | Nicole van der Hoeven | `https://www.youtube.com/@nicolevanderhoeven/playlists` | Most comprehensive Obsidian content |
| Obsidian for Developers | No Boilerplate | `https://www.youtube.com/@NoBoilerplate/playlists` | Developer-specific Obsidian usage |

---

# SECTION 13 — NOTION KNOWLEDGE MANAGEMENT
**Priority:** 🟢 Optional | **Difficulty:** Beginner | **Study Time:** 3–5 days  
**Prerequisites:** Section 08 (n8n for sync workflows)

### Learning Outcomes
- Use Notion API for programmatic page and database management
- Build an MCP server exposing Notion operations to agents
- Create automated sync: agent results → Notion database rows
- Build PAIOS Notion workspace template (task tracker, knowledge base, daily digest)

### Milestone
Agent task results auto-populate Notion database. Daily digest page created automatically via n8n.

---

#### VIDEO 01 — Notion API Python Tutorial
- **Title to search:** "Notion API Tutorial with Python – Create and Read Pages"
- **Channel:** Patrick Loeber (Python Engineer)
- **Channel URL:** `https://www.youtube.com/@patloeber`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** Patrick Loeber produces clean Python API tutorials. His Notion API tutorial covers the exact operations used in PAIOS: creating pages, querying databases, updating blocks.

#### VIDEO 02 — n8n + Notion Automation
- **Title to search:** "n8n Notion Integration – Automate Your Notion Workspace"
- **Channel:** n8n (Official)
- **Channel URL:** `https://www.youtube.com/c/n8n-io`
- **Difficulty:** Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** PAIOS uses n8n to sync to Notion. Official node documentation via video ensures correct configuration.

#### VIDEO 03 — Notion as a Database for AI Applications
- **Title to search:** "Notion API as a Database – Full Tutorial"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** Using Notion as a structured data store for agent outputs requires understanding database properties and filtering. Sam covers the API patterns comprehensively.

#### VIDEO 04 — Notion Automations and Integrations
- **Title to search:** "Notion Automations – Automate Your Workspace"
- **Channel:** Thomas Frank Explains
- **Channel URL:** `https://www.youtube.com/@ThomasFrankExplains`
- **Difficulty:** Beginner
- **Priority:** 🟢 Optional
- **Why selected:** Thomas Frank is the most-watched Notion educator. Understanding native Notion automations helps design what to offload to agents vs. handle natively.

#### VIDEO 05 — Build a Notion Dashboard for AI Projects
- **Title to search:** "Notion Dashboard Setup – Project Management for Developers"
- **Channel:** Thomas Frank Explains
- **Channel URL:** `https://www.youtube.com/@ThomasFrankExplains`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** The PAIOS Notion template is based on a developer project dashboard. Thomas Frank's templates and structure advice are widely adopted.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Notion Tutorials | Thomas Frank Explains | `https://www.youtube.com/@ThomasFrankExplains/playlists` | Best Notion education |
| Notion API | Patrick Loeber | `https://www.youtube.com/@patloeber/playlists` | Python Notion API focus |

---

# SECTION 14 — RAG SYSTEMS
**Priority:** 🔴 Mandatory | **Difficulty:** Intermediate → Advanced | **Study Time:** 2 weeks  
**Prerequisites:** Section 11 (pgvector running)

### Learning Outcomes
- Build production RAG with semantic chunking and contextual prefix injection
- Implement hybrid search (vector + BM25 keyword)
- Add reranking with cross-encoder or Cohere
- Build ingestion pipelines for PDF, Markdown, GitHub repos, URLs, YouTube transcripts
- Evaluate RAG quality with RAGAS metrics
- Build auto-ingestion watcher for Obsidian vault

### Milestone
Full RAG pipeline ingesting 3+ source types. Hybrid search outperforms vector-only. RAGAS faithfulness score > 0.8.

---

#### VIDEO 01 — RAG from Scratch (Complete Series)
- **Title to search:** "RAG from Scratch – Full Series"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Intermediate
- **Priority:** 🔴 Mandatory
- **Why selected:** Official LangChain RAG from scratch series is the canonical YouTube resource for understanding RAG at the implementation level. Builds every component individually before assembling.

#### VIDEO 02 — Advanced RAG Techniques
- **Title to search:** "Advanced RAG – Improve Retrieval with Hybrid Search and Reranking"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Production RAG requires hybrid search and reranking. Sam Witteveen covers these advanced techniques with implementations that match the PAIOS pgvector stack.

#### VIDEO 03 — pgvector RAG: Build RAG with PostgreSQL
- **Title to search:** "Build a RAG App with pgvector and PostgreSQL"
- **Channel:** Supabase (Official)
- **Channel URL:** `https://www.youtube.com/@Supabase`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** PAIOS uses PostgreSQL+pgvector for RAG, not a separate vector DB. Supabase's pgvector RAG tutorials are directly applicable — no translation required.

#### VIDEO 04 — Contextual Retrieval (Anthropic Method)
- **Title to search:** "Contextual Retrieval – Better RAG with Claude"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** PAIOS uses Anthropic's contextual prefix injection method for chunking. Sam Witteveen covered this technique from the Anthropic research post — the best practical implementation video.

#### VIDEO 05 — RAG Evaluation with RAGAS
- **Title to search:** "Evaluating RAG Systems with RAGAS – Tutorial"
- **Channel:** AI Jason
- **Channel URL:** `https://www.youtube.com/@AIJasonZ`
- **Difficulty:** Advanced
- **Priority:** 🔴 Mandatory
- **Why selected:** Unmeasured RAG is unmanageable RAG. AI Jason covers RAGAS evaluation metrics including faithfulness, answer relevancy, and context precision — the metrics used in PAIOS.

#### VIDEO 06 — LlamaIndex Advanced RAG
- **Title to search:** "LlamaIndex Advanced RAG – Production Patterns"
- **Channel:** LlamaIndex (Official)
- **Channel URL:** `https://www.youtube.com/@LlamaIndex`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** LlamaIndex's RAG patterns (hierarchical retrieval, recursive summarization) inform PAIOS RAG architecture even when not using LlamaIndex directly.

#### VIDEO 07 — PDF RAG with Python
- **Title to search:** "RAG over PDFs – Build a PDF Question Answering System"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** PDF is a primary PAIOS knowledge source. Cole's implementation uses PyMuPDF + embeddings + pgvector — matching the PAIOS stack exactly.

#### VIDEO 08 — Multi-Source RAG Pipeline
- **Title to search:** "Multi-Source RAG – Ingest Web, PDF, YouTube into One Knowledge Base"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS Knowledge Engine ingests from 6 source types. Cole's multi-source RAG implementation is the closest match to the PAIOS ingestion pipeline architecture.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| RAG from Scratch | LangChain | `https://www.youtube.com/@LangChain/playlists` | Canonical RAG education |
| Vector Search & RAG | Supabase | `https://www.youtube.com/@Supabase/playlists` | pgvector-native RAG content |
| LlamaIndex Tutorials | LlamaIndex | `https://www.youtube.com/@LlamaIndex/playlists` | Advanced retrieval patterns |

---

# SECTION 15 — BROWSER AUTOMATION
**Priority:** 🟡 Recommended | **Difficulty:** Intermediate | **Study Time:** 1 week  
**Prerequisites:** Section 05 (Playwright in paios-skills)

### Learning Outcomes
- Use Playwright Python for reliable, production browser automation
- Build an AI-native browser agent (research, monitor, extract, form-fill modes)
- Run browser sessions in Docker containers (headless)
- Connect browser automation as a CrewAI tool and MCP tool
- Implement responsible scraping patterns

### Milestone
Browser agent researches 5 topics, stores results in RAG. Monitoring task detects page changes. Docker isolation verified.

---

#### VIDEO 01 — Playwright Python Complete Course
- **Title to search:** "Playwright Python Tutorial – Full Course"
- **Channel:** Hitesh Choudhary
- **Channel URL:** `https://www.youtube.com/@HiteshCodeLab`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Most comprehensive Playwright Python tutorial available. Covers selectors, waits, screenshots, and page navigation — all core to the PAIOS browser agent.

#### VIDEO 02 — browser-use: AI-Powered Browser Automation
- **Title to search:** "browser-use Python Library – AI Agent Controls the Browser"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** browser-use is the Python library used in PAIOS for AI-native browser automation. Cole covers the library with practical examples.

#### VIDEO 03 — Web Scraping with Playwright at Scale
- **Title to search:** "Web Scraping with Playwright – Scrape JavaScript Websites"
- **Channel:** John Watson Rooney
- **Channel URL:** `https://www.youtube.com/@JohnWatsonRooney`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** John Watson Rooney is the most trusted web scraping educator. Playwright+Python for JS-heavy sites is directly applicable to PAIOS web research tools.

#### VIDEO 04 — Browser Automation with AI Agents
- **Title to search:** "AI Browser Agents – Control Web Browsers with AI"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Connecting browser automation to LLM decision-making requires understanding the agent loop + browser observation patterns. Sam covers this integration.

#### VIDEO 05 — Playwright in Docker
- **Title to search:** "Run Playwright Tests in Docker – Headless Browser Setup"
- **Channel:** Playwright (Official)
- **Channel URL:** `https://www.youtube.com/@Playwright`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS browser agents run in Docker containers. Official Playwright Docker setup ensures correct headless configuration.

#### VIDEO 06 — Responsible Web Scraping
- **Title to search:** "Ethical Web Scraping – Best Practices and Legal Considerations"
- **Channel:** John Watson Rooney
- **Channel URL:** `https://www.youtube.com/@JohnWatsonRooney`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** PAIOS browser agents must respect robots.txt, rate limits, and ToS. John's coverage of responsible scraping prevents legal and ethical issues.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Web Scraping Tutorials | John Watson Rooney | `https://www.youtube.com/@JohnWatsonRooney/playlists` | Best web scraping content |
| Playwright Tutorials | Playwright Official | `https://www.youtube.com/@Playwright/playlists` | Official Playwright education |

---

# SECTION 16 — COMPUTER USE AGENTS
**Priority:** 🟢 Optional | **Difficulty:** Advanced | **Study Time:** 2 weeks  
**Prerequisites:** Sections 06, 10, 15 complete. Docker sandbox mandatory before proceeding.

### ⚠️ Safety Requirement
All computer use agents must run in isolated Docker containers with no host filesystem access and no LAN access before any implementation begins. Human approval gates are non-negotiable.

### Learning Outcomes
- Use Anthropic Computer Use API for GUI automation
- Build agents that interact with desktop environments
- Implement mandatory human approval gates for every consequential action
- Design safety guardrails and audit logging
- Understand when computer use is the right tool vs. API/browser

### Milestone
2 desktop automation tasks completed in Docker sandbox. Human approval gate blocks execution without confirmation. Audit log records every action.

---

#### VIDEO 01 — Anthropic Computer Use API Explained
- **Title to search:** "Claude Computer Use – AI Controls Your Computer"
- **Channel:** Fireship
- **Channel URL:** `https://www.youtube.com/@Fireship`
- **Difficulty:** Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** Fireship's concise explainer covers what computer use is and its implications before implementation.

#### VIDEO 02 — Computer Use Agent Tutorial
- **Title to search:** "Anthropic Computer Use API Tutorial – Build GUI Automation Agents"
- **Channel:** Sam Witteveen
- **Channel URL:** `https://www.youtube.com/@samwitteveenai`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** Sam Witteveen's technical depth on the Anthropic API extends to computer use. Covers the screenshot loop, action encoding, and safety considerations.

#### VIDEO 03 — AI Agents Safety and Guardrails
- **Title to search:** "AI Agent Safety – Building Safe Autonomous Systems"
- **Channel:** AI Jason
- **Channel URL:** `https://www.youtube.com/@AIJasonZ`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** Safety is not an afterthought in computer use agents. AI Jason covers agent safety patterns including approval gates and action auditing.

#### VIDEO 04 — Desktop Automation with Python
- **Title to search:** "PyAutoGUI Tutorial – Desktop Automation with Python"
- **Channel:** Sentdex
- **Channel URL:** `https://www.youtube.com/@sentdex`
- **Difficulty:** Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** PyAutoGUI is a lightweight alternative to full computer use API for simple desktop tasks. Sentdex is the most-watched Python automation channel.

#### VIDEO 05 — Docker Sandboxing for AI Agents
- **Title to search:** "Docker Security – Sandbox Applications and Isolate Containers"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** Computer use agents must be sandboxed. Nana's Docker security content covers the isolation patterns required for safe computer use deployment.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Automation with Python | Sentdex | `https://www.youtube.com/@sentdex/playlists` | Python automation foundation |
| AI Safety & Agents | AI Jason | `https://www.youtube.com/@AIJasonZ/playlists` | Agent safety patterns |

---

# SECTION 17 — GITHUB & OPEN SOURCE CONTRIBUTION
**Priority:** 🟡 Recommended | **Difficulty:** Intermediate | **Study Time:** Ongoing  
**Prerequisites:** Git proficient, at least one PAIOS component understood deeply

### Learning Outcomes
- Navigate open-source contribution workflows (issue → fork → branch → PR → review)
- Set up GitHub Actions CI/CD for PAIOS
- Find and filter good-first-issues in target projects
- Write quality PRs with proper descriptions and tests
- Build automated contribution tracking in PAIOS

### Milestone
5 PRs opened to target projects (OpenCode, CrewAI, n8n, OpenHands, pgvector). At least 1 merged.

---

#### VIDEO 01 — How to Contribute to Open Source
- **Title to search:** "How to Contribute to Open Source – A Practical Guide"
- **Channel:** Eddie Jaoude
- **Channel URL:** `https://www.youtube.com/@eddiejaoude`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Eddie Jaoude is the most trusted open-source contribution educator. His practical guides on finding issues, making PRs, and engaging with maintainers are the standard reference.

#### VIDEO 02 — GitHub Actions Complete Course
- **Title to search:** "GitHub Actions Tutorial – Complete CI/CD Pipeline"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS GitHub Actions CI/CD pipeline deploys Docker images on push. Nana's complete GitHub Actions course covers everything needed.

#### VIDEO 03 — Reading Large Codebases
- **Title to search:** "How to Read Code – Understanding Large Codebases Quickly"
- **Channel:** ThePrimeagen
- **Channel URL:** `https://www.youtube.com/@ThePrimeagen`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** Contributing to OpenCode, CrewAI, or n8n requires navigating large, unfamiliar codebases. ThePrimeagen's strategy for reading code is directly applicable.

#### VIDEO 04 — Writing Good PRs and Issues
- **Title to search:** "How to Write Great GitHub Issues and Pull Requests"
- **Channel:** Eddie Jaoude
- **Channel URL:** `https://www.youtube.com/@eddiejaoude`
- **Difficulty:** Beginner-Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** The quality of your PR description determines whether maintainers review it. Eddie Jaoude covers the communication norms of OSS contribution.

#### VIDEO 05 — Git Advanced Techniques
- **Title to search:** "Advanced Git Tutorial – Rebase, Cherry-Pick, Stash"
- **Channel:** freeCodeCamp.org
- **Channel URL:** `https://www.youtube.com/@freecodecamp`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Contributing to active repos requires rebasing, resolving conflicts, and clean commit history. freeCodeCamp's advanced Git course covers these techniques.

#### VIDEO 06 — GitHub Copilot in Open Source Workflows
- **Title to search:** "GitHub Actions Advanced – Matrix Builds, Secrets, Environments"
- **Channel:** GitHub (Official)
- **Channel URL:** `https://www.youtube.com/@GitHub`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** Advanced GitHub Actions features (matrix builds, environments) are used in PAIOS for cross-platform testing of agent components.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| Open Source Contribution | Eddie Jaoude | `https://www.youtube.com/@eddiejaoude/playlists` | Best OSS contribution education |
| GitHub Actions | TechWorld with Nana | `https://www.youtube.com/c/TechWorldwithNana/playlists` | CI/CD for PAIOS deployment |

---

# SECTION 18 — ADVANCED SYSTEM ARCHITECTURE
**Priority:** 🟡 Recommended | **Difficulty:** Advanced | **Study Time:** 2 weeks  
**Prerequisites:** Sections 06, 08, 11, 14 complete. Working PAIOS with active agents.

### Learning Outcomes
- Implement LangGraph for complex cyclical agent workflows
- Build an A2A-compatible agent communication protocol
- Design fault-tolerant systems with checkpointing
- Add structured observability: tracing, cost tracking, error rates
- Build evaluation frameworks for agent quality measurement

### Milestone
LangGraph supervisor handles 3 complex workflows. Observability dashboard shows real-time agent data. Cost alerts fire correctly.

---

#### VIDEO 01 — LangGraph Complete Tutorial
- **Title to search:** "LangGraph Tutorial – Build Stateful Multi-Agent Applications"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Official LangChain tutorial for LangGraph. Stateful agent graphs with conditional routing are used in PAIOS's advanced orchestration layer.

#### VIDEO 02 — LangSmith: Agent Observability
- **Title to search:** "LangSmith Tutorial – Debug and Monitor Your AI Agents"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** LangSmith provides tracing for LangGraph and LangChain agents. The observability patterns apply even when using the PAIOS custom dashboard.

#### VIDEO 03 — Building Reliable AI Systems
- **Title to search:** "Building Reliable AI Agents – Fault Tolerance and Error Handling"
- **Channel:** AI Jason
- **Channel URL:** `https://www.youtube.com/@AIJasonZ`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Production AI systems require graceful degradation, retry policies, and fallback handling. AI Jason covers reliability patterns specifically for multi-agent systems.

#### VIDEO 04 — Agent Evaluation and Testing
- **Title to search:** "AI Agent Evaluation – How to Test and Measure Agent Performance"
- **Channel:** LangChain (Official)
- **Channel URL:** `https://www.youtube.com/@LangChain`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Untested agents are undeployable agents. LangChain's evaluation content covers the metrics and frameworks needed to measure PAIOS agent quality.

#### VIDEO 05 — Pydantic AI for Production Agents
- **Title to search:** "PydanticAI Tutorial – Type-Safe AI Agents with Pydantic"
- **Channel:** Cole Medin
- **Channel URL:** `https://www.youtube.com/@ColeMedin`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Cole Medin explicitly cites Pydantic AI and LangGraph as his two favorite frameworks. Type-safe agent outputs reduce runtime errors in production PAIOS.

#### VIDEO 06 — Microservices Architecture for AI
- **Title to search:** "Microservices Architecture Tutorial – Design Patterns"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** PAIOS is a microservices architecture. Understanding service decomposition, communication patterns, and data consistency applies directly.

#### VIDEO 07 — Event-Driven Architecture
- **Title to search:** "Event-Driven Architecture – Pub/Sub, Message Queues Explained"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Advanced
- **Priority:** 🟢 Optional
- **Why selected:** PAIOS uses Redis pub/sub for event-driven agent coordination. Nana covers event-driven patterns in the context of real distributed systems.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| LangGraph Tutorials | LangChain | `https://www.youtube.com/@LangChain/playlists` | Official stateful agent content |
| System Design | TechWorld with Nana | `https://www.youtube.com/c/TechWorldwithNana/playlists` | Architecture patterns |

---

# SECTION 19 — PRODUCTION DEPLOYMENT
**Priority:** 🟡 Recommended | **Difficulty:** Advanced | **Study Time:** 2 weeks  
**Prerequisites:** All 🔴 Mandatory sections complete, working local PAIOS

### Learning Outcomes
- Deploy PAIOS behind Nginx reverse proxy with HTTPS
- Implement secrets management (no keys in code)
- Configure automated PostgreSQL backups
- Set up monitoring, alerting, and uptime checks
- Build CI/CD pipeline: push → test → build → deploy
- Harden containers for production security

### Milestone
PAIOS accessible at real HTTPS URL. CI/CD push-to-deploy in under 5 minutes. Backup verified by restore test.

---

#### VIDEO 01 — Self-Hosted Production AI Stack
- **Title to search:** "Self-Hosting AI Apps in Production – Docker, Nginx, HTTPS"
- **Channel:** NetworkChuck
- **Channel URL:** `https://www.youtube.com/@NetworkChuck`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** NetworkChuck's production self-hosting content is the most practical on YouTube. Covers Nginx, SSL certificates, and Docker in the specific combination used by PAIOS.

#### VIDEO 02 — Nginx HTTPS with Let's Encrypt
- **Title to search:** "NGINX with Let's Encrypt SSL Tutorial – Secure Your Server"
- **Channel:** NetworkChuck
- **Channel URL:** `https://www.youtube.com/@NetworkChuck`
- **Difficulty:** Intermediate
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS production uses Nginx + Let's Encrypt for HTTPS. NetworkChuck's practical approach covers the exact setup needed.

#### VIDEO 03 — GitHub Actions Complete CI/CD Pipeline
- **Title to search:** "GitHub Actions Full Course – Build a Complete CI/CD Pipeline"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS's `.github/workflows/deploy.yml` pipeline is based on the patterns in Nana's complete CI/CD course.

#### VIDEO 04 — PostgreSQL Backup and Recovery
- **Title to search:** "PostgreSQL Backup Tutorial – pg_dump and Restore"
- **Channel:** Hussein Nasser
- **Channel URL:** `https://www.youtube.com/@hnasr`
- **Difficulty:** Intermediate-Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS agent memory lives in PostgreSQL. Losing it is catastrophic. Hussein Nasser's backup tutorial covers pg_dump strategies for Docker-hosted PostgreSQL.

#### VIDEO 05 — Docker Production Best Practices
- **Title to search:** "Docker in Production – Best Practices for Production Deployments"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** Production Docker requires health checks, resource limits, log management, and zero-downtime deployments. Nana covers all of these.

#### VIDEO 06 — Monitoring Your Production Apps
- **Title to search:** "Application Monitoring Tutorial – Logs, Metrics, Alerting"
- **Channel:** TechWorld with Nana
- **Channel URL:** `https://www.youtube.com/c/TechWorldwithNana`
- **Difficulty:** Advanced
- **Priority:** 🟡 Recommended
- **Why selected:** PAIOS production monitoring (cost alerts, error rates, uptime) requires understanding log aggregation and metric collection patterns.

#### VIDEO 07 — Cloudflare Tunnel for Self-Hosted Apps
- **Title to search:** "Cloudflare Tunnel Tutorial – Expose Local Services to the Internet"
- **Channel:** NetworkChuck
- **Channel URL:** `https://www.youtube.com/@NetworkChuck`
- **Difficulty:** Intermediate
- **Priority:** 🟢 Optional
- **Why selected:** For Windows users without a static IP, Cloudflare Tunnel is the best way to expose PAIOS to the internet. NetworkChuck covers this with a hands-on demo.

### Best Playlists

| Playlist | Channel | URL | Why |
|----------|---------|-----|-----|
| DevOps Bootcamp | TechWorld with Nana | `https://www.youtube.com/c/TechWorldwithNana/playlists` | Complete production deployment education |
| Self-Hosted Apps | NetworkChuck | `https://www.youtube.com/@NetworkChuck/playlists` | Practical self-hosting for developers |

---

# MASTER CHANNEL REFERENCE

| Channel | Handle | Focus | Quality Signal |
|---------|--------|-------|---------------|
| NetworkChuck | `@NetworkChuck` | Networking, WSL2, Docker, Nginx | 3M+ subscribers, Docker tutorials widely cited |
| TechWorld with Nana | `@TechWorldwithNana` | Docker, DevOps, CI/CD | Official Docker Captain |
| Fireship | `@Fireship` | AI tools, quick explainers | 3M+ subscribers, consistently cited |
| Cole Medin | `@ColeMedin` | AI Agents, n8n, LangGraph, MCP | Ranked #1 AI agent educator 2026 |
| Sam Witteveen | `@samwitteveenai` | AI Agents, MCP, LLMs | Google ML Developer Expert |
| IndyDevDan | `@IndyDevDan` | MCP servers, terminal AI tools | Leading MCP educator on YouTube |
| AI Jason | `@AIJasonZ` | Agent patterns, RAG, evaluation | Consistent quality, accurate technical content |
| LangChain (Official) | `@LangChain` | RAG, LangGraph, LangSmith | Official maintainer content |
| CrewAI (Official) | `@crewAIInc` | Multi-agent systems, Flows | Official maintainer content |
| n8n (Official) | `@n8n-io` | Workflow automation, MCP | Official maintainer content |
| Supabase | `@Supabase` | pgvector, databases, RAG | Best pgvector tutorials |
| Corey Schafer | `@coreyms` | Python tutorials, packaging | Most cited Python educator |
| ArjanCodes | `@ArjanCodes` | Python architecture, FastAPI | Best clean code Python content |
| freeCodeCamp | `@freecodecamp` | Git, SQL, crash courses | Most-watched free tech education |
| Hussein Nasser | `@hnasr` | PostgreSQL, databases | Most rigorous DB educator |
| Eddie Jaoude | `@eddiejaoude` | Open source contribution | OSS community leader |
| Andrej Karpathy | `@AndrejKarpathy` | LLM fundamentals | Highest-credibility AI educator |
| ThePrimeagen | `@ThePrimeagen` | Dev tools, code reading | Trusted senior dev perspective |
| Nicole van der Hoeven | `@nicolevanderhoeven` | Obsidian, PKM | Leading Obsidian educator |
| No Boilerplate | `@NoBoilerplate` | Developer tools, Obsidian | Developer-specific PKM content |
| LlamaIndex (Official) | `@LlamaIndex` | Advanced RAG | Official maintainer RAG content |
| John Watson Rooney | `@JohnWatsonRooney` | Web scraping | Most trusted scraping educator |
| Hitesh Choudhary | `@HiteshCodeLab` | Playwright, Python | Practical Python automation |
| Mervin Praison | `@MervinPraison` | AI tools, OpenHands, LiteLLM | Broad AI tools coverage |
| Patrick Loeber | `@patloeber` | Python APIs, Notion | Clean Python API tutorials |
| Thomas Frank Explains | `@ThomasFrankExplains` | Notion | Most-watched Notion educator |
| GitHub (Official) | `@GitHub` | GitHub Actions | Official GitHub content |
| Siddhardhan | `@Siddhardhan` | ML/AI projects, CrewAI | Production ML/AI projects |
| Tiago Forte | `@TiagoForte` | PKM, Second Brain | PARA method creator |
| Sentdex | `@sentdex` | Python automation | Veteran Python educator |
| Playwright (Official) | `@Playwright` | Browser automation | Official Playwright content |
| Visual Studio Code | `@code` | VS Code, WSL | Official Microsoft VS Code |

---

# CHRONOLOGICAL STUDY SCHEDULE

## Phase 1: Foundation (Weeks 1–2)
```
Week 1: Sections 01 + 02
  Days 1-3: Section 01 (WSL2, Python, Docker, Git, VS Code)
  Days 4-7: Section 02 (AI Agent Fundamentals)
  
Week 2: Sections 03 + 04
  Days 8-10: Section 03 (OpenCode setup and configuration)
  Days 11-14: Section 04 (MCP Servers, build first custom server)
```
**Milestone:** OpenCode running. First MCP server connected. Tool-calling agent built from scratch.

## Phase 2: Orchestration (Weeks 3–4)
```
Week 3: Sections 05 + 06
  Days 15-17: Section 05 (Skills library, FastAPI tools)
  Days 18-21: Section 06 (CrewAI crews + Flows)
  
Week 4: Sections 07 + 08
  Days 22-24: Section 07 (Hermes task manager)
  Days 25-28: Section 08 (n8n automation hub)
```
**Milestone:** Multi-agent crew routes tasks. 10 n8n workflows running. Hermes classifies and dispatches.

## Phase 3: Knowledge Engine (Weeks 5–6)
```
Week 5: Sections 10 + 11
  Days 29-31: Section 10 (Docker Compose full PAIOS stack)
  Days 32-35: Section 11 (PostgreSQL + pgvector + memory)
  
Week 6: Sections 12 + 13 + 14
  Days 36-37: Section 12 (Obsidian setup + MCP)
  Days 38-39: Section 13 (Notion if using)
  Days 40-42: Section 14 (RAG system)
```
**Milestone:** Full PAIOS stack in Docker. Memory persists across sessions. RAG ingests 100+ documents.

## Phase 4: Automation & Advanced Agents (Weeks 7–8)
```
Week 7: Sections 09 + 15
  Days 43-46: Section 09 (OpenHands + PR pipeline)
  Days 47-49: Section 15 (Browser automation)
  
Week 8: Section 16 + 17
  Days 50-53: Section 16 (Computer use, sandboxed)
  Days 54-56: Section 17 (OSS contributions)
```
**Milestone:** Autonomous PR pipeline live. Browser research agent operational. First OSS PR submitted.

## Phase 5: Production (Weeks 9–12)
```
Weeks 9-10: Section 18 (Advanced architecture)
Weeks 11-12: Section 19 (Production deployment + portfolio)
```
**Milestone:** PAIOS live at HTTPS URL. CI/CD deployed. Portfolio published. OSS PR merged.

---

# PREREQUISITES MAP

```
Section 01 (Foundation)
    └── Section 02 (AI Fundamentals)
            ├── Section 03 (OpenCode)
            │       └── Section 05 (Skills)
            │               └── Section 06 (CrewAI)
            │                       └── Section 07 (Hermes)
            ├── Section 04 (MCP)
            │       └── Section 06 (CrewAI)
            └── Section 10 (Docker)
                    ├── Section 08 (n8n)
                    │       └── Section 09 (OpenHands)
                    └── Section 11 (PostgreSQL)
                            ├── Section 12 (Obsidian)
                            ├── Section 13 (Notion)
                            └── Section 14 (RAG)
                                    └── Section 15 (Browser)
                                            └── Section 16 (Computer Use)

Sections 17-19 require: all above sections at basic level
```

---

*PAIOS YouTube Roadmap · June 2026*  
*All channels verified as active. Search exact video titles for reliable results.*  
*Every channel URL format: `https://www.youtube.com/@Handle`*
