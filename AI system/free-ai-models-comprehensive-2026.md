# 🆓 Free AI Models: The Ultimate 2026 Guide

> **Last Updated:** June 2026 | Covers chat interfaces, free API tiers, and open-source self-hosted models.  
> All benchmark data sourced from publicly verified evaluations (SWE-Bench, GPQA Diamond, LiveCodeBench, Artificial Analysis Intelligence Index, and provider documentation).

---

## Table of Contents

1. [How to Read This Guide](#1-how-to-read-this-guide)
2. [Provider Overview & Free Tier Summary](#2-provider-overview--free-tier-summary)
3. [Provider Deep-Dives & Model Rankings](#3-provider-deep-dives--model-rankings)
   - [Google — Gemini & Gemma](#31-google--gemini--gemma)
   - [Meta — Llama 4 (via Groq, Cerebras, OpenRouter)](#32-meta--llama-4-via-groq-cerebras-openrouter)
   - [DeepSeek — V3 / R1 (via OpenRouter, NVIDIA NIM)](#33-deepseek--v3--r1-via-openrouter-nvidia-nim)
   - [Mistral AI — Mistral & Devstral (free tier)](#34-mistral-ai--mistral--devstral-free-tier)
   - [Alibaba / Qwen — Qwen3 family](#35-alibaba--qwen--qwen3-family)
   - [xAI — Grok (via GitHub Models)](#36-xai--grok-via-github-models)
   - [OpenAI — GPT-4o / GPT-4o Mini (chat free tier)](#37-openai--gpt-4o--gpt-4o-mini-chat-free-tier)
   - [Anthropic — Claude Sonnet (chat free tier)](#38-anthropic--claude-sonnet-chat-free-tier)
   - [NVIDIA NIM — Free Hosted Models](#39-nvidia-nim--free-hosted-models)
   - [Groq — Speed-Optimized Free API](#310-groq--speed-optimized-free-api)
   - [Cerebras — Ultra-Fast Free API](#311-cerebras--ultra-fast-free-api)
   - [OpenRouter — Aggregated Free Models](#312-openrouter--aggregated-free-models)
   - [Cloudflare Workers AI](#313-cloudflare-workers-ai)
   - [GitHub Models](#314-github-models)
   - [Hugging Face (Serverless Inference API)](#hugging-face-serverless-inference-api)
   - [Cohere](#cohere)
4. [Cross-Provider Rankings by Category](#4-cross-provider-rankings-by-category)
   - [Best for Coding](#41-best-for-coding)
   - [Best for Reasoning](#42-best-for-reasoning)
   - [Best for Debugging](#43-best-for-debugging)
   - [Fastest Models (Speed)](#44-fastest-models-speed)
   - [Longest Context Window](#45-longest-context-window)
   - [Best Multimodal Capabilities](#46-best-multimodal-capabilities)
   - [Best Overall Performance](#47-best-overall-performance)
   - [Coding Benchmarks (Detailed)](#coding-benchmarks-detailed)
   - [Reasoning Benchmarks (Detailed)](#reasoning-benchmarks-detailed)
   - [Speed / Latency (Detailed Tokens Per Second)](#speed--latency-detailed-tokens-per-second)
5. [Use-Case Recommendations](#5-use-case-recommendations)
   - [Recommendations by User Type](#recommendations-by-user-type)
6. [Free Tier Limitations Comparison](#6-free-tier-limitations-comparison)
7. [Privacy & Data Handling](#7-privacy--data-handling)
8. [Stacking Free Tiers: The Zero-Cost Inference Stack](#8-stacking-free-tiers-the-zero-cost-inference-stack)
9. [Quick-Pick Decision Tree](#9-quick-pick-decision-tree)
10. [AI Development Ecosystem & Tooling](#10-ai-development-ecosystem--tooling)
    - [AI Coding Agents](#101-ai-coding-agents)
    - [MCP Servers](#102-mcp-servers)
    - [AI Frameworks & Orchestration](#103-ai-frameworks--orchestration)
    - [Multi-Agent Systems](#104-multi-agent-systems)
    - [LLM Providers & Local Models](#105-llm-providers--local-models)
    - [RAG & Knowledge Systems](#106-rag--knowledge-systems)
    - [Vector Databases](#107-vector-databases)
    - [Backend Development](#108-backend-development)
    - [Frontend Development](#109-frontend-development)
    - [Databases & Storage](#1010-databases--storage)
    - [DevOps & Deployment](#1011-devops--deployment)
    - [Observability & Monitoring](#1012-observability--monitoring)
    - [Automation & Workflows](#1013-automation--workflows)
    - [Authentication & Security](#1014-authentication--security)
    - [Testing & Evaluation](#1015-testing--evaluation)
    - [Productivity & Project Management](#1016-productivity--project-management)
    - [Recommended Tech Stacks](#1017-recommended-tech-stacks)
    - [Learning Roadmap](#1018-learning-roadmap)
    - [Implementation Priorities](#1019-implementation-priorities)
    - [Quick Reference: Tool by Category Summary](#1020-quick-reference-tool-by-category-summary)
    - [Essential GitHub Repositories](#1021-essential-github-repositories)
11. [Personal AI OS Architecture](#11-personal-ai-os-architecture)
    - [System Overview](#111-system-overview)
    - [Architecture Diagram](#112-architecture-diagram)
    - [Component Explanations](#113-component-explanations)
    - [Agent Architecture](#114-agent-architecture)
    - [Memory Architecture](#115-memory-architecture)
    - [Knowledge Management](#116-knowledge-management)
    - [Task Orchestration](#117-task-orchestration)
    - [Development Workflow](#118-development-workflow)
    - [Monitoring and Logging](#119-monitoring-and-logging)
    - [OpenCode as Command Center](#1110-opencode-as-command-center)
    - [Folder Structure](#1111-folder-structure)
    - [Docker Setup](#1112-docker-setup)
    - [MCP Server Configuration](#1113-mcp-server-configuration)
    - [Environment Variables](#1114-environment-variables)
    - [Database Schema](#1115-database-schema)
    - [Workflow Examples](#1116-workflow-examples)
    - [Installation Roadmap](#1117-installation-roadmap)
    - [Security Practices](#1118-security-practices)
    - [Backup Strategy](#1119-backup-strategy)
    - [Troubleshooting Guide](#1120-troubleshooting-guide)
    - [Scaling Path](#1121-scaling-path)

---

## 1. How to Read This Guide

### Scope of "Free"

This guide covers three types of free access:

| Type | What It Means |
|---|---|
| **Free Chat Interface** | No account credit card needed; access via browser app (claude.ai, chat.openai.com, gemini.google.com, etc.) |
| **Free API Tier** | Permanent free-tier API keys with rate limits, no trial expiry |
| **Open Source / Self-Hosted** | Download and run locally for free (hardware costs only) via Ollama, Hugging Face, etc. |

### Benchmark Key

| Benchmark | What It Tests |
|---|---|
| **SWE-Bench Verified** | Real GitHub issue resolution (coding) |
| **LiveCodeBench** | Live coding competition problems |
| **GPQA Diamond** | Graduate-level science/reasoning |
| **HLE (Humanity's Last Exam)** | Expert-level multi-domain reasoning |
| **MMMU-Pro** | Multimodal understanding |
| **Artificial Analysis Intelligence Index** | Composite of 10 evaluations |

### Rating Scale (used in this guide)

⭐⭐⭐⭐⭐ = Exceptional | ⭐⭐⭐⭐ = Very Good | ⭐⭐⭐ = Good | ⭐⭐ = Average | ⭐ = Limited

---

## 2. Provider Overview & Free Tier Summary

| Provider | Free Chat | Free API | Open-Source | Best Free Models |
|---|---|---|---|---|
| **Google** | ✅ Gemini app | ✅ AI Studio (permanent) | ✅ Gemma family | Gemini 2.5 Flash, Gemma 3 27B |
| **Meta** | ❌ | Via Groq/Cerebras | ✅ Llama 4 family | Llama 4 Scout, Llama 4 Maverick |
| **DeepSeek** | ✅ chat.deepseek.com | ✅ Limited credits | ✅ DeepSeek V3/R1 | DeepSeek R1, DeepSeek V3 |
| **Mistral AI** | ✅ le Chat | ✅ Free tier (rate-limited) | ✅ Mistral 7B, Devstral | Devstral, Mistral Small |
| **Alibaba/Qwen** | ✅ Tongyi | Via OpenRouter | ✅ Qwen3 family | Qwen3 235B, Qwen3-Coder |
| **xAI** | ✅ Grok (X.com) | Via GitHub Models | ❌ | Grok 3, Grok 3 Mini |
| **OpenAI** | ✅ GPT-4o (limited) | ❌ Permanent free | ❌ GPT-OSS via NIM | GPT-4o Mini, GPT-4o |
| **Anthropic** | ✅ Claude Sonnet | ❌ No free API | ❌ | Claude Sonnet 4.6 |
| **NVIDIA NIM** | ❌ | ✅ Free (phone verify) | ✅ Many models | DeepSeek R1, Llama 4 |
| **Groq** | ❌ | ✅ Free (rate-limited) | Via Groq hardware | Llama 4, Gemma 3, Mistral |
| **Cerebras** | ❌ | ✅ 1M tok/day free | Via Cerebras hardware | Llama 4 Scout, Qwen3 32B |
| **OpenRouter** | ❌ | ✅ 29+ free models | Via aggregation | DeepSeek V3, Llama 3.3 70B |
| **Cloudflare** | ❌ | ✅ 10K neurons/day | Via Workers AI | DeepSeek R1 Distill, Llama models |
| **GitHub Models** | ❌ | ✅ Free with GitHub | ❌ | GPT-4o, Grok 3, Llama 4 |

---

## 3. Provider Deep-Dives & Model Rankings

---

### 3.1 Google — Gemini & Gemma

Google offers the **most generous permanent free API tier** among major providers, with no credit card required and no expiry. Access via [aistudio.google.com](https://aistudio.google.com).

**Headquarters:** Mountain View, CA, USA
**Infrastructure:** Google TPU clusters
**Signup:** Email / Google account, no credit card required

Google AI Studio remains the most generous free tier for sustained, long-running access. It provides developer access to Google's latest stable Gemini models with a 1M token context window — identical in quality to the paid tier. The only trade-off on the free tier is that Google may use prompt data to improve models; this is not the case on paid or Vertex AI.

#### Free Models Available

| Model | Context Window | Multimodal | Reasoning | Free API Limits |
|---|---|---|---|---|
| **Gemini 2.5 Flash** | 1,000,000 tokens | ✅ Text, Image, Audio, Video | ✅ Thinking mode | 15 RPM, 1,500 RPD |
| **Gemini 2.5 Flash Lite** | 1,000,000 tokens | ✅ Text, Image, Audio, Video | ✅ (lighter) | Higher RPM than Flash |
| **Gemini 2.0 Flash** | 1,000,000 tokens | ✅ Text, Image, Audio, Video | ✅ | 15 RPM, 1M TPM |
| **Gemini 2.0 Flash Lite** | 1,000,000 tokens | ✅ Text, Image | ❌ | Highest RPM of all |
| **Gemma 3 27B** | 128,000 tokens | ✅ Text + Image | ❌ | Self-hosted or via NIM |
| **Gemma 3 12B** | 128,000 tokens | ✅ Text + Image | ❌ | RTX 3060+ (8GB VRAM) |

**Note:** Gemini 2.5 Pro was briefly available on the free tier with a 50 RPD cap but was restricted to paid tiers as of April 2026. Gemini 3.1 Pro (preview) is currently paid-only.

#### Rankings Within Provider

| Category | Rank 1 | Rank 2 | Rank 3 |
|---|---|---|---|
| Coding | Gemini 2.5 Flash | Gemini 2.0 Flash | Gemma 3 27B |
| Reasoning | Gemini 2.5 Flash | Gemini 2.5 Flash Lite | Gemini 2.0 Flash |
| Speed | Gemini 2.0 Flash Lite | Gemini 2.5 Flash Lite | Gemini 2.0 Flash |
| Context | All Gemini 2.x models (tied 1M) | Gemma 3 27B (128K) | — |
| Multimodal | Gemini 2.5 Flash | Gemini 2.0 Flash | Gemma 3 27B |

**⭐ Standout: Gemini 2.5 Flash**  
- 1M token context at **zero cost** — unmatched in the free tier  
- Supports text, images, audio, and video input  
- Includes controllable "thinking mode" for harder reasoning  
- Best free model for document analysis, multimodal tasks, long-context work

**Strengths:** Massive free context window; multimodal; permanent free tier; no credit card  
**Weaknesses:** Rate limits (15 RPM) can bottleneck high-volume apps; slower than Groq/Cerebras; Google may use free-tier data for model training

---

### 3.2 Meta — Llama 4 (via Groq, Cerebras, OpenRouter)

Meta's Llama 4 family is open-source and available through many free inference providers.

#### Free Models Available

| Model | Parameters | Context Window | Best For | Where Free |
|---|---|---|---|---|
| **Llama 4 Scout** | ~17B active (MoE) | 10,000,000 tokens | Long-context tasks, documents | Groq, Cerebras, OpenRouter |
| **Llama 4 Maverick** | ~17B active (MoE) | 1,000,000 tokens | Reasoning, coding | Groq (500 RPD), OpenRouter |
| **Llama 3.3 70B** | 70B | 128,000 tokens | Balanced performance | Groq, OpenRouter |
| **Llama 3.2 3B / 11B** | 3B–11B | 128,000 tokens | Fast lightweight tasks | Groq, OpenRouter, many |

#### Rankings Within Provider

| Category | Rank 1 | Rank 2 |
|---|---|---|
| Coding | Llama 4 Maverick | Llama 3.3 70B |
| Reasoning | Llama 4 Maverick | Llama 3.3 70B |
| Context Length | Llama 4 Scout (10M!) | Llama 4 Maverick (1M) |
| Speed | Llama 3.2 3B on Cerebras | Llama 4 Scout on Groq |
| General Use | Llama 4 Maverick | Llama 3.3 70B |

**⭐ Standout: Llama 4 Scout**  
- **10 million token context window** — the largest of any model available free  
- Ideal for ingesting entire codebases, books, or large datasets  
- Available on Groq and Cerebras at no cost

**Strengths:** Massive ecosystem; huge community; Apache 2.0 license; runs locally  
**Weaknesses:** Slightly behind frontier models on raw benchmark scores; Maverick is rate-limited on Groq (500 RPD)

---

### 3.3 DeepSeek — V3 / R1 (via OpenRouter, NVIDIA NIM)

DeepSeek models punch far above their weight class and are available free through several providers.

#### Free Models Available

| Model | Parameters | Context Window | Best For | Where Free |
|---|---|---|---|---|
| **DeepSeek R1** | 671B MoE | 128,000 tokens | Advanced reasoning, math | OpenRouter (:free), NVIDIA NIM, Cloudflare |
| **DeepSeek V3** | 671B MoE | 128,000 tokens | Coding, general tasks | OpenRouter (:free), NVIDIA NIM |
| **DeepSeek R1 Distill Qwen 32B** | 32B | 128,000 tokens | Fast reasoning | Groq, Cloudflare Workers AI |
| **DeepSeek R1 Distill Llama 70B** | 70B | 128,000 tokens | High-quality reasoning | OpenRouter (:free) |

#### Rankings Within Provider

| Category | Rank 1 | Rank 2 |
|---|---|---|
| Coding | DeepSeek V3 | DeepSeek R1 |
| Reasoning | DeepSeek R1 | DeepSeek R1 Distill Llama 70B |
| Debugging | DeepSeek R1 | DeepSeek V3 |
| Speed | R1 Distill Qwen 32B (on Groq) | DeepSeek V3 |

**⭐ Standout: DeepSeek R1**  
- Reasoning performance comparable to OpenAI o1 on math, code, and logic  
- Available free via OpenRouter (:free suffix) and NVIDIA NIM  
- MIT licensed — can be used in commercial products

**Strengths:** World-class reasoning; MIT license; strong coding; free via aggregators  
**Weaknesses:** Data privacy concerns (servers in China); context window smaller than Gemini (128K vs 1M); free tiers can be slow during peak traffic

---

### 3.4 Mistral AI — Mistral & Devstral (free tier)

Mistral offers a free API tier (rate-limited) and a free chat interface at le Chat.

**Headquarters:** Paris, France
**Infrastructure:** GPU clusters (European data centers)
**Signup:** Phone verification required, no credit card

Mistral's free "Experiment" plan is one of the broadest in terms of model access — all Mistral models including Mistral Large and Codestral are available. The 1 billion tokens per month allowance is generous for prototyping, but the 2 RPM cap makes it unsuitable for real-time or interactive applications. Data may be used for model improvement on the free tier.

#### Free Models Available

| Model | Parameters | Context Window | Best For | Free Access |
|---|---|---|---|---|
| **Devstral** | ~24B | 128,000 tokens | Agentic coding | OpenRouter (:free), Mistral API |
| **Mistral Small** | ~24B | 128,000 tokens | Efficient general tasks | Mistral free API |
| **Mistral Small 3.1** | ~22B | 128,000 tokens | Efficient general tasks | Mistral free API |
| **Mistral 7B** | 7B | 32,000 tokens | Lightweight, fast | OpenRouter, many |
| **Codestral** | ~22B | 256,000 tokens | Code generation | le Chat (limited), Mistral API |
| **Mistral Nemo** | 12B | 128,000 tokens | General tasks | Mistral API |
| **Mistral Large (latest)** | ~123B | 128,000 tokens | Broad tasks | Mistral API |
| **Pixtral 12B** | 12B | 128,000 tokens | Multimodal (text + image) | Mistral API |
| **Mistral Embed** | — | 8K tokens | Embeddings | Mistral API |

#### Rankings Within Provider

| Category | Rank 1 | Rank 2 |
|---|---|---|
| Coding | Devstral | Codestral |
| Reasoning | Mistral Small | Devstral |
| Speed | Mistral 7B | Mistral Small |
| General | Mistral Small | Devstral |

**⭐ Standout: Devstral**  
- Purpose-built for agentic coding workflows (multi-file edits, tool use)  
- Apache 2.0 license — commercially usable  
- Available free on OpenRouter

**Strengths:** Coding-specialized models; clean Apache 2.0 licensing; European data residency option; 1B tokens/month  
**Weaknesses:** Free Mistral API limits are tighter than Google's (2 RPM cap); Devstral not as strong on reasoning tasks outside code

---

### 3.5 Alibaba / Qwen — Qwen3 Family

Qwen3 models are open-weight and available via OpenRouter free tier and self-hosting.

#### Free Models Available

| Model | Parameters | Context Window | Best For | Free Access |
|---|---|---|---|---|
| **Qwen3 235B A22B** | 235B MoE (22B active) | 128,000 tokens | All-around top performance | OpenRouter (:free), self-host |
| **Qwen3 32B** | 32B | 128,000 tokens | Balanced performance | Cerebras, OpenRouter |
| **Qwen3-Coder** | 32B | 128,000 tokens | Code generation | OpenRouter (:free) |
| **Qwen3 8B** | 8B | 128,000 tokens | Fast tasks, local use | Ollama, OpenRouter |

#### Rankings Within Provider

| Category | Rank 1 | Rank 2 |
|---|---|---|
| Coding | Qwen3-Coder | Qwen3 235B |
| Reasoning | Qwen3 235B | Qwen3 32B |
| Speed | Qwen3 8B | Qwen3 32B on Cerebras |
| General / Multilingual | Qwen3 235B | Qwen3 32B |

**⭐ Standout: Qwen3 235B A22B**  
- #1 model on OpenRouter by token volume  
- Competes with frontier closed models at zero API cost  
- Exceptional multilingual performance (100+ languages)

**Strengths:** Huge model variety; multilingual; top OpenRouter free model by usage  
**Weaknesses:** Largest models require significant hardware for self-hosting; OpenRouter free tier may deprioritize during peak hours

---

### 3.6 xAI — Grok (via GitHub Models)

Grok 3 and Grok 3 Mini are available free via GitHub Models, tied to your GitHub/Copilot account tier.

#### Free Models Available

| Model | Context Window | Best For | Free Access |
|---|---|---|---|
| **Grok 3** | 131,000 tokens | Reasoning, analysis, real-time data | GitHub Models |
| **Grok 3 Mini** | 131,000 tokens | Fast reasoning, lower cost | GitHub Models |

**⭐ Standout: Grok 3**  
- Access to real-time X/Twitter data and current events  
- Strong reasoning performance

**Strengths:** Real-time data; strong reasoning; fewer content restrictions than some competitors  
**Weaknesses:** Free access only via GitHub Models (requires account); no permanent standalone free API; xAI's $25 signup credit is one-time and not a true free tier; several older Grok models retired in May 2026

---

### 3.7 OpenAI — GPT-4o / GPT-4o Mini (chat free tier)

OpenAI's free tier is **chat-only** (no permanent free API). The API offers only one-time credits.

#### Free Models Available (Chat Only)

| Model | Context | Best For | Free Access |
|---|---|---|---|
| **GPT-4o** | 128,000 tokens | Broad capability, vision | ChatGPT free (limited msgs) |
| **GPT-4o Mini** | 128,000 tokens | Fast everyday tasks | ChatGPT free (default) |
| **GPT-5** | 128,000 tokens | Frontier reasoning, coding | GitHub Models |
| **GPT-4.1** | 128,000 tokens | Strong all-rounder | GitHub Models |
| **GPT-OSS 120B** | 128,000 tokens | Open-weight GPT quality | Groq, Cerebras, NVIDIA NIM |
| **GPT-OSS 20B** | 128,000 tokens | Lighter GPT-class tasks | Groq, Cerebras, Cloudflare |

**Note:** GPT-4o Mini is the **default** free chat model. GPT-4o access is available but message-limited. GitHub Models provides free API access to GPT-4o, GPT-4.1, and GPT-5.

**Strengths:** Broadest feature set (vision, code interpreter, image gen, web search) in the free chat interface  
**Weaknesses:** Most aggressive rate limiting among chat free tiers; no permanent free API (the one-time $5 API credit expires)

---

### 3.8 Anthropic — Claude Sonnet (chat free tier)

Anthropic offers a **chat-only free tier** — there is no permanent free Claude API.

#### Free Models Available (Chat Only)

| Model | Context | Best For | Free Access |
|---|---|---|---|
| **Claude Sonnet 4.6** | 200,000 tokens | Long-form reasoning, analysis, coding | claude.ai free (message-limited) |

**Note:** The free tier uses Claude Sonnet (mid-tier model), not Claude Haiku. Message limits are stricter than Gemini but the model quality per message is higher than most chat free tiers.

**Strengths:** 200K context even on free tier; high model quality; best free option for analyzing long documents  
**Weaknesses:** Strictest daily message limits among major chat free tiers; no free API tier; messages adjust based on server load

---

### 3.9 NVIDIA NIM — Free Hosted Models

NVIDIA NIM provides free access to 90+ open-source models (phone verification required).

**Headquarters:** Santa Clara, CA, USA
**Infrastructure:** NVIDIA H100/H200 GPU clusters
**Signup:** Phone verification required, no credit card

NVIDIA NIM hosts 91+ AI models for free with an unusually generous 40 RPM rate limit and no stated daily token cap. This makes it especially valuable for sustained workloads. It is fully OpenAI API-compatible and does not restrict model use to NVIDIA hardware on the client side.

#### Notable Free Models

| Model | Context | Type |
|---|---|---|
| DeepSeek R1 | 128K | Reasoning |
| DeepSeek V3 | 64K | General/Coding |
| Llama 4 Scout | 10M | Long-context |
| Llama 4 Maverick | 1M | Reasoning/Coding |
| Llama 3.3 70B | 128K | Reliable all-rounder |
| Qwen3 235B | 32K | Largest open MoE |
| Gemma 3 27B | 128K | General |
| Mistral Large | 128K | European compliance |
| Mistral Small | 128K | Efficient general |
| Nemotron 70B | 128K | NVIDIA-optimized |
| GPT-OSS 120B | 128K | GPT-class quality |

**Strengths:** Massive model selection (90+); 40 RPM with no hard daily token cap; domain-specialized models; OpenAI-compatible API; no data training  
**Weaknesses:** Phone verification required; rate limits not publicly documented; not available in all regions

---

### 3.10 Groq — Speed-Optimized Free API

Groq uses custom Language Processing Units (LPUs) for dramatically faster inference than GPU-based providers.

**Headquarters:** Sunnyvale, CA, USA
**Infrastructure:** Proprietary LPU (Language Processing Unit) chips
**Signup:** Email / Google / GitHub, no credit card required

Groq's core selling point is raw inference speed — 300–1,000 tokens per second depending on model size — achieved through custom LPU hardware. The free tier provides access to every model Groq hosts with rate limits as the only constraint. It is fully OpenAI SDK-compatible, making it a drop-in replacement. Groq does not train on user data.

#### Free Models & Rate Limits

| Model | RPM | RPD | TPM | TPD |
|---|---|---|---|---|
| **Llama 4 Scout** | 30 | 1,000 | 6,000 | — |
| **Llama 4 Maverick** | 15 | 500 | 3,000 | — |
| **Llama 3.3 70B** | 30 | 1,000 | 6,000 | 100,000 |
| **Llama 3.1 8B** | 30 | 14,400 | 20,000 | — |
| **Gemma 3 27B** | 30 | 14,400 | — | — |
| **Gemma 2 9B** | 30 | 14,400 | 15,000 | — |
| **DeepSeek R1 Distill 70B** | 30 | 1,000 | 6,000 | — |
| **DeepSeek R1 Distill 32B** | 30 | 1,000 | 6,000 | — |
| **Qwen QwQ 32B** | 30 | 1,000 | 6,000 | — |
| **Mistral Small** | 30 | 14,400 | — | — |
| **Mistral Saba 24B** | 30 | 1,000 | 6,000 | — |
| **GPT-OSS 120B / 20B** | Varies | Varies | — | — |
| **Whisper (large-v3)** | 20 | 2,000 | — | — |

*RPM = Requests Per Minute, RPD = Requests Per Day, TPM = Tokens Per Minute, TPD = Tokens Per Day*

**⭐ Standout:** Groq delivers **sub-second first-token latency** for most models — up to 315 tokens/second on its LPU hardware. This is 5–20x faster than GPU-based providers for the same model.

**Strengths:** Fastest free inference available; no credit card; all models accessible on free tier; OpenAI SDK-compatible; no data training  
**Weaknesses:** Tighter RPD limits (1,000 for most models); not suitable for high-volume production without upgrade; open-source models only (no GPT, Gemini, Claude)

---

### 3.11 Cerebras — Ultra-Fast Free API

Cerebras uses wafer-scale chips delivering **2,600+ tokens/second** — the fastest inference available publicly.

**Headquarters:** Sunnyvale, CA, USA
**Infrastructure:** Wafer-Scale Engine (WSE) chips — custom AI silicon
**Signup:** Email, no credit card required

Cerebras is the **speed champion** of free cloud inference in 2026, delivering 2,600+ tokens per second on its wafer-scale chips — roughly 20× faster than standard GPU providers. The free tier provides 1 million tokens per day with a daily reset. It is OpenAI SDK-compatible. Cerebras does not train on user data. The main limitation is a restricted model catalog (Llama family and a few others) with an 8,192-token context cap on the free tier.

#### Free Models & Limits

| Model | Context | RPM | Free Daily Limit | Speed |
|---|---|---|---|---|
| **Llama 4 Scout** | 10,000,000 tokens* | 30 | 1M tokens/day | 2,600+ tok/s |
| **Qwen3 32B** | 32,000 tokens | 30 | 1M tokens/day | 2,600+ tok/s |
| **Llama 3.3 70B** | 8,000 tokens† | 30 | 1M tokens/day | ~2,200 tok/s |
| **Llama 3.1 70B** | 8,000 tokens† | 30 | 1M tokens/day | ~2,000 tok/s |
| **DeepSeek R1 Distill 70B** | 8,000 tokens† | 30 | 1M tokens/day | ~1,800 tok/s |
| **GPT-OSS 120B** | 8,000 tokens† | 30 | 1M tokens/day | ~1,500 tok/s |

> *Llama 4 Scout's full 10M context may be capped at 8K on the free tier. †Free tier context cap is 8,192 tokens for most models. TPM cap: 60,000.

**⭐ Standout:** 1 million tokens/day free — the **most generous daily token volume** of any free API provider. Combined with 2,600+ tokens/second speed, Cerebras is ideal for high-volume personal/prototype workloads.

**Strengths:** Highest daily free token volume; fastest inference speed publicly available; no credit card; OpenAI SDK-compatible; no data training  
**Weaknesses:** 8K context cap on free tier is a major limitation; limited model selection compared to OpenRouter or NVIDIA NIM; best for throughput, not variety

---

### 3.12 OpenRouter — Aggregated Free Models

OpenRouter provides a unified API key for 200+ models, with 29+ permanently free (marked with `:free` suffix).

**Headquarters:** San Francisco, CA, USA
**Infrastructure:** API gateway / aggregator (routes to multiple providers)
**Signup:** Email / GitHub, no credit card required

OpenRouter is not an inference provider itself — it is a unified API gateway that aggregates 200+ models from multiple providers under a single OpenAI-compatible endpoint. Free models are community-subsidized and are marked with a `:free` suffix. The free tier gives 50 requests per day without an account balance (upgrades to 1,000/day with $10+ balance). Free requests are deprioritized during peak traffic, leading to variable latency.

#### Notable Free Models on OpenRouter

| Model ID | What It Is |
|---|---|
| `deepseek/deepseek-r1:free` | DeepSeek R1 671B (64K context) |
| `deepseek/deepseek-v3:free` | DeepSeek V3 671B (64K context) |
| `meta-llama/llama-4-scout:free` | Llama 4 Scout (10M context) |
| `meta-llama/llama-4-maverick:free` | Llama 4 Maverick (1M context) |
| `meta-llama/llama-3.3-70b-instruct:free` | Llama 3.3 70B (128K context) |
| `qwen/qwen3-235b-a22b:free` | Qwen3 235B (32K context, best overall) |
| `qwen/qwen3-coder:free` | Qwen3 Coder (32K context) |
| `mistralai/devstral:free` | Devstral (128K context, agentic coding) |
| `google/gemma-3-27b-it:free` | Gemma 3 27B (128K context) |
| `microsoft/phi-4:free` | Microsoft Phi-4 |
| `openai/gpt-oss-120b:free` | GPT-OSS 120B (128K context) |

**Strengths:** Single API key for dozens of free models; easy model comparison/switching; no credit card; includes frontier-class models (Qwen3 235B, DeepSeek R1, GPT-OSS 120B)  
**Weaknesses:** Free requests deprioritized during peak hours (latency spikes 30–60+ seconds); availability can change without notice; only 50 requests/day without a paid balance ($10+ = 1,000/day); 20 RPM

---

### 3.13 Cloudflare Workers AI

Cloudflare provides 10,000 free "Neurons" per day (a compute unit) with no credit card.

**Headquarters:** San Francisco, CA, USA
**Infrastructure:** Global edge network (250+ cities)
**Signup:** Cloudflare account, no credit card

Cloudflare Workers AI runs models at the network edge, giving the lowest latency for geographically distributed applications. The free tier provides 10,000 Neurons per day (a compute unit, not tokens). Model selection is more limited than other providers. Best for applications already built on Cloudflare's developer stack.

#### Notable Free Models

| Model | Type |
|---|---|
| DeepSeek R1 Distill Qwen 32B | Reasoning |
| Llama 4 Scout / Maverick | General |
| Llama 3.3 70B | Edge-deployed (8K context) |
| Llama 3.1 8B | Fastest on edge (8K context) |
| GPT-OSS family (20B) | OpenAI-class (8K context) |
| Gemma 3 12B / 27B | General, multimodal |
| Mistral 7B | European GDPR-friendly |
| FLUX.1 Schnell | Image generation |
| Stable Diffusion XL | Image generation |
| Whisper | Speech-to-text |

**Strengths:** Edge-deployed (low latency if near a Cloudflare datacenter); includes image models; no credit card; GDPR-compliant, no data training  
**Weaknesses:** 8K context cap on most models; 10K neurons/day = ~200–500 requests for medium models; limited model catalog vs. other providers; not suitable for compute-heavy tasks

---

### 3.14 GitHub Models

GitHub Models provides free API access to 100+ models, with rate limits tied to your GitHub Copilot subscription.

**Headquarters:** Microsoft / GitHub (San Francisco, CA)
**Infrastructure:** Azure AI infrastructure
**Signup:** Any GitHub account (free), no credit card

GitHub Models offers free API access to frontier models including GPT-5, GPT-4.1, GPT-4o, and Phi-4 — no OpenAI subscription needed. Rate limits are tied to your GitHub Copilot tier. Free GitHub users get lower limits (8K input / 4K output per request, ~50 requests/day equivalent); Copilot Individual or Business users get higher limits. This is the only free way to access GPT-5 and GPT-4 class OpenAI models via API.

#### Notable Free Models

| Model | Provider | Context | Notes |
|---|---|---|---|
| GPT-5 | OpenAI | 128K tokens | Best free GPT model; frontier reasoning |
| GPT-4.1 | OpenAI | 128K tokens | Free (rate-limited) |
| GPT-4o | OpenAI | 128K tokens | Free with GitHub account; multimodal |
| o4-mini | OpenAI | — | Reasoning, free tier |
| Phi-4 Reasoning | Microsoft | 16K tokens | Strong small reasoning |
| Grok 3 | xAI | 131K tokens | Free with GitHub |
| Grok 3 Mini | xAI | 131K tokens | Free with GitHub |
| Llama 4 Scout/Maverick | Meta | 10M/1M tokens | Free with GitHub |
| Mistral Large | Mistral | 128K tokens | European model |
| DeepSeek V3 | DeepSeek | 64K tokens | Strong coder |

**Strengths:** Access to frontier models (GPT-5, o4-mini, Grok 3) without separate API accounts; GitHub-integrated; good for developers already using Copilot  
**Weaknesses:** Very low rate limits (50 req/day for free GitHub users); 8K input / 4K output per request cap; not suitable for production; limits tied to Copilot tier

---

### Hugging Face (Serverless Inference API)

**Headquarters:** New York, NY, USA
**Infrastructure:** Multi-provider routing (Groq, Together AI, Fireworks, Cerebras, etc.)
**Signup:** Email, no credit card

Hugging Face's Serverless Inference API offers access to 200,000+ models in theory, but the free tier practically limits you to models under ~10B parameters with strict rate caps. The Inference Providers feature routes to 15+ third-party backends (including Groq, Cerebras, Together AI). Free users get 100K monthly Inference Provider credits. HuggingFace PRO ($9/month) unlocks significantly higher limits.

**Free Tier Highlights:**
- Access to thousands of models (practical: smaller open-weight models)
- 100K monthly credits for Inference Providers (routes to Groq, Cerebras, etc.)
- Cold starts can take 30+ seconds on free tier
- Best for: Model discovery, research prototyping, embedding generation

---

### Cohere

**Headquarters:** Toronto, Canada
**Infrastructure:** GPU clusters
**Signup:** Email, no credit card

Cohere's free tier is purpose-built for retrieval-augmented generation (RAG) pipelines. The combination of Command R+ for generation, Embed 4 for vector embeddings, and Rerank 3.5 for result re-ranking covers the full RAG stack at zero cost. Particularly strong for enterprise document Q&A and search applications.

**Free Models (as of June 2026):**

| Model | Context | Notes |
|---|---|---|
| Command R+ | 128K tokens | Best free RAG model |
| Command R | 128K tokens | Lighter RAG option |
| Embed 4 | 512 tokens | Multilingual embeddings |
| Rerank 3.5 | — | Result re-ranking |
| Aya Expanse 32B | 128K tokens | Multilingual generation |

---

## 4. Cross-Provider Rankings by Category

---

### 4.1 Best for Coding

Ranked by SWE-Bench Verified, LiveCodeBench, and real-world coding workflow performance.

| Rank | Model | Provider/Access | SWE-Bench Est. | LiveCodeBench | Notes |
|---|---|---|---|---|---|
| 🥇 1 | **DeepSeek V3** | OpenRouter :free, NVIDIA NIM | ~80%+ | High | Best free coding model; MIT license |
| 🥈 2 | **Qwen3-Coder** | OpenRouter :free | ~79% | Very High | Optimized specifically for code |
| 🥉 3 | **Devstral** | OpenRouter :free, Mistral API | ~78% | High | Best for agentic multi-file coding |
| 4 | **Gemini 2.5 Flash** | Google AI Studio | ~77% | High | Best multimodal coding; 1M context |
| 5 | **Qwen3 235B** | OpenRouter :free | ~76% | High | Best all-around open-weight model |
| 6 | **Llama 4 Maverick** | Groq, OpenRouter | ~72% | Good | Best Llama model for coding |
| 7 | **DeepSeek R1** | OpenRouter :free, NVIDIA NIM | ~70% | Good | Reasoning approach to code |
| 8 | **GPT-4o** | ChatGPT free, GitHub Models | ~74% | Good | Strong but rate-limited free access |
| 9 | **Llama 3.3 70B** | Groq, OpenRouter | ~65% | Good | Fast on Groq; solid everyday coding |
| 10 | **Claude Sonnet 4.6** | claude.ai (chat only) | ~75% | Good | Best chat-only coding assistant |

### Coding Benchmarks (Detailed)

| Model | SWE-Bench Verified | HumanEval | Notes |
|---|---|---|---|
| GPT-5 (GitHub Models) | ~74.9% | ~97%+ | Best free GPT model |
| DeepSeek V3 / R1 | ~80.6% (V4 Pro, similar arch) | ~96% | Best free coding |
| Llama 4 Maverick | ~62–65% (est.) | ~92% | Strong open model |
| Qwen3 235B | ~68% (est.) | ~94% | Top open MoE |
| Codestral (Mistral) | ~55–60% (est.) | ~91% | Code-specialized |
| Gemini 2.5 Flash | ~70–72% (est.) | ~93% | Best multimodal coder |
| Llama 3.3 70B | ~53% (est.) | ~89% | Solid baseline |
| GPT-OSS 120B | ~60–65% (est.) | ~91% | GPT-class open |
| Qwen QwQ 32B | ~58% (est.) | ~92% | Strong reasoning |

---

### 4.2 Best for Reasoning

Ranked by GPQA Diamond, HLE, and multi-step logical inference performance.

| Rank | Model | Provider/Access | GPQA Diamond | HLE Score | Notes |
|---|---|---|---|---|---|
| 🥇 1 | **DeepSeek R1** | OpenRouter :free, NVIDIA NIM | ~71% | High | Best free reasoning model overall |
| 🥈 2 | **Gemini 2.5 Flash** | Google AI Studio | ~70% | High | Thinking mode enables deep reasoning |
| 🥉 3 | **Qwen3 235B (Thinking)** | OpenRouter :free | ~69% | High | Thinking mode available |
| 4 | **Grok 3** | GitHub Models | ~66% | Good | Strong logical deduction |
| 5 | **DeepSeek R1 Distill Llama 70B** | OpenRouter :free | ~64% | Good | Smaller but strong reasoning |
| 6 | **Llama 4 Maverick** | Groq, OpenRouter | ~62% | Good | Best Llama for reasoning |
| 7 | **Claude Sonnet 4.6** | claude.ai (chat only) | ~65% | High | Best chat-only reasoning |
| 8 | **GPT-4o** | ChatGPT free (limited) | ~60% | Good | Solid but limited free access |
| 9 | **Qwen3 32B (Thinking)** | Cerebras | ~60% | Good | Fast + thinking on Cerebras |
| 10 | **Mistral Small** | Mistral API (free) | ~55% | Moderate | Best for efficient reasoning tasks |

### Reasoning Benchmarks (Detailed)

| Model | GPQA Diamond | AIME 2025 | Reasoning Style |
|---|---|---|---|
| DeepSeek R1 Distill 70B | ~73% | ~80% | Chain-of-thought |
| Qwen QwQ 32B | ~71% | ~79% | Chain-of-thought |
| GPT-5 (GitHub Models) | ~76% | ~83% | Structured |
| Gemini 2.5 Flash | ~72% | ~81% | Thinking mode |
| Llama 4 Maverick | ~57% | ~67% | Standard |
| Llama 3.3 70B | ~51% | ~59% | Standard |

---

### 4.3 Best for Debugging

Debugging requires reasoning over code context, understanding error messages, and proposing targeted fixes.

| Rank | Model | Best Access | Strength |
|---|---|---|---|
| 🥇 1 | **DeepSeek R1** | OpenRouter :free | Traces logic step-by-step through errors |
| 🥈 2 | **Gemini 2.5 Flash** | Google AI Studio | 1M context = entire codebase + logs |
| 🥉 3 | **DeepSeek V3** | OpenRouter :free | Fast, precise code fixes |
| 4 | **Claude Sonnet 4.6** | claude.ai (chat only) | Excellent error explanation; 200K context |
| 5 | **Qwen3-Coder** | OpenRouter :free | Optimized for code understanding |
| 6 | **Devstral** | OpenRouter :free | Multi-file debugging via agentic approach |
| 7 | **Llama 4 Scout** | Groq, Cerebras | 10M context = full project ingestion |
| 8 | **GPT-4o** | ChatGPT free (limited) | Strong at interpreting stack traces |
| 9 | **Llama 3.3 70B** | Groq | Fast turnaround on Groq hardware |
| 10 | **Qwen3 32B** | Cerebras | 1M tokens/day free; good reasoning |

---

### 4.4 Fastest Models (Speed)

Ranked by tokens/second and time to first token.

| Rank | Model | Platform | Speed | Notes |
|---|---|---|---|---|
| 🥇 1 | **Llama 4 Scout / Qwen3 32B** | **Cerebras** | 2,600+ tok/s | Wafer-scale chips; fastest available |
| 🥈 2 | **Llama 4 Scout / Llama 3.3 70B** | **Groq** | ~315–394 tok/s | LPU hardware; sub-second TTFT |
| 🥉 3 | **DeepSeek R1 Distill 32B** | **Groq** | ~250 tok/s | Fast reasoning via Groq LPUs |
| 4 | **Gemini 2.0 Flash Lite** | Google AI Studio | ~150 tok/s | Best speed/quality for multimodal |
| 5 | **GPT-4o Mini** | ChatGPT free | ~100 tok/s | Fast for a frontier-class model |
| 6 | **Mistral 7B** | Groq/OpenRouter | ~200 tok/s | Tiny and fast |
| 7 | **Gemini 2.5 Flash Lite** | Google AI Studio | ~120 tok/s | Faster than full Flash |
| 8 | **Qwen3 8B** | Ollama (local) | Depends on GPU | ~200 tok/s on RTX 4090 |
| 9 | **Gemma 3 12B** | Local (Ollama) | ~80–150 tok/s | Runs on 8GB VRAM |
| 10 | **GPT-OSS 20B** | Cerebras/Groq | ~200 tok/s | Fast GPT-class open model |

### Speed / Latency (Detailed Tokens Per Second)

| Provider | Model | Tokens/Sec | TTFT (avg) | Best For |
|---|---|---|---|---|
| Cerebras | All models | 2,600+ | <50ms | Real-time, agentic |
| Groq | Llama 3.1 8B | ~800 | <100ms | Chat, fast response |
| Groq | Llama 3.3 70B | ~394 | <150ms | Balanced |
| Groq | DeepSeek R1 70B | ~315 | <200ms | Reasoning |
| NVIDIA NIM | Llama 4 Scout | ~200 | <300ms | Long-context |
| Google AI Studio | Gemini 2.5 Flash | ~150–200 | ~300ms | Multimodal |
| OpenRouter (:free) | Various | ~50–200 | 2–60s | Variable |
| Mistral | All models | ~80–150 | ~500ms | Batch tasks |
| Cloudflare | Llama 3.1 8B | ~100–200 | <200ms | Edge latency |

---

### 4.5 Longest Context Window

| Rank | Model | Context Window | Free Access |
|---|---|---|---|
| 🥇 1 | **Llama 4 Scout** | **10,000,000 tokens** | Groq, Cerebras, OpenRouter, NVIDIA NIM |
| 🥈 2 | **Gemini 2.5 Flash / 2.0 Flash** | **1,000,000 tokens** | Google AI Studio (free) |
| 🥉 3 | **Gemini 2.5 Flash Lite** | **1,000,000 tokens** | Google AI Studio (free) |
| 4 | **Llama 4 Maverick** | 1,000,000 tokens | Groq (500 RPD), OpenRouter, NVIDIA NIM |
| 5 | **Codestral** | 256,000 tokens | Mistral (le Chat) |
| 6 | **Claude Sonnet 4.6** | 200,000 tokens | claude.ai (chat only) |
| 7 | **Gemma 3 27B / 12B** | 128,000 tokens | Ollama, NVIDIA NIM |
| 8 | **DeepSeek R1 / V3** | 128,000 tokens | OpenRouter :free, NIM |
| 9 | **Qwen3 models** | 128,000 tokens | OpenRouter :free, Cerebras |
| 10 | **GPT-4o / Grok 3 / GPT-5** | 128,000 tokens | ChatGPT free / GitHub Models |

*Cerebras Llama 4 Scout context may be capped at 8K on free tier despite the model's 10M capability.

---

### 4.6 Best Multimodal Capabilities

Supports inputs beyond text (images, audio, video, PDFs).

| Rank | Model | Modalities Supported | Free Access | Notes |
|---|---|---|---|---|
| 🥇 1 | **Gemini 2.5 Flash** | Text, Image, Audio, Video, PDF | Google AI Studio (free) | Best free multimodal model |
| 🥈 2 | **Gemini 2.0 Flash** | Text, Image, Audio, Video | Google AI Studio (free) | Slightly older but same inputs |
| 🥉 3 | **Gemini 2.5 Flash Lite** | Text, Image, Audio, Video | Google AI Studio (free) | Faster, lighter version |
| 4 | **GPT-4o** | Text, Image, PDF | ChatGPT free (limited), GitHub Models | Includes code interpreter |
| 5 | **GPT-5** | Text, Image | GitHub Models | Frontier multimodal |
| 6 | **Gemma 3 27B** | Text, Image | NVIDIA NIM, Ollama | Open-source multimodal |
| 7 | **Llama 4 Scout/Maverick** | Text, Image | Groq, Cerebras, OpenRouter | Limited vs Gemini |
| 8 | **Grok 3** | Text, Image | GitHub Models | Via X API integration |
| 9 | **Claude Sonnet 4.6** | Text, Image, PDF | claude.ai (chat only) | Strong at document analysis |
| 10 | **Qwen3 235B** | Text + limited image | OpenRouter :free | Image support via specific API |
| 11 | **Pixtral 12B** | Text, Image | Mistral | Open multimodal |
| 12 | **Cloudflare FLUX** | → Image generation | Cloudflare Workers AI | Free image generation |

---

### 4.7 Best Overall Performance

Composite ranking across coding, reasoning, context, speed, and multimodal capabilities on the **free tier**.

| Rank | Model | Free Access | Overall Score | Best Single Strength |
|---|---|---|---|---|
| 🥇 1 | **Gemini 2.5 Flash** | Google AI Studio | ⭐⭐⭐⭐⭐ | 1M context + multimodal + reasoning |
| 🥈 2 | **DeepSeek R1** | OpenRouter :free / NVIDIA NIM | ⭐⭐⭐⭐½ | Best free reasoning model |
| 🥉 3 | **DeepSeek V3** | OpenRouter :free / NVIDIA NIM | ⭐⭐⭐⭐½ | Best free coding model |
| 4 | **Qwen3 235B** | OpenRouter :free | ⭐⭐⭐⭐ | Top open-weight all-rounder |
| 5 | **Llama 4 Scout** | Groq / Cerebras / NVIDIA NIM | ⭐⭐⭐⭐ | World's largest free context window |
| 6 | **Devstral** | OpenRouter :free | ⭐⭐⭐⭐ | Best agentic coding |
| 7 | **Qwen3-Coder** | OpenRouter :free | ⭐⭐⭐½ | Best specialized coding |
| 8 | **Claude Sonnet 4.6** | claude.ai (chat only) | ⭐⭐⭐⭐ | Best free chat quality |
| 9 | **Llama 4 Maverick** | Groq / OpenRouter | ⭐⭐⭐½ | Best Llama for reasoning |
| 10 | **Gemini 2.0 Flash** | Google AI Studio | ⭐⭐⭐½ | Reliable, fast, multimodal |

### Provider-Level Comparison

| Provider | Model Quality | Rate Limits | Reliability | API Ease | Privacy | Value |
|---|---|---|---|---|---|---|
| Google AI Studio | ★★★★★ | ★★★★☆ | ★★★★★ | ★★★★★ | ★★★☆☆ | ★★★★★ |
| Groq | ★★★★☆ | ★★★☆☆ | ★★★★★ | ★★★★★ | ★★★★★ | ★★★★☆ |
| Cerebras | ★★★★☆ | ★★★★☆ | ★★★★☆ | ★★★★★ | ★★★★★ | ★★★★★ |
| Mistral | ★★★★☆ | ★★☆☆☆ | ★★★★☆ | ★★★★☆ | ★★★★☆ | ★★★☆☆ |
| OpenRouter | ★★★★★ | ★★★☆☆ | ★★★☆☆ | ★★★★★ | ★★★☆☆ | ★★★★☆ |
| NVIDIA NIM | ★★★★☆ | ★★★★★ | ★★★★☆ | ★★★★★ | ★★★★★ | ★★★★★ |
| Cloudflare | ★★★☆☆ | ★★★☆☆ | ★★★★★ | ★★★★☆ | ★★★★★ | ★★★☆☆ |
| Hugging Face | ★★★☆☆ | ★★☆☆☆ | ★★★☆☆ | ★★★☆☆ | ★★★★☆ | ★★★☆☆ |
| Cohere | ★★★☆☆ | ★★★☆☆ | ★★★★☆ | ★★★★☆ | ★★★★★ | ★★★★☆ |
| GitHub Models | ★★★★★ | ★★☆☆☆ | ★★★★☆ | ★★★★★ | ★★★★★ | ★★★☆☆ |

---

## 5. Use-Case Recommendations

| Use Case | Best Free Model | Best Free Access | Why |
|---|---|---|---|
| **Daily coding / IDE assistant** | DeepSeek V3 or Qwen3-Coder | OpenRouter :free | Top coding benchmarks; MIT license |
| **Agentic coding (multi-file)** | Devstral | OpenRouter :free | Built for tool use and repo traversal |
| **Complex reasoning & math** | DeepSeek R1 | OpenRouter :free | o1-comparable reasoning at $0 |
| **Long document analysis** | Gemini 2.5 Flash | Google AI Studio | 1M free context; handles PDFs |
| **Analyzing entire codebases** | Llama 4 Scout | Groq / Cerebras / NVIDIA NIM | 10M token context window |
| **Multimodal / image analysis** | Gemini 2.5 Flash | Google AI Studio | Text + image + audio + video |
| **Ultra-low latency apps** | Llama 4 Scout or Qwen3 32B | **Cerebras** | 2,600+ tokens/sec free |
| **High-throughput prototyping** | Qwen3 32B or Llama 4 Scout | **Cerebras** | 1M tokens/day free budget |
| **Multilingual tasks** | Qwen3 235B | OpenRouter :free | 100+ languages, top quality |
| **Local/private inference** | Gemma 3 27B or Llama 4 Scout | Ollama (self-hosted) | No data leaves your machine |
| **General chat assistant** | Claude Sonnet 4.6 | claude.ai | High quality per message |
| **Real-time data / current events** | Grok 3 | GitHub Models | Access to X/Twitter data |
| **Free API experimentation** | Multiple models | OpenRouter | One key, 29+ free models |
| **Developer prototyping (API)** | Gemini 2.5 Flash | Google AI Studio | Best permanent free API tier |
| **Debugging complex errors** | DeepSeek R1 | OpenRouter :free | Step-by-step reasoning through errors |
| **Image generation (free)** | FLUX via Cloudflare | Cloudflare Workers AI | Free image gen, 10K neurons/day |
| **RAG pipelines** | Command R+ + Embed 4 | Cohere | Full RAG stack at zero cost |
| **Embeddings & semantic search** | Embed 4 (Cohere) | Cohere | Best free multilingual embeddings |
| **AI agents & automation** | Llama 4 Scout (Cerebras) | Cerebras | Speed + 10M context |
| **Research & academic work** | Gemini 2.5 Flash | Google AI Studio | 1M context, multimodal, reliable |
| **Content creation** | Gemini 2.5 Flash | Google AI Studio | Creative + multimodal |
| **Student everyday use** | Gemini 2.5 Flash | Google AI Studio | 1,500 free requests/day, no CC |
| **Enterprise / privacy-sensitive** | Groq + Cerebras + NVIDIA NIM | Various | These three do not train on user data |

---

### Recommendations by User Type

#### For Students

**Primary:** Google AI Studio (Gemini 2.5 Flash)
- 1,500 free requests/day, no credit card, 1M context for uploading lecture slides and PDFs
- Multimodal — analyze diagrams, charts, equations in images
- Pair with: Groq (DeepSeek R1 for math/reasoning), GitHub Models (GPT-5 for essay help)

**Stack:**
1. Google AI Studio → everyday Q&A, document analysis, image understanding
2. Groq → math, logic, step-by-step reasoning (DeepSeek R1 Distill)
3. GitHub Models → GPT-5 for creative and language-heavy tasks

---

#### For Developers

**Primary:** Groq + NVIDIA NIM (complementary)
- Groq: fastest development loop, OpenAI-compatible, no credit card
- NVIDIA NIM: 40 RPM sustained throughput when Groq's 1,000 RPD runs out

**Stack:**
1. Groq → interactive development, fast iteration (Llama 3.3 70B or DeepSeek R1)
2. NVIDIA NIM → sustained workloads, batch processing
3. Google AI Studio → multimodal features, long-context document processing
4. Mistral (Codestral) → long code-file editing (256K context)
5. OpenRouter → A/B testing models, model-agnostic architecture

**Tips:**
- Use Groq's OpenAI-compatible endpoint — swap in/out without code changes
- Route coding tasks to DeepSeek R1, creative tasks to Gemini, long-context to Llama 4 Scout
- NVIDIA NIM for anything where Groq's 1,000 RPD cap becomes a bottleneck

---

#### For Researchers

**Primary:** Google AI Studio + NVIDIA NIM
- Gemini 2.5 Flash: ingest PDFs, images, audio, long papers (1M context)
- Llama 4 Scout (NVIDIA NIM): 10M token context for entire corpora
- DeepSeek R1 (Groq): transparent reasoning chains — inspect model's thinking

**Stack:**
1. Google AI Studio → multimodal document analysis, literature review
2. NVIDIA NIM (Llama 4 Scout) → whole-corpus ingestion
3. Groq (DeepSeek R1) → math, science reasoning with traceable steps
4. Cohere (Command R+ + Embed 4) → RAG over research databases
5. OpenRouter (Qwen3 235B) → largest open MoE for complex synthesis

---

#### For AI Agents & Automation

**Primary:** Cerebras + Groq (complementary)
- Cerebras: 2,600+ tok/s means multi-step agent loops complete in seconds, not minutes
- Llama 4 Scout: 10M context enables agents that hold entire codebases or conversation histories in context

**Stack:**
1. Cerebras (Llama 4 Scout / Qwen3 32B) → fast agent calls, reasoning loops
2. Groq (DeepSeek R1 70B) → planning, tool selection, complex reasoning steps
3. Google AI Studio (Gemini 2.5 Flash) → multimodal tool use, grounded search, document parsing
4. NVIDIA NIM → sustained background agent tasks, overflow from Groq/Cerebras limits

**Architecture tip:** Use Cerebras for fast "worker" calls and Gemini 2.5 Flash for "orchestrator" steps that need tool use or vision.

---

#### For Content Creators

**Primary:** Google AI Studio + GitHub Models
- Gemini 2.5 Flash: analyze reference images, generate with visual context
- GPT-5 (GitHub Models): best language quality for polished writing

**Stack:**
1. Google AI Studio → visual content analysis, long-form drafting
2. GitHub Models (GPT-5) → high-quality writing, creative tasks
3. Groq (Llama 3.3 70B) → fast bulk generation, first drafts
4. Cloudflare Workers AI (FLUX.1 Schnell) → free AI image generation

---

#### For Enterprise / Privacy-Sensitive Workflows

> Note: Free tiers from most providers do not guarantee the privacy protections enterprises require. For production, consider paid tiers. For prototyping:

**Primary:** Groq + Cerebras + NVIDIA NIM
- These three providers explicitly do not train on user data on free tiers
- Avoid: Google AI Studio (free tier data used for training), Mistral free tier (data used for improvement)

**Stack:**
1. Groq (Llama 3.3 70B or DeepSeek R1) → internal reasoning tasks
2. Cerebras → high-speed batch classification, extraction
3. NVIDIA NIM → sustained workloads, larger model inference
4. Cloudflare Workers AI → GDPR-compliant edge inference (EU data residency)

---

## 6. Free Tier Limitations Comparison

| Provider | Rate Limit | Token Limit | Expiry | Credit Card | Data Privacy |
|---|---|---|---|---|---|
| **Google AI Studio** | 15–30 RPM (Flash) | 1M TPM | Never | ❌ | Google's data policy (trains on free tier) |
| **Cerebras** | 30 RPM | **1M tokens/day** | Never | ❌ | US-based servers; no data training |
| **Groq** | 30 RPM, 1K–14.4K RPD | 100K–500K TPD | Never | ❌ | US-based; no data training |
| **OpenRouter** | 20 RPM, 50 RPD (no balance) | Varies | Never | ❌ | Depends on model provider |
| **NVIDIA NIM** | 40 RPM, no hard daily cap | Not published | Never | ❌ (phone verify) | US-based; no data training |
| **Cloudflare Workers AI** | 10K neurons/day | Varies | Never | ❌ | Edge (global); no data training |
| **GitHub Models** | ~50 req/day (free tier) | Tied to Copilot | Never | ❌ (GitHub account) | Microsoft |
| **Mistral API** | 2 RPM (free mode) | ~1B tok/month | Never | ❌ (phone) | EU-based; data used for training |
| **Hugging Face** | ~100K credits/month | Model-dependent | Monthly reset | ❌ | Varies |
| **Cohere** | 5 RPM | Trial credits | Finite | ❌ | US/Canada |
| **ChatGPT (OpenAI)** | Aggressive (unpublished) | Not published | Never | ❌ | OpenAI policy |
| **Claude (Anthropic)** | Stricter than Gemini | ~30–100 msgs/day est. | Never | ❌ | Anthropic policy |
| **DeepSeek chat** | Moderate | Not published | Never | ❌ | 🚨 Servers in China |
| **OpenAI API** | N/A | $5 one-time credit | ⚠️ Expires | ✅ Required after | OpenAI policy |
| **xAI API** | N/A | $25 one-time | ⚠️ Expires | ✅ Required | xAI policy |

---

## 7. Privacy & Data Handling

> ⚠️ **Important for business/enterprise users:** Where your data goes matters.

| Provider | Data Location | Logs Prompts? | Notes |
|---|---|---|---|
| **Google AI Studio** | US/Global | By default | Can opt out; review data settings; free tier data used for training |
| **Anthropic (Claude)** | US | By default | Free tier data may be used for training |
| **OpenAI (ChatGPT)** | US | By default | Can disable chat history/training |
| **Groq** | US | No | No data training on user prompts |
| **Cerebras** | US | No | No data training on user prompts |
| **Mistral AI** | EU | Zero-retention option | Best EU data residency; data may be used for improvement on free tier |
| **DeepSeek** | 🚨 **China** | Yes | Not recommended for sensitive data |
| **Cloudflare Workers AI** | Edge (global) | Limited | Privacy-forward architecture; no data training |
| **NVIDIA NIM** | US | No | No data training on user prompts |
| **OpenRouter** | Routed to provider | Varies | Check underlying provider |
| **Cohere** | US/Canada | Varies | Production-grade API |
| **GitHub Models** | Azure (global) | Microsoft policy | Tied to GitHub/Copilot |
| **Venice.ai** | Decentralized | No server logging | Privacy-first alternative |
| **Duck.ai** | Proxied | Nothing stored | Anonymous; uses Llama/Claude under the hood |

---

## 8. Stacking Free Tiers: The Zero-Cost Inference Stack

You can combine multiple free tiers to reach **3–4 million free tokens/day** with zero spending:

### Starter Stack (Prototyping)
```
Primary:    Google AI Studio    → Gemini 2.5 Flash (multimodal, long context)
Secondary:  Groq                → Llama 4 / DeepSeek R1 Distill (speed)
Fallback:   OpenRouter :free    → DeepSeek V3 / Qwen3 235B (quality)
```

### Developer Stack (High Volume)
```
Primary:    Cerebras            → 1M tokens/day (fastest)
Secondary:  Google AI Studio    → 1.5K RPD Gemini (multimodal fallback)
Tertiary:   Groq                → 1K–14.4K RPD (speed fallback)
Overflow:   OpenRouter :free    → 29+ models (model variety)
```

### Developer Stack (Sustained Workloads)
```
Primary:    NVIDIA NIM          → 40 RPM, no daily cap (sustained throughput)
Secondary:  Groq                → Fast interactive development
Tertiary:   Google AI Studio    → Multimodal, long-context
Overflow:   OpenRouter :free    → Model variety
```

### Privacy-First Stack
```
Primary:    Ollama (local)      → Gemma 3 27B or Llama 4 Scout (no data sent)
Secondary:  Mistral AI (free)   → EU-based, zero-retention option
Fallback:   Cloudflare Workers  → Edge-deployed
```

### Research/Reasoning Stack
```
Primary:    DeepSeek R1 via OpenRouter :free  → Best reasoning
Secondary:  Gemini 2.5 Flash via AI Studio   → Best context + multimodal
Tertiary:   Qwen3 235B via OpenRouter :free  → All-around backup
```

### AI Agents Stack
```
Primary:    Cerebras (Llama 4 Scout / Qwen3 32B) → Fast agent calls
Secondary:  Groq (DeepSeek R1 70B)              → Planning & reasoning
Tertiary:   Google AI Studio (Gemini 2.5 Flash)  → Multimodal tool use
Overflow:   NVIDIA NIM                           → Sustained background tasks
```

### Student Stack
```
Primary:    Google AI Studio    → Gemini 2.5 Flash (everyday Q&A, documents)
Secondary:  Groq                → DeepSeek R1 (math, reasoning)
Tertiary:   GitHub Models       → GPT-5 (essays, creative writing)
```

---

## 9. Quick-Pick Decision Tree

```
What's your priority?
│
├── QUALITY (best output)
│   ├── Need reasoning → DeepSeek R1 (OpenRouter :free)
│   ├── Need coding   → DeepSeek V3 or Qwen3-Coder (OpenRouter :free)
│   └── Need chat     → Claude Sonnet 4.6 (claude.ai)
│
├── CONTEXT LENGTH (huge documents)
│   ├── < 1M tokens   → Gemini 2.5 Flash (Google AI Studio)
│   └── > 1M tokens   → Llama 4 Scout (Groq or Cerebras)
│
├── SPEED (low latency)
│   ├── Fastest ever  → Any model on Cerebras (2,600+ tok/s)
│   └── Very fast     → Groq LPU (~315 tok/s)
│
├── MULTIMODAL (images / audio / video)
│   └── → Gemini 2.5 Flash (Google AI Studio) — best by far
│
├── PRIVACY (sensitive data)
│   ├── Max privacy   → Ollama (local) with Gemma 3 27B or Llama 4
│   ├── EU data       → Mistral AI (free tier)
│   └── No training   → Groq, Cerebras, or NVIDIA NIM
│
├── HIGH VOLUME (many requests/day)
│   ├── Tokens/day    → Cerebras (1M tokens/day free)
│   ├── Requests/day  → Groq (14.4K RPD for some models)
│   └── Sustained     → NVIDIA NIM (40 RPM, no daily cap)
│
├── VARIETY (try many models)
│   └── → OpenRouter (29+ free models, one API key)
│
├── FRONTIER MODELS (GPT-5, Grok 3)
│   └── → GitHub Models (free with GitHub account)
│
├── RAG / SEARCH (embeddings + generation)
│   └── → Cohere (Command R+ + Embed 4 + Rerank 3.5)
│
└── EDGE DEPLOYMENT (low geographic latency)
    └── → Cloudflare Workers AI (250+ cities)
```

---

## Provider Rankings (Overall Free Tier Value)

| Rank | Provider | Score /10 | Best For |
|---|---|---|---|
| 1 | **Google AI Studio** | 9.2 | Multimodal, long-context, sustained daily use |
| 2 | **NVIDIA NIM** | 8.8 | Sustained throughput, model variety, no data training |
| 3 | **Cerebras** | 8.5 | Speed, agentic workflows, high daily token volume |
| 4 | **Groq** | 8.4 | Fast inference, coding/reasoning, OpenAI-compatible |
| 5 | **OpenRouter** | 7.8 | Model variety, multi-provider access, experimentation |
| 6 | **Mistral** | 7.2 | Code (Codestral), GDPR compliance, batch tasks |
| 7 | **GitHub Models** | 6.8 | GPT-5 access, prototyping, GitHub users |
| 8 | **Cohere** | 6.5 | RAG pipelines, embeddings, semantic search |
| 9 | **Cloudflare Workers AI** | 5.8 | Edge latency, image/audio generation, Cloudflare apps |
| 10 | **Hugging Face** | 5.5 | Model discovery, research, routing gateway |

---

## Overall Best Free Models (Cross-Provider)

| Rank | Model | Provider | Category Win |
|---|---|---|---|
| 1 | **Gemini 2.5 Flash** | Google AI Studio | Best all-rounder: multimodal + long-context |
| 2 | **DeepSeek R1 Distill 70B** | Groq / NVIDIA NIM | Best free reasoning + coding model |
| 3 | **DeepSeek V3** | OpenRouter / NVIDIA NIM | Best free coding model |
| 4 | **Llama 4 Scout** | NVIDIA NIM / Groq / Cerebras | Best context window (10M) |
| 5 | **Qwen3 235B** | OpenRouter | Best open-weight all-rounder |
| 6 | **GPT-5** | GitHub Models | Best GPT-class access |
| 7 | **Qwen QwQ 32B** | Groq | Best dedicated reasoning model |
| 8 | **GPT-OSS 120B** | Cerebras / NVIDIA NIM | Best speed-quality balance |
| 9 | **Codestral** | Mistral | Best code-specialized model (256K context) |
| 10 | **Llama 3.3 70B** | Groq / Cerebras | Best reliable baseline |
| 11 | **Command R+** | Cohere | Best RAG model |
| 12 | **Llama 3.1 8B** | Groq | Best high-volume lightweight model |

---

## Model Capability Ratings (Free Tier)

Ratings are on a 1–5 scale (5 = best), relative to what is available at zero cost. Rows are models as served by their best free provider.

| Model / Provider | Coding | Reasoning | Debugging | Speed | Context | Multimodal | Overall |
|---|---|---|---|---|---|---|---|
| Gemini 2.5 Flash (Google AI Studio) | 4 | 4 | 4 | 3 | 5 | 5 | **4.5** |
| DeepSeek R1 Distill 70B (Groq) | 5 | 5 | 5 | 4 | 3 | 1 | **4.4** |
| Llama 4 Scout (Groq/NVIDIA) | 3 | 3 | 3 | 4 | 5 | 2 | **3.7** |
| Llama 4 Scout (Cerebras) | 3 | 3 | 3 | 5 | 5 | 2 | **3.8** |
| Qwen3 235B (OpenRouter) | 4 | 4 | 4 | 2 | 3 | 1 | **3.5** |
| Llama 3.3 70B (Groq) | 3 | 3 | 3 | 5 | 3 | 1 | **3.2** |
| Qwen QwQ 32B (Groq) | 4 | 5 | 4 | 4 | 3 | 1 | **4.0** |
| GPT-OSS 120B (Cerebras/NVIDIA) | 4 | 4 | 4 | 5 | 3 | 1 | **3.8** |
| Codestral (Mistral) | 5 | 3 | 5 | 1 | 4 | 1 | **3.8** |
| Mistral Large (Mistral) | 3 | 3 | 3 | 1 | 3 | 2 | **2.8** |
| Command R+ (Cohere) | 2 | 3 | 2 | 3 | 4 | 1 | **3.2** |
| GPT-5 (GitHub Models) | 5 | 5 | 5 | 3 | 4 | 4 | **4.5** |
| GPT-4o (GitHub Models) | 4 | 4 | 4 | 3 | 4 | 5 | **4.2** |
| Gemma 3 27B (Google/Cloudflare) | 3 | 3 | 3 | 3 | 3 | 3 | **3.0** |
| Devstral :free (OpenRouter) | 4 | 3 | 4 | 2 | 3 | 1 | **3.2** |
| Llama 3.1 8B (Groq) | 2 | 2 | 2 | 5 | 3 | 1 | **2.8** |

---

## API Availability & Compatibility

| Provider | API Protocol | SDK | OpenAI-Compatible | Streaming | Function Calling | Embeddings |
|---|---|---|---|---|---|---|
| Google AI Studio | REST / gRPC | Python, JS, Go, Java, REST | Partial | Yes | Yes | Yes (Gemini Embed) |
| Groq | REST | Python, JS, REST | **Yes (drop-in)** | Yes | Yes | No |
| Cerebras | REST | Python, REST | **Yes (drop-in)** | Yes | Yes | No |
| Mistral | REST | Python, JS | **Yes** | Yes | Yes | Yes |
| OpenRouter | REST | Any OpenAI SDK | **Yes (drop-in)** | Yes | Yes | No |
| NVIDIA NIM | REST | Any OpenAI SDK | **Yes (drop-in)** | Yes | Yes | Yes |
| Cloudflare | REST / Workers | JS (Workers), REST | Partial | Yes | Limited | Yes |
| Hugging Face | REST | Python (transformers), REST | Partial | Yes | Limited | Yes |
| Cohere | REST | Python, JS, Java, Go | Partial | Yes | Yes | Yes |
| GitHub Models | REST | Any OpenAI SDK | **Yes** | Yes | Yes | No |

---

## Important Caveats

Free tiers change frequently. This report reflects the best available information as of June 2026, but:

- Providers adjust rate limits, model availability, and data policies without advance notice
- Always verify current limits directly on the provider's official pricing/docs page before production use
- Google AI Studio free tier terms (data used for training) may change; check current policy before using for sensitive tasks
- OpenRouter free model availability depends on community subsidization and can fluctuate
- GitHub Models limits are tied to GitHub Copilot plan evolution
- DeepSeek API grants 5M free tokens at signup with a 30-day expiration, making it a time-limited rather than indefinite free tier
- Cerebras Llama 4 Scout context may be capped at 8K on free tier despite the model's 10M capability
- OpenRouter free models are deprioritized; latency can spike to 30–60+ seconds under load

**Indefinitely free (quota resets, no expiry):** Google AI Studio, Groq, Cerebras, OpenRouter, NVIDIA NIM, Cloudflare Workers AI, Mistral (experiment plan)

**Time-limited or finite credits:** DeepSeek API, SambaNova, Together AI, HuggingFace Inference Providers (monthly budget)

---

## Summary: The Top 5 Free Models of 2026

| # | Model | Why It's Here |
|---|---|---|
| **1** | **Gemini 2.5 Flash** (Google AI Studio) | Best permanent free API: 1M context, multimodal, reasoning, no CC required |
| **2** | **DeepSeek R1** (OpenRouter :free) | Best free reasoning model; o1-comparable performance at zero cost |
| **3** | **DeepSeek V3** (OpenRouter :free) | Best free coding model; MIT licensed; production-quality |
| **4** | **Llama 4 Scout** (Cerebras/Groq/NVIDIA NIM) | Largest free context window (10M); fastest inference on Cerebras |
| **5** | **Qwen3 235B** (OpenRouter :free) | Best open-weight all-rounder; #1 by token volume on OpenRouter |

---

## 10. AI Development Ecosystem & Tooling

> The following sections cover the full AI development stack — agents, frameworks, databases, deployment, and automation tools — that complement the free models above to build a complete AI-powered development environment.

### 10.1 AI Coding Agents

Tools that write, edit, debug, and refactor code autonomously.

#### OpenCode

| Field | Details |
|-------|---------|
| **Purpose** | Terminal-native AI coding agent, open-source Claude Code alternative |
| **License** | Open Source (MIT) |
| **GitHub Stars** | 150K+ (fastest growing in 2026) |
| **Learning Priority** | **Beginner** — primary coding agent |

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

#### Claude Code

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

#### Aider

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

#### OpenHands (formerly OpenDevin)

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

#### Cline

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

### 10.2 MCP Servers

> Model Context Protocol — the "USB standard" for AI tools. Connect agents to any data source or service.

**Core Concept:** MCP servers translate real-world systems into a format AI agents can act on. One standard, infinite integrations.

#### GitHub MCP Server
**Purpose:** Full GitHub access for AI agents — repository management, PR creation/review, issue tracking, code search, Actions integration. **Priority: Must-Have**

#### PostgreSQL MCP Server
**Purpose:** Database access and queries for agents — schema inspection, SQL query execution, data analysis, safe read/write operations. **Priority: Must-Have**

#### Filesystem MCP Server
**Purpose:** Local file system access — read/write files, directory traversal, file search. **Priority: Must-Have**

#### Browser/Playwright MCP Server
**Purpose:** Web browsing and scraping — browser automation, form filling, screenshot, web scraping. **Priority: High**
**Alternatives:** Puppeteer MCP, browser-control-mcp (Firefox extension)

#### Chroma MCP / Qdrant MCP
**Purpose:** Vector database access for RAG agents — semantic search, embedding retrieval, knowledge base queries. **Priority: High**

#### n8n MCP Server
**Purpose:** Trigger and manage n8n workflows from AI agents — workflow triggering, status monitoring, data passing between agents and automations. **Priority: High** — core integration

#### Notion MCP Server
**Purpose:** Read/write Notion databases and pages — page creation, database queries, task management via AI. **Priority: High** — project management integration

#### Slack / Discord MCP
**Purpose:** Team communication integration. **Priority: Medium**

#### Docker MCP
**Purpose:** Container management from AI agents — container start/stop, log inspection, image management. **Priority: Medium**

#### YouTube Transcript MCP
**Purpose:** Extract video transcripts for AI analysis. **Priority: Low-Medium**

#### dbt Semantic Layer MCP
**Purpose:** Data modeling and analytics access. **Priority: Advanced**

#### Building Custom MCP Servers
Use official SDKs: `@modelcontextprotocol/sdk` (TypeScript), `mcp` (Python). Any REST API can become an MCP server in ~50 lines of code.

---

### 10.3 AI Frameworks & Orchestration

Scaffolding that turns single LLM calls into complex, stateful applications.

#### LangChain
**License:** MIT | **Stars:** 85K+ | **Priority:** **Beginner**

Foundation framework for LLM applications. Integrations with all major LLM providers, document loaders (PDF, CSV, web, Notion), support for all major vector databases, chains/agents/tools ecosystem, LangSmith integration for observability. **Use Cases:** RAG pipelines, chatbots, document QA, tool-using agents

#### LangGraph
**License:** MIT (LangChain ecosystem) | **Priority:** **Intermediate**

Graph-based stateful agent workflows. State machine with nodes, edges, conditional routing. Durable execution — agents resume after failures. Human-in-the-loop support. Checkpointing and persistence. PostgresSaver for database-backed state. Both Python and JavaScript. v1.0 production-hardened. **Use Cases:** Production agents, multi-step reasoning, approvals workflows, long-running jobs

#### LlamaIndex
**License:** MIT | **Priority:** **Intermediate**

RAG-first framework for enterprise data. Best-in-class document parsing and indexing. Works with Qdrant, Weaviate, Pinecone, MongoDB. Agent capabilities over structured/unstructured data. Multi-modal support. **Use Cases:** Document intelligence, enterprise RAG, data analysis agents

#### Haystack (deepset)
**License:** Apache 2.0 | **Priority:** **Advanced**

Production RAG with built-in evaluation. REST API deployment ready. Modular pipeline design.

#### Anthropic Claude Agent SDK
**Priority:** **Intermediate**

Official Anthropic SDK for Claude-native agents. Native tool use and memory APIs. Passed AutoGen in enterprise deployment count (Q1–Q2 2026).

#### Pydantic AI
**Priority:** **Intermediate**

Type-safe agent framework from Pydantic team. Full type safety from model to response. Structured outputs by default. Clean, minimal API design.

---

### 10.4 Multi-Agent Systems

Orchestrate teams of specialized AI agents working together.

#### CrewAI
**License:** MIT (core) | **Priority:** **Beginner** — primary multi-agent framework

Role-based multi-agent collaboration. Define agents with roles, goals, backstories. Sequential and parallel task execution. Built-in tool routing for Claude/GPT/Gemini. Async crew runner (experimental). A2A (Agent-to-Agent) protocol support growing. **Use Cases:** Research agents, content pipelines, automated workflows with multiple specialists
**Alternatives:** AutoGen (conversational), LangGraph (stateful), OpenAI Agents SDK

#### Microsoft AutoGen / AG2
**License:** Apache 2.0 (AG2 community fork) / CC-BY-4.0 | **Priority:** **Intermediate**

Conversational multi-agent problem solving. GroupChat: agents debate and collaborate. No-code AutoGen Studio. .NET support for enterprise. Best for deliberation and brainstorming workflows.
**Note:** AutoGen split in 2025 — Microsoft maintains v0.4+ rewrite; community continues as AG2. Pick deliberately.

#### Google ADK (Agent Development Kit)
**Priority:** **Advanced**

Hierarchical agent trees with A2A protocol. Root agent delegates to sub-agents recursively. Native A2A protocol for cross-framework communication. Integrates with Vertex AI and Gemini. Can call LangGraph or CrewAI agents via A2A.

#### OpenAI Agents SDK
**Priority:** **Intermediate**

Production agent framework from OpenAI. Handoffs: explicit agent-to-agent control transfer. First-party tools (code interpreter, web search). Production-grade since March 2025.

#### MetaGPT
**License:** Apache 2.0 | **Priority:** **Advanced**

Software development automation via agent teams. Simulates software engineering team (PM, architect, engineer, QA). Generates PRDs, architecture docs, and code. Best for greenfield projects.

---

### 10.5 LLM Providers & Local Models

#### Cloud LLM Providers

| Provider | Best Model | Strength | Pricing |
|----------|-----------|----------|---------|
| **Anthropic** | Claude Opus 4.7 (87.6% SWE-bench) | Reasoning, coding, agents | Pay-per-token |
| **OpenAI** | GPT-5.5 / o3 | General purpose, speed | Pay-per-token |
| **Google** | Gemini 2.5 Pro | Multimodal, long context | Pay-per-token |
| **DeepSeek** | DeepSeek-V3 / R1 | Cost-effective, strong reasoning | Very cheap |
| **Groq** | Llama 3.1 70B | Ultra-fast inference | Free tier |
| **Together AI** | Multiple open models | BYOM hosting | Affordable |

#### Ollama (Local Models)
**License:** MIT | **Priority:** **Beginner** — install immediately

One command to pull and run models: `ollama pull llama3.1`. REST API compatible with OpenAI format. Runs Llama, Qwen, DeepSeek, Mistral, Phi locally. Zero API cost after download. Works offline.

**Recommended Models:**
- `llama3.1:8b` — fast, fits 8GB RAM
- `qwen2.5-coder:7b` — best local coding model
- `deepseek-r1:7b` — local reasoning
- `nomic-embed-text` — local embeddings

**Use Cases:** Private/offline work, cost-free prototyping, embedding generation

#### LiteLLM
**License:** MIT | **Priority:** **Intermediate**

Universal LLM gateway — one API for 100+ providers. Single OpenAI-compatible API endpoint. Automatic failover between providers. Cost tracking and rate limiting. Self-hostable proxy. **Use Cases:** Model routing, cost optimization, provider abstraction

---

### 10.6 RAG & Knowledge Systems

Give your agents long-term memory and domain knowledge.

#### RAG Architecture
```
Documents → Chunking → Embedding → Vector Store
                                        ↓
User Query → Embedding → Similarity Search → Retrieved Chunks
                                                    ↓
                                     LLM + Context → Answer
```

#### LangChain RAG Pipeline (Priority: Beginner)
Standard starting point. Combines document loaders, text splitters, embeddings, vector stores, and retrieval chains.

#### LlamaIndex (Priority: Intermediate)
Better for complex document types (PDFs with tables, code, structured data). Superior parsing.

#### Chroma (Priority: Beginner)
Local-first vector database for development. Zero setup, runs in-process or as server. Python and JavaScript clients. Persistent storage on disk.

#### Unstructured.io (Priority: Intermediate)
Document parsing pipeline (PDF, DOCX, HTML, etc.). Handles messy real-world documents. Table extraction, image captioning. Chunking strategies built-in.

#### DSPy (Priority: Advanced)
Programmatic prompt optimization framework. Automatically optimizes prompts via compilation. Replaces manual prompt engineering. Works with any LLM.

---

### 10.7 Vector Databases

#### Qdrant
**License:** Apache 2.0 | **Priority:** **Intermediate** — primary vector DB

High-performance vector database, self-hostable. Built in Rust — blazing fast (8ms p50 at 1M vectors). Best filtered vector search. Payload filtering: combine similarity + metadata conditions. Self-host free, or Qdrant Cloud (1GB free tier). Docker deployment in one command.

**Command:** `docker run -p 6333:6333 qdrant/qdrant`

**Use Cases:** Production RAG, semantic search, AI memory systems

#### pgvector (PostgreSQL Extension)
**License:** PostgreSQL License | **Priority:** **Beginner** — simplest if already on Postgres

Vector search inside PostgreSQL. No new database to manage. Combines relational + vector queries. Works with all PostgreSQL tools.

**Use Cases:** Simple RAG, apps already on PostgreSQL, unified data layer

#### Weaviate
**License:** BSD-3-Clause | **Priority:** **Intermediate**

AI-native vector database with hybrid search. Hybrid search: vector similarity + BM25 keyword. GraphQL API. Multi-modal data handling. Agent Skills for agentic AI (Feb 2026). SOC 2 / HIPAA compliant.

#### Milvus
**License:** Apache 2.0 | **Priority:** **Advanced**

Open-source vector database at scale. Built for billions of vectors. Kubernetes-native. Multiple index types.

#### Pinecone
**Priority:** **Intermediate** — if you want zero ops

Fully managed serverless vector database. **Note:** Managed only — no self-hosting option.

---

### 10.8 Backend Development

#### FastAPI
**License:** MIT | **Priority:** **Beginner** — primary backend

High-performance Python API framework. Automatic OpenAPI/Swagger documentation. Native async support (asyncio). Type safety via Pydantic. 38-40% Python web dev adoption (2025-2026). Perfect pairing with AI/ML Python ecosystem. Auto-validation of LLM structured outputs. 1-line integration with LangChain, CrewAI.

#### Node.js / Express / Hono
**Hono** — ultra-fast, edge-compatible. Prefer over Express for new projects.
**NestJS** — opinionated, enterprise-grade TypeScript framework.

#### Supabase
**License:** Apache 2.0 | **Priority:** **Beginner** — backend-as-a-service

Open-source Firebase alternative. PostgreSQL database with auto-generated REST APIs. Authentication (email, OAuth, phone). Row-Level Security (RLS) policies. Real-time subscriptions. Edge Functions (serverless). File storage. TypeScript type generation from schema. Self-hostable via Docker.

**Use Cases:** Full-stack apps, SaaS, auth layer, rapid prototyping

#### Redis
**License:** Redis Source Available (SSPL) / Valkey (BSD)

**Use Cases:** Agent session caching, rate limiting, pub/sub for workflows, LLM response caching
**Alternative:** Valkey (BSD-3, community Redis fork)

---

### 10.9 Frontend Development

#### Next.js
**License:** MIT | **Priority:** **Beginner** — primary frontend framework

React framework for full-stack web applications. SSR + SSG. React Server Components. API routes built-in. Vercel deployment in one click. App Router for modern patterns.

#### Tailwind CSS
**License:** MIT | **Priority:** **Beginner** — use with every project

Utility-first CSS framework. No CSS file maintenance. Responsive design utilities built-in. Pairs perfectly with shadcn/ui.

#### shadcn/ui
**License:** MIT | **Priority:** **Beginner**

Copy-paste React component library. Components you own (not a package). Built on Radix UI primitives. Tailwind-based styling. AI-assistant friendly (generates great shadcn code).

#### React / TypeScript
Standard foundation for all modern web UIs. Always use TypeScript.

#### Vercel
**Priority:** **Beginner**

Frontend deployment platform. Zero-config Next.js deployment, edge functions, analytics, preview deployments. Generous free tier for personal projects.

---

### 10.10 Databases & Storage

#### PostgreSQL
**License:** PostgreSQL License (fully open source) | **Priority:** **Beginner** — use for everything

ACID compliant, battle-tested at scale. JSON/JSONB support. pgvector extension for vector search. Full-text search built-in. Row-Level Security. Rich ecosystem (Prisma, SQLAlchemy, Drizzle).

**Extensions to install:** `pgvector` (vector similarity search), `pg_cron` (scheduled jobs), `pg_stat_statements` (query performance)

#### SQLite
**License:** Public Domain | **Priority:** **Beginner**

Zero-config embedded database. **Use Cases:** Local development, prototyping, small apps, agent memory stores

#### Prisma ORM
**License:** Apache 2.0 | **Priority:** **Beginner**

Type-safe database ORM for TypeScript. **Use Cases:** Next.js + PostgreSQL, type-safe queries, schema migrations

#### SQLAlchemy / SQLModel
**License:** MIT | **Priority:** **Beginner**

Python ORM for FastAPI + PostgreSQL. **SQLModel** = SQLAlchemy + Pydantic, built by FastAPI creator.

#### MinIO
**License:** AGPL-3.0 | **Priority:** **Intermediate**

Self-hosted S3-compatible object storage. **Use Cases:** File uploads, model artifacts, RAG document storage, backups

---

### 10.11 DevOps & Deployment

#### Docker & Docker Compose
**License:** Apache 2.0 (Compose) | **Priority:** **Beginner** — use from day one

Container runtime and multi-service orchestration. Reproducible environments. Volume mounts for data persistence. Networks for service isolation.

**Recommended services:**
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

#### GitHub Actions
**Priority:** **Beginner**

CI/CD pipeline automation. Free for public repos (2000 min/month private). Matrix builds, artifact caching. OpenCode/Claude Code integration for PR reviews. Docker build and push automation.

**Core workflows to build:** 1. Test on PR → merge on pass 2. Build Docker image → push to registry 3. Deploy on merge to main 4. AI code review on PR

#### Coolify
**License:** Apache 2.0 | **Priority:** **Intermediate**

Self-hosted Heroku/Vercel alternative. Deploy any Docker app from GitHub. Free on your own VPS. SSL, domains, environment variables managed. Supports Next.js, FastAPI, n8n, Supabase.

#### Kubernetes (k3s / k0s)
**Priority:** **Advanced**

Container orchestration at scale. **k3s** — lightweight Kubernetes for single servers and edge. Use when you outgrow Docker Compose.

#### Terraform / OpenTofu
**License:** MPL-2.0 | **Priority:** **Advanced**

Infrastructure-as-code. **OpenTofu** is the fully open-source Terraform fork maintained by the Linux Foundation.

---

### 10.12 Observability & Monitoring

#### Langfuse
**License:** MIT | **Priority:** **Intermediate** — primary AI observability tool

LLM tracing, prompt management, evaluation. Full request/response tracing for LLM calls. Prompt versioning and management. Multi-turn conversation tracking. Self-hosted (free) or cloud ($59/month Pro). Acquired by ClickHouse (Jan 2026). Works with LangChain, LlamaIndex, OpenAI, Anthropic.

**Use Cases:** Debug agent failures, track costs, monitor quality regressions

#### LangSmith
**Priority:** **Intermediate**

LangChain-native tracing and evaluation. Best for teams using LangChain/LangGraph. Native graph visualization. **Note:** Commercial SaaS, no self-hosting.

#### Arize Phoenix
**License:** ELv2 | **Priority:** **Advanced**

OpenTelemetry-native AI observability. OTel-native — integrates with existing APM. Strong open-source eval metrics library. Best self-hosted alternative to Langfuse.

#### Helicone
**License:** Apache 2.0 | **Priority:** **Beginner** — fastest to add

LLM gateway with cost tracking. One-line proxy integration. Multi-provider cost visibility. Caching to reduce spend. Response replay.

#### Grafana + Prometheus
**License:** AGPL-3.0 (Grafana) / Apache 2.0 (Prometheus) | **Priority:** **Intermediate**

General-purpose metrics and dashboards. **Use Cases:** System metrics (CPU, memory, latency), custom dashboards, alerts

#### Sentry
**Priority:** **Beginner**

Application error tracking. **Use Cases:** Catch runtime errors in FastAPI, Next.js, agent code

---

### 10.13 Automation & Workflows

#### n8n
**License:** Source-available (free self-hosted) | **Priority:** **Beginner** — primary automation layer

Visual workflow automation with 1,400+ integrations (Slack, GitHub, Gmail, Notion, Airtable, etc.). LLM nodes: OpenAI, Anthropic, Google, Ollama. AI agent nodes — build agents visually. Webhook triggers, cron jobs, event triggers. Self-hosted on a $5 VPS = unlimited executions.

**Cost advantage:** n8n Cloud Pro = €60/month for 30K executions. Self-hosted = $5/month, unlimited.

**How it works with AI OS:** n8n handles SaaS plumbing and data routing; Hermes Agent handles AI reasoning steps; CrewAI agents can be triggered via n8n webhooks.

**Use Cases:** Lead processing, report generation, code review pipelines, notification systems, data ETL

#### Hermes Agent
**License:** MIT | **Priority:** **Intermediate** — pairs with n8n

Memory-backed AI agent for judgment-heavy tasks. Memory persistence across runs. Designed for research, analysis, report generation. Minimal dependencies — easy self-host via Docker. Webhook and cron job support.

**When to use vs n8n:** Use **n8n** when every step is predefined ("when X, do Y, then Z"). Use **Hermes** when the task requires judgment, research, or memory.

**Use Cases:** Competitor monitoring, support ticket analysis, monthly data reports, strategic research

#### Zapier / Make.com
**Priority:** **Beginner** (use n8n instead for self-hosted)

Commercial automation platforms. Use for quick integrations without self-hosting overhead.

#### Temporal
**License:** MIT | **Priority:** **Advanced**

Durable workflow execution engine. **Use Cases:** Long-running agent tasks, retry logic, workflow versioning at scale

---

### 10.14 Authentication & Security

#### Supabase Auth
**Priority:** **Beginner** — use if already on Supabase

Authentication built into your database. Email/password, OAuth (Google, GitHub), magic links. Row-Level Security (RLS) on every table. JWT tokens.

#### Clerk
**Priority:** **Beginner**

Authentication-as-a-service for Next.js. Best developer experience for Next.js. Pre-built UI components. Middleware integration. Generous free tier.

#### Auth.js (NextAuth)
**License:** ISC | **Priority:** **Intermediate**

Open-source auth for Next.js. Self-hosted auth with multiple providers.

#### Keycloak
**License:** Apache 2.0 | **Priority:** **Advanced**

Enterprise SSO and identity management. SAML/OIDC for enterprise clients, multi-tenant SaaS.

#### Vault (HashiCorp) / Infisical
**License:** BSL 1.1 (Vault) / MIT (Infisical) | **Priority:** **Intermediate**

Secrets management. **Infisical** — open-source, self-hostable. Preferred for teams.

#### OWASP Best Practices
- Never hardcode API keys — use `.env` + Infisical
- Rate limit all LLM endpoints
- Validate and sanitize all agent tool inputs
- Use RLS in PostgreSQL
- Scan Docker images with Trivy

---

### 10.15 Testing & Evaluation

#### Pytest
**License:** MIT | **Priority:** **Beginner** — test everything

Python testing framework. **Use Cases:** FastAPI endpoints, agent functions, RAG pipeline quality

#### DeepEval
**License:** Apache 2.0 | **Priority:** **Intermediate**

LLM evaluation framework. 14+ evaluation metrics (faithfulness, relevancy, hallucination, toxicity). RAG-specific evaluators (context precision, recall). CI/CD integration. Self-hosted evaluations.

#### RAGAS
**License:** Apache 2.0 | **Priority:** **Intermediate**

RAG pipeline evaluation. **Metrics:** Faithfulness, answer relevancy, context recall, context precision

#### Playwright / Cypress
**Priority:** **Intermediate**

End-to-end browser testing. **Playwright** — Microsoft, cross-browser, Python + JS. Preferred.

#### Jest / Vitest
**Priority:** **Beginner**

JavaScript unit testing. **Vitest** — faster, Vite-native. Preferred for new projects.

#### Braintrust
**Priority:** **Advanced**

Eval-driven development with CI/CD gates. Free tier: 1M spans/month, 10K evals.

---

### 10.16 Productivity & Project Management

#### Notion
**Priority:** **Beginner** — primary project hub

Knowledge base, project management, AI workspace. Notion MCP server → AI agents read/write to Notion. Store agent prompts, system designs, roadmaps. Link GitHub issues to Notion tasks. Auto-generate project docs via n8n + LLM.

**Recommended Setup:** Projects database (linked to GitHub repos), Prompts Library (system prompts for agents), Agent Runbooks (how to operate each agent), Decision Log (architecture decisions)

#### GitHub (Issues, Projects, Wiki)
**Priority:** **Beginner**

Code, issues, CI/CD — the center of your dev workflow. GitHub MCP → agents create PRs, review code. GitHub Actions → automated testing, deployment. GitHub Projects → kanban for tasks.

#### Linear
**Priority:** **Beginner**

Fast, keyboard-driven project management. **Use Cases:** Engineering teams, sprint planning, issue tracking

#### Obsidian
**License:** Proprietary (free personal use) | **Priority:** **Beginner**

Local-first knowledge management (Markdown). **AI OS Integration:** Local vault → RAG pipeline → AI answers questions about your notes

---

### 10.17 Recommended Tech Stacks

#### Stack A: Personal AI OS (Core Setup)
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

#### Stack B: RAG Application
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

#### Stack C: Full-Stack SaaS
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

#### Stack D: Autonomous Agent System
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

### 10.18 Learning Roadmap

#### Phase 1 — Foundation (Weeks 1–4)
**Goal:** Get your AI OS running locally
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

#### Phase 2 — Building (Weeks 5–10)
**Goal:** Ship first AI application
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

#### Phase 3 — Production (Weeks 11–18)
**Goal:** Production-grade agents and systems
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

#### Phase 4 — Scale (Weeks 19+)
**Goal:** Enterprise-grade, self-sustaining system
- [ ] Migrate to Kubernetes (k3s) for orchestration
- [ ] Implement Temporal for durable long-running workflows
- [ ] Build A2A (Agent-to-Agent) communication
- [ ] Set up DSPy for automated prompt optimization
- [ ] Add Keycloak for enterprise SSO
- [ ] Infrastructure-as-code with OpenTofu
- [ ] Multi-region deployment strategy
- [ ] Advanced agent evaluation and regression testing

---

### 10.19 Implementation Priorities

**Week 1: Must Do First**
1. `docker-compose up` with PostgreSQL + Qdrant + Redis + n8n
2. Install Ollama, pull `llama3.1:8b` and `nomic-embed-text`
3. Install OpenCode, connect to Ollama
4. Create first n8n workflow (webhook → LLM → Notion)

**Month 1: Core Stack**
1. FastAPI backend with PostgreSQL
2. First CrewAI multi-agent workflow
3. Langfuse for tracing
4. Next.js frontend deployed to Vercel
5. GitHub Actions CI/CD

**Month 3: Production-Ready**
1. LangGraph stateful agents
2. Qdrant RAG pipeline
3. OpenHands for autonomous tasks
4. Evaluation pipeline
5. Monitoring stack

**Month 6: Full AI OS**
1. Custom MCP servers for your stack
2. LiteLLM gateway for all model calls
3. n8n + Hermes as automation backbone
4. Fully automated testing and deployment

---

### 10.20 Quick Reference: Tool by Category Summary

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

### 10.21 Essential GitHub Repositories

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

## 11. Personal AI OS Architecture

A fully self-hosted, free, laptop-first ecosystem where every AI tool is unified under a single control surface: **OpenCode**.

### 11.1 System Overview

| Layer | Purpose | Tools |
|-------|---------|-------|
| **Control** | Single command interface | OpenCode |
| **Agents** | Autonomous task execution | Hermes, CrewAI, OpenHands |
| **Orchestration** | Workflow automation | n8n |
| **Memory** | Persistent knowledge store | PostgreSQL + pgvector |
| **Knowledge** | Structured notes & docs | Notion (self-hosted alt: AppFlowy) |
| **Code** | Version control & CI | GitHub |
| **Runtime** | Isolated environments | Docker |

#### Design Principles
- **Zero licensing cost** — every tool is free and open-source
- **Laptop-first** — runs on 8GB+ RAM; optimized for resource constraints
- **Offline-capable** — local LLMs via Ollama for air-gapped use
- **Upgrade-ready** — same compose files work on a VPS or home server
- **Single pane of glass** — OpenCode MCP connections touch every service

---

### 11.2 Architecture Diagram

#### High-Level System Architecture
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

#### Data Flow
```
User Types in OpenCode → [Intent Classification via LLM]
    → Code Task → OpenHands → CrewAI (Research) → PostgreSQL → Notion Sync → GitHub Commit → OpenCode Response
    → Automation Task → n8n Webhook Trigger → Hermes Agent (Reasoning) → PostgreSQL → Notion Sync → GitHub Commit → OpenCode Response
```

#### Communication Protocol Map
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

### 11.3 Component Explanations

#### OpenCode — The Command Center
Terminal-based AI coding assistant supporting MCP. Connects to PostgreSQL, GitHub, n8n, file systems, and custom agents — all accessible via natural language inside one terminal session.

**Key capabilities:** Issue natural language commands that route to agents, read/write database via MCP-PostgreSQL, trigger n8n workflows via MCP-HTTP, browse and commit code via MCP-GitHub, access project knowledge via MCP-filesystem.

#### Hermes Agent — Reasoning & Planning Engine
Based on the Hermes series by Nous Research (e.g., `Hermes-3-Llama-3.1`), fine-tuned for function calling, chain-of-thought reasoning, agentic planning, and structured JSON output. Served via Ollama locally, accessed by n8n and CrewAI agents via HTTP.

**Deployment:** `Ollama ──serves──► Hermes Model`, `n8n ──calls──► http://ollama:11434/api/generate`, `CrewAI ──calls──► Ollama OpenAI-compatible endpoint`

#### n8n — Workflow Orchestration Engine
Self-hosted workflow automation acting as trigger hub (webhooks, cron, DB events), agent router (decides which agent handles a task), integration glue (connects GitHub, Notion, PostgreSQL, email), and error handler (catches agent failures and retries or alerts).

#### CrewAI — Multi-Agent Teams
Define crews — groups of agents with different roles (researcher, writer, coder, reviewer) that collaborate on shared tasks.

**Example crews:** Research Crew (Research + Summarizer + Note-Taking), Dev Crew (Planner + Coder + Reviewer), Data Crew (Collector + Analyst + Visualizer)

#### OpenHands — Code Generation & Execution
Autonomous software engineer that writes entire files/applications, executes code in sandboxed Docker containers, browses documentation, fixes bugs autonomously, and runs terminal commands.

#### Notion — Knowledge Management
Human-readable layer of the knowledge base. Agents write summaries, research outputs, and project plans here via the Notion API. **Free self-hosted alternative:** AppFlowy.

#### PostgreSQL — The System Brain Database
Central persistent store for all agent memory, task history, embeddings, and metadata. Extensions: pgvector (vector embeddings), pg_cron (scheduled maintenance), pg_stat_statements (query monitoring).

#### GitHub — Code Repository & CI/CD
Version control for all projects. Used by OpenHands to commit generated code, n8n workflows to trigger on push/PR events, and OpenCode's MCP-GitHub server for direct repo management.

#### Docker — Container Runtime
Runs the entire PAIOS stack in isolated, reproducible containers via a single `docker-compose.yml`.

---

### 11.4 Agent Architecture

#### Agent Hierarchy
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
│ Hermes LLM   │ │  OpenHands  │ │  CrewAI      │
│ - Break tasks│ │  - Write    │ │  Research    │
│ - Make plan  │ │    code      │ │  Crew        │
│ - Prioritize │ │  - Run code │ │  - Gather    │
│              │ │  - Fix bugs │ │    data      │
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

#### Agent Responsibilities

| Agent | Model | Trigger | Responsibility | Output |
|-------|-------|---------|---------------|--------|
| **Planner** | Hermes-3 (Ollama) | Any new task | Break task into subtasks, create execution plan | JSON task plan → PostgreSQL |
| **Coder** | OpenHands + GPT/Claude | Code subtask | Write, test, debug, commit code | Git commit + test results |
| **Researcher** | CrewAI + Hermes | Research subtask | Web search, summarize, extract facts | Markdown report → Notion |
| **Reviewer** | CrewAI | After code/research | Quality check, fact-check, suggest improvements | Review notes → PostgreSQL |
| **Notifier** | n8n built-in | Task completion | Send summary to user via terminal/email/Slack | Notification |
| **Archivist** | n8n + pg functions | Nightly cron | Embed and archive completed task data | pgvector embeddings |

#### Agent Communication Protocol
Agents communicate via: 1. Direct HTTP calls (synchronous), 2. Redis pub/sub (asynchronous, event-driven), 3. PostgreSQL task queue (persistent, durable).

---

### 11.5 Memory Architecture

#### Memory Types
```
┌─────────────────────────────────────────────────────────┐
│                    MEMORY SYSTEM                         │
│  ┌────────────────┐  ┌──────────────┐  ┌─────────────┐  │
│  │  WORKING       │  │  EPISODIC    │  │  SEMANTIC   │  │
│  │  MEMORY        │  │  MEMORY      │  │  MEMORY     │  │
│  │  Redis         │  │  PostgreSQL  │  │  pgvector   │  │
│  │  (In-flight    │  │  tasks +     │  │  (Embedded  │  │
│  │   context)     │  │  history     │  │   knowledge │  │
│  │  TTL: 1 hour   │  │  tables      │  │   chunks)   │  │
│  └────────────────┘  └──────────────┘  └─────────────┘  │
│  ┌────────────────┐  ┌──────────────────────────────┐   │
│  │  PROCEDURAL    │  │  EXTERNAL                    │   │
│  │  MEMORY        │  │  MEMORY                      │   │
│  │  n8n Workflows │  │  GitHub (code history)       │   │
│  │  (How-to-do    │  │  Notion (structured notes)   │   │
│  │   patterns)    │  │  Files (filesystem)          │   │
│  └────────────────┘  └──────────────────────────────┘   │
└─────────────────────────────────────────────────────────┘
```

#### Vector Memory (Semantic Search)
All agent outputs are embedded and stored in pgvector for semantic retrieval:
```sql
SELECT store_memory(content := 'FastAPI handles async routes with async def',
    memory_type := 'technical_fact', source := 'research_agent', project_id := 'proj_abc123');
SELECT * FROM recall_memory(query := 'how to handle async in Python web frameworks',
    limit_n := 5, project_filter := 'proj_abc123');
```

#### Context Window Management
Each agent call constructs its context from: `[System Prompt] + [Recalled Memories (top-5 semantic matches)] + [Recent Task History (last 10 from PostgreSQL)] + [Current Task Details] + [Available Tools (MCP tool list)]`

---

### 11.6 Knowledge Management

#### Knowledge Flow
```
Raw Input (web/file/conversation) → Chunking Service (n8n, 512-token chunks) → Embedding (Ollama nomic-embed-text) → pgvector Storage → Notion (human readable) + PostgreSQL (machine queryable)
```

#### Knowledge Categories

| Category | Storage | Access Pattern |
|----------|---------|---------------|
| Project documentation | Notion/AppFlowy | Human reading + API |
| Code snippets | GitHub | Git + search |
| Research findings | PostgreSQL + Notion | Semantic search + browse |
| Agent decisions | PostgreSQL | Query by task/date |
| Personal notes | Notion/AppFlowy | Manual + API |
| System configs | Files + GitHub | Git versioned |

#### Notion Integration (via n8n)
```
Agent Output → n8n Notion Node (Notion API v1) → Notion Workspace
  📁 Projects/ → 📄 [Project Name] → 🗒️ Research Notes, 💻 Code Decisions, ✅ Task Tracker
  📁 Agent Memory/ → 📄 Daily Logs, 📄 Important Facts
  📁 Knowledge Base/ → 📄 Technical Reference, 📄 How-To Guides
```

**AppFlowy (Self-hosted Notion alternative):**
```yaml
appflowy:
  image: appflowyinc/appflowy_cloud:latest
  ports: ["8080:8080"]
  environment:
    - APPFLOWY_DATABASE_URL=postgres://ai_os:${POSTGRES_PASSWORD}@postgres:5432/appflowy
```

---

### 11.7 Task Orchestration

#### Task Lifecycle
```
[Task Created] → [Queued in PostgreSQL] → [Planner analyzes] → [Subtasks generated] → [Assigned to agents] → [Executed] → [Results aggregated] → [Review pass] → [Stored in memory] → [Notion updated] → [GitHub committed] → [User notified]
```

#### n8n Master Workflow
```
Webhook: POST /webhook/task → [Parse task JSON] → [Switch node: task.type]
  → "code" → [OpenHands API call]
  → "research" → [CrewAI Research Crew API]
  → "plan"/"write"/"default" → [Hermes Ollama API]
  → [Wait for result] → [Store in PostgreSQL] → [Update Notion page] → [Emit completion event via Redis] → [Return result to caller]
```

#### Priority Queue (PostgreSQL-based)
```sql
SELECT * FROM task_queue
WHERE status = 'pending' AND assigned_to = $1
ORDER BY priority DESC, created_at ASC
LIMIT 1
FOR UPDATE SKIP LOCKED;
```

---

### 11.8 Development Workflow

#### Typical Dev Session
1. Open terminal → launch OpenCode
2. Describe task in natural language (e.g., "Implement a FastAPI endpoint for user authentication with JWT")
3. OpenCode routes to Planner Agent via n8n → Planner breaks into subtasks (design DB schema, write auth utilities, write endpoint, write tests, update README)
4. OpenHands executes subtasks sequentially → writes files → runs tests → auto-fixes failures
5. Results committed to GitHub → summary written to Notion → OpenCode shows completion report

#### Git Workflow
```
main (protected) → develop → feature/agent-generated-xxx, feature/agent-generated-yyy, hotfix/agent-fix-zzz
```
All agent commits go to `feature/` branches. You review and merge to `develop`, then `main`.

#### CI Pipeline (GitHub Actions — Free Tier)
```yaml
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
        run: curl -X POST ${{ secrets.N8N_WEBHOOK_URL }}/ci-result -H "Content-Type: application/json" -d '{"status": "${{ job.status }}", "repo": "${{ github.repository }}"}'
```

---

### 11.9 Monitoring and Logging

#### Monitoring Stack (All Free)
| Tool | Purpose | Port |
|------|---------|------|
| **Grafana** | Dashboards and alerts | 3001 |
| **Prometheus** | Metrics collection | 9090 |
| **Loki** | Log aggregation | 3100 |
| **Promtail** | Log shipping | — |
| **cAdvisor** | Container metrics | 8081 |

#### Key Metrics to Track
```
Agent Metrics: tasks_completed_total, task_duration_seconds, task_failure_total, agent_queue_depth
System Metrics: cpu_usage_percent, memory_usage_bytes, ollama_inference_seconds, postgres_query_duration_seconds
n8n Metrics: workflow_executions_total, workflow_error_total, webhook_latency_seconds
```

#### Logging Architecture
```
All Services → stdout/stderr → Docker logs → Promtail → Loki → Grafana (log explorer + alerts)
```
All agent decisions are also logged to PostgreSQL for searchable audit trail:
```sql
INSERT INTO agent_logs (agent_name, task_id, action, reasoning, timestamp)
VALUES ('hermes_planner', $1, 'created_subtask', $2, NOW());
```

---

### 11.10 OpenCode as Command Center

#### MCP Server Map
OpenCode connects to these MCP servers simultaneously:
```json
{
  "mcpServers": {
    "postgres": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-postgres"], "env": { "POSTGRES_CONNECTION_STRING": "postgresql://ai_os:password@localhost:5432/ai_os_db" } },
    "github": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-github"], "env": { "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}" } },
    "filesystem": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-filesystem", "/home/user/projects"] },
    "n8n-http": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-http"], "env": { "BASE_URL": "http://localhost:5678", "API_KEY": "${N8N_API_KEY}" } },
    "memory": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-memory"] },
    "brave-search": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-brave-search"], "env": { "BRAVE_API_KEY": "${BRAVE_API_KEY}" } }
  }
}
```

#### What You Can Say to OpenCode
```bash
"Create a new n8n workflow that monitors my GitHub PRs and summarizes them daily"
"Show me all tasks that failed in the last 24 hours"
"Start a research crew to find the best vector database options in 2025"
"Build a REST API for the task queue schema we designed"
"What did we decide about authentication last week?"
"How many workflows ran today? Any failures?"
"Show me what files the OpenHands agent changed in the last commit"
```

---

### 11.11 Folder Structure

```
~/ai-os/
├── 📄 docker-compose.yml          # Main compose file
├── 📄 docker-compose.dev.yml      # Dev overrides
├── 📄 docker-compose.test.yml     # Test environment
├── 📄 .env                        # Environment variables (gitignored)
├── 📄 .env.example                # Template for env vars
├── 📄 Makefile                    # Shortcut commands
├── 📄 README.md
├── 📁 mcp_servers/                # Custom MCP servers
│   ├── 📄 paios_server.py
│   ├── 📄 requirements.txt
│   └── 📄 Dockerfile
├── 📁 agents/
│   ├── 📁 crewai/                 # CrewAI crews and agents
│   │   ├── 📄 crews.py
│   │   ├── 📄 agents.py
│   │   ├── 📄 tasks.py
│   │   ├── 📄 tools.py
│   │   ├── 📄 api.py
│   │   ├── 📄 requirements.txt
│   │   └── 📄 Dockerfile
│   ├── 📁 hermes/                 # Hermes agent service
│   │   ├── 📄 api.py
│   │   ├── 📄 planner.py
│   │   ├── 📄 memory.py
│   │   ├── 📄 requirements.txt
│   │   └── 📄 Dockerfile
│   └── 📁 openhands/              # OpenHands config
│       └── 📄 config.toml
├── 📁 n8n/                        # Exported n8n workflows
│   ├── 📁 workflows/
│   │   ├── 📄 master_router.json
│   │   ├── 📄 github_monitor.json
│   │   ├── 📄 notion_sync.json
│   │   └── 📄 daily_digest.json
│   └── 📁 credentials/
├── 📁 database/
│   ├── 📄 init.sql
│   ├── 📄 schema.sql
│   ├── 📁 migrations/
│   └── 📁 seeds/
├── 📁 monitoring/
│   ├── 📄 prometheus.yml
│   ├── 📁 grafana/
│   │   ├── 📄 datasources.yml
│   │   └── 📁 dashboards/
│   └── 📄 loki-config.yml
├── 📁 scripts/
│   ├── 📄 setup.sh
│   ├── 📄 backup.sh
│   ├── 📄 restore.sh
│   └── 📄 health-check.sh
├── 📁 projects/
│   └── 📁 [project-name]/
│       └── 📄 .paios.yml
└── 📁 data/                       # Persistent data (gitignored)
    ├── 📁 postgres/
    ├── 📁 redis/
    ├── 📁 n8n/
    ├── 📁 ollama/
    ├── 📁 grafana/
    └── 📁 loki/
```

---

### 11.12 Docker Setup

#### Main docker-compose.yml
```yaml
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
    ports: ["5432:5432"]
    networks: [ai-os-net]
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${POSTGRES_USER:-ai_os}"]
      interval: 10s
      timeout: 5s
      retries: 5

  redis:
    image: redis:7-alpine
    container_name: ai-os-redis
    restart: unless-stopped
    command: redis-server --requirepass ${REDIS_PASSWORD} --maxmemory 512mb --maxmemory-policy allkeys-lru
    volumes: [redis_data:/data]
    ports: ["6379:6379"]
    networks: [ai-os-net]
    healthcheck:
      test: ["CMD", "redis-cli", "-a", "${REDIS_PASSWORD}", "ping"]
      interval: 10s

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
    ports: ["5678:5678"]
    networks: [ai-os-net]
    depends_on:
      postgres: { condition: service_healthy }
      redis: { condition: service_healthy }

  ollama:
    image: ollama/ollama:latest
    container_name: ai-os-ollama
    restart: unless-stopped
    volumes: [ollama_data:/root/.ollama]
    ports: ["11434:11434"]
    networks: [ai-os-net]

  crewai:
    build: { context: ./agents/crewai, dockerfile: Dockerfile }
    container_name: ai-os-crewai
    restart: unless-stopped
    environment:
      OPENAI_API_BASE: http://ollama:11434/v1
      OPENAI_API_KEY: ollama
      POSTGRES_URL: postgresql://${POSTGRES_USER:-ai_os}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB:-ai_os_db}
      REDIS_URL: redis://:${REDIS_PASSWORD}@redis:6379/0
    ports: ["8001:8001"]
    networks: [ai-os-net]

  hermes:
    build: { context: ./agents/hermes, dockerfile: Dockerfile }
    container_name: ai-os-hermes
    restart: unless-stopped
    environment:
      OLLAMA_BASE_URL: http://ollama:11434
      POSTGRES_URL: postgresql://${POSTGRES_USER:-ai_os}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB:-ai_os_db}
      REDIS_URL: redis://:${REDIS_PASSWORD}@redis:6379/0
      MODEL_NAME: ${HERMES_MODEL:-hermes3:8b}
    ports: ["8002:8002"]
    networks: [ai-os-net]

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
    ports: ["3000:3000"]
    networks: [ai-os-net]

  paios-mcp:
    build: { context: ./mcp_servers, dockerfile: Dockerfile }
    container_name: ai-os-mcp
    restart: unless-stopped
    environment:
      N8N_BASE_URL: http://n8n:5678
      N8N_API_KEY: ${N8N_API_KEY}
      POSTGRES_URL: postgresql://${POSTGRES_USER:-ai_os}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB:-ai_os_db}
      HERMES_URL: http://hermes:8002
      CREWAI_URL: http://crewai:8001
      OPENHANDS_URL: http://openhands:3000
    ports: ["8000:8000"]
    networks: [ai-os-net]

  prometheus:
    image: prom/prometheus:latest
    container_name: ai-os-prometheus
    restart: unless-stopped
    command: ['--config.file=/etc/prometheus/prometheus.yml', '--storage.tsdb.path=/prometheus', '--storage.tsdb.retention.time=15d']
    volumes: [./monitoring/prometheus.yml:/etc/prometheus/prometheus.yml]
    ports: ["9090:9090"]
    networks: [ai-os-net]

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
    ports: ["3001:3000"]
    networks: [ai-os-net]

  loki:
    image: grafana/loki:latest
    container_name: ai-os-loki
    restart: unless-stopped
    command: -config.file=/etc/loki/local-config.yaml
    volumes:
      - loki_data:/loki
      - ./monitoring/loki-config.yml:/etc/loki/local-config.yaml
    ports: ["3100:3100"]
    networks: [ai-os-net]

  cadvisor:
    image: gcr.io/cadvisor/cadvisor:latest
    container_name: ai-os-cadvisor
    restart: unless-stopped
    privileged: true
    volumes: [/, /var/run, /sys, /var/lib/docker]
    ports: ["8081:8080"]
    networks: [ai-os-net]
```

#### CrewAI Dockerfile
```dockerfile
FROM python:3.11-slim
WORKDIR /app
RUN pip install --no-cache-dir crewai crewai-tools fastapi uvicorn asyncpg redis psycopg2-binary
COPY . .
CMD ["uvicorn", "api:app", "--host", "0.0.0.0", "--port", "8001"]
```

#### Hermes Agent Dockerfile
```dockerfile
FROM python:3.11-slim
WORKDIR /app
RUN pip install --no-cache-dir fastapi uvicorn httpx asyncpg redis pgvector sentence-transformers
COPY . .
CMD ["uvicorn", "api:app", "--host", "0.0.0.0", "--port", "8002"]
```

#### Makefile Shortcuts
```makefile
.PHONY: up down restart logs pull-models status
up: docker compose up -d
down: docker compose down
restart: docker compose restart
logs: docker compose logs -f --tail=100
pull-models:
	docker exec ai-os-ollama ollama pull hermes3:8b
	docker exec ai-os-ollama ollama pull nomic-embed-text
	docker exec ai-os-ollama ollama pull llama3.2:3b
status: docker compose ps && docker stats --no-stream --format "table {{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}"
backup: ./scripts/backup.sh
health: ./scripts/health-check.sh
init-db: docker exec -i ai-os-postgres psql -U ai_os -d ai_os_db < database/init.sql
```

---

### 11.13 MCP Server Configuration

#### OpenCode Config File
```json
{
  "model": "anthropic/claude-sonnet-4-5",
  "fallback_model": "ollama/hermes3:8b",
  "theme": "catppuccin",
  "mcpServers": {
    "paios": {
      "command": "python",
      "args": ["/home/user/ai-os/mcp_servers/paios_server.py"],
      "env": { "N8N_API_KEY": "${N8N_API_KEY}", "POSTGRES_URL": "postgresql://ai_os:${POSTGRES_PASSWORD}@localhost:5432/ai_os_db" }
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://ai_os:${POSTGRES_PASSWORD}@localhost:5432/ai_os_db"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": { "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}" }
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/home/user/projects", "/home/user/ai-os/n8n/workflows"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

---

### 11.14 Environment Variables

```bash
# ~/ai-os/.env
POSTGRES_USER=ai_os
POSTGRES_PASSWORD=change_me_strong_password_here
POSTGRES_DB=ai_os_db
REDIS_PASSWORD=change_me_redis_password
N8N_ENCRYPTION_KEY=change_me_32_char_encryption_key_
N8N_HOST=localhost
N8N_API_KEY=change_me_n8n_api_key
HERMES_MODEL=hermes3:8b
OPENHANDS_MODEL=hermes3:8b
EMBED_MODEL=nomic-embed-text
GITHUB_TOKEN=ghp_your_github_personal_access_token
GITHUB_USERNAME=your_username
NOTION_API_KEY=secret_your_notion_integration_token
NOTION_DATABASE_ID=your_notion_database_id
GRAFANA_PASSWORD=change_me_grafana_admin_password
ANTHROPIC_API_KEY=sk-ant-your-key-here
OPENAI_API_KEY=sk-your-key-here
LOG_LEVEL=info
ENVIRONMENT=development
TZ=Asia/Kolkata
```

---

### 11.15 Database Schema

```sql
-- Enable required extensions
CREATE EXTENSION IF NOT EXISTS vector;
CREATE EXTENSION IF NOT EXISTS pg_stat_statements;
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

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
    assigned_to   TEXT,
    payload       JSONB DEFAULT '{}',
    result        JSONB,
    summary       TEXT,
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
    embedding     vector(768),
    memory_type   TEXT DEFAULT 'general' CHECK (memory_type IN ('technical_fact','decision','research','code','conversation','general')),
    source        TEXT,
    importance    FLOAT DEFAULT 0.5,
    access_count  INTEGER DEFAULT 0,
    last_accessed TIMESTAMPTZ,
    created_at    TIMESTAMPTZ DEFAULT NOW(),
    expires_at    TIMESTAMPTZ
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

-- Knowledge Base
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

-- Indexes
CREATE INDEX idx_task_status ON task_queue(status);
CREATE INDEX idx_task_assigned ON task_queue(assigned_to, status);
CREATE INDEX idx_task_project ON task_queue(project_id);
CREATE INDEX idx_task_created ON task_queue(created_at DESC);
CREATE INDEX idx_memory_embedding ON memory_store USING hnsw (embedding vector_cosine_ops) WITH (m = 16, ef_construction = 64);
CREATE INDEX idx_kb_embedding ON knowledge_base USING hnsw (embedding vector_cosine_ops) WITH (m = 16, ef_construction = 64);

-- Helper Functions
CREATE OR REPLACE FUNCTION store_memory(
    p_content TEXT, p_memory_type TEXT DEFAULT 'general', p_source TEXT DEFAULT 'system',
    p_project_id UUID DEFAULT NULL, p_task_id UUID DEFAULT NULL, p_importance FLOAT DEFAULT 0.5
) RETURNS UUID AS $$ ... $$ LANGUAGE plpgsql;

CREATE OR REPLACE FUNCTION claim_next_task(p_agent_name TEXT)
RETURNS task_queue AS $$ ... $$ LANGUAGE plpgsql;

-- Views
CREATE OR REPLACE VIEW v_task_dashboard AS ...;
CREATE OR REPLACE VIEW v_agent_stats AS ...;
```

---

### 11.16 Workflow Examples

#### Example: "Build me a REST API" Workflow
```
User in OpenCode: "Build a FastAPI CRUD API for a todo app with PostgreSQL"
→ OpenCode calls PAIOS MCP tool: trigger_task
→ n8n Webhook receives task
→ n8n → Hermes Agent (Planning): responds with subtask plan
→ n8n inserts subtasks into task_queue
→ n8n triggers OpenHands → writes models.py, database.py, main.py, test_main.py → commits to GitHub
→ n8n triggers CrewAI for README → saves to Notion + commits to GitHub
→ All subtasks complete → n8n sends completion summary → OpenCode displays: "API complete! 4 files created, tests passing ✅"
```

#### Example: Daily Research Digest (Cron Workflow)
```yaml
# n8n cron workflow (daily at 8 AM)
Trigger: Schedule (cron: 0 8 * * *)
→ HTTP Node: GET recent GitHub activity
→ Hermes Agent: Summarize changes
→ CrewAI Research Crew: Find related news
→ Merge Node: Combine summaries
→ PostgreSQL Node: Store full report
→ Notion Node: Create daily digest page
→ Redis Publish: "daily_digest_ready"
```

#### Example: GitHub PR Auto-Review
```
GitHub PR opened → GitHub webhook → n8n → fetch PR diff via GitHub API
→ CrewAI Code Review Crew: Security Agent + Style Agent + Logic Agent
→ n8n posts review comment to GitHub PR → Store in PostgreSQL → Update Notion
```

---

### 11.17 Installation Roadmap

#### Phase 0: Prerequisites (Day 1)
```bash
# Install Docker Desktop
# Install Node.js (for MCP servers)
# Install OpenCode: curl -fsSL https://opencode.ai/install | bash
# Install Python 3.11+
# Clone PAIOS repo, copy .env.example to .env, edit with your values
```

#### Phase 1: Core Infrastructure (Day 1–2)
```bash
docker compose up -d postgres redis
make init-db
```

#### Phase 2: Local LLM Setup (Day 2)
```bash
docker compose up -d ollama
make pull-models  # Pulls hermes3:8b, nomic-embed-text, llama3.2:3b
```

**Recommended models by RAM:** 8GB → hermes3:3b, nomic-embed-text | 16GB → hermes3:8b, nomic-embed-text, llama3.2:3b | 32GB+ → hermes3:8b, llama3.1:70b (quantized), nomic-embed-text

#### Phase 3: n8n Setup (Day 3)
```bash
docker compose up -d n8n
# Open http://localhost:5678, create admin account, set up API key
make n8n-import
```

#### Phase 4: Agent Services (Day 4)
```bash
docker compose up -d crewai hermes openhands
```

#### Phase 5: OpenCode + MCP (Day 5)
```bash
npm install -g @modelcontextprotocol/server-postgres @modelcontextprotocol/server-github @modelcontextprotocol/server-filesystem @modelcontextprotocol/server-memory
cd ~/ai-os/mcp_servers && pip3 install -r requirements.txt
opencode  # Test MCP connection: "What is the status of all PAIOS services?"
```

#### Phase 6: Monitoring (Day 6)
```bash
docker compose up -d prometheus grafana loki cadvisor
# Open http://localhost:3001, login: admin / your GRAFANA_PASSWORD
```

#### Phase 7: Full Stack Verification (Day 7)
```bash
make health
# Expected: PostgreSQL ✅, Redis ✅, n8n ✅, Ollama ✅, CrewAI ✅, Hermes ✅, OpenHands ✅, Grafana ✅, Prometheus ✅
```

---

### 11.18 Security Practices

- **Secrets Management:** NEVER commit `.env` to git. Use strong, unique passwords. Rotate secrets every 90 days.
- **Network Security:** Restrict port bindings to `127.0.0.1` in development. For VPS, use firewall (allow only 22, 80, 443).
- **n8n Security:** Enable basic auth. Use webhook authentication with `X-API-Key`.
- **PostgreSQL Security:** Create read-only user for monitoring. Apply principle of least privilege.
- **GitHub Token Scopes:** Required: `repo`, `workflow`. NOT needed: `admin:org`, `delete_repo`.
- **OpenHands Sandboxing:** Runs code in sandboxed Docker containers by default — never on host directly.

---

### 11.19 Backup Strategy

#### Automated Backup Script
```bash
#!/bin/bash
# scripts/backup.sh
BACKUP_DIR=~/ai-os-backups
DATE=$(date +%Y%m%d_%H%M%S)
BACKUP_PATH="$BACKUP_DIR/$DATE"
mkdir -p "$BACKUP_PATH"

# 1. PostgreSQL dump
docker exec ai-os-postgres pg_dump -U ai_os -d ai_os_db --format=custom --compress=9 > "$BACKUP_PATH/postgres.dump"

# 2. n8n data
docker run --rm -v ai-os_n8n_data:/source -v "$BACKUP_PATH":/backup alpine tar czf /backup/n8n_data.tar.gz -C /source .

# 3. n8n workflows (via API)
curl -s http://localhost:5678/api/v1/workflows -H "X-N8N-API-KEY: $N8N_API_KEY" > "$BACKUP_PATH/n8n_workflows.json"

# 4. Environment structure (redacted secrets)
cat .env | sed 's/=.*/=REDACTED/' > "$BACKUP_PATH/env_structure.txt"

# 5. Ollama models list
docker exec ai-os-ollama ollama list > "$BACKUP_PATH/ollama_models.txt"

# 6. Git commit all project files
cd ~/ai-os && git add -A && git commit -m "Auto-backup: $DATE" || true && git push origin main || true

# 7. Compress and clean up (keep last 7 days)
tar czf "$BACKUP_DIR/paios_backup_$DATE.tar.gz" -C "$BACKUP_DIR" "$DATE"
rm -rf "$BACKUP_PATH"
find "$BACKUP_DIR" -name "*.tar.gz" -mtime +7 -delete
```

#### Restore Script
```bash
#!/bin/bash
# scripts/restore.sh BACKUP_FILE
BACKUP_FILE=$1
BACKUP_DIR=/tmp/paios_restore
mkdir -p "$BACKUP_DIR"
tar xzf "$BACKUP_FILE" -C "$BACKUP_DIR"
docker exec -i ai-os-postgres pg_restore -U ai_os -d ai_os_db --clean < "$BACKUP_DIR/postgres.dump"
docker run --rm -v ai-os_n8n_data:/dest -v "$BACKUP_DIR":/backup alpine sh -c "cd /dest && tar xzf /backup/n8n_data.tar.gz"
```

**Backup Schedule:** Add to crontab: Daily at 2 AM, weekly full backup on Sundays.

---

### 11.20 Troubleshooting Guide

#### Common Issues

**Docker services not starting:**
```bash
docker compose logs postgres n8n
df -h && free -h
docker compose restart n8n
docker compose down && docker compose up -d  # Nuclear option
```

**Ollama models are slow:**
```bash
docker exec ai-os-ollama ollama ps
docker exec ai-os-ollama ollama pull hermes3:3b  # Use smaller model
nvidia-smi  # Check VRAM (if GPU available)
```

**PostgreSQL connection refused:**
```bash
docker inspect ai-os-postgres | grep Health
netstat -tlpn | grep 5432
docker exec -it ai-os-postgres psql -U ai_os -d ai_os_db
```

**n8n webhook not responding:**
```bash
curl http://localhost:5678/healthz
curl -X POST http://localhost:5678/webhook/task -H "Content-Type: application/json" -d '{"task": "test"}'
# Check n8n UI → Executions → view failed executions
```

**pgvector search returns empty results:**
```bash
docker exec ai-os-postgres psql -U ai_os -d ai_os_db -c "SELECT COUNT(*) FROM memory_store WHERE embedding IS NOT NULL;"
docker compose logs hermes | grep embed
```

**MCP server not connecting to OpenCode:**
```bash
python3 ~/ai-os/mcp_servers/paios_server.py
cat ~/.config/opencode/config.json
env | grep N8N_API_KEY && env | grep POSTGRES_PASSWORD
opencode --debug
```

**CrewAI timeout on tasks:** Increase Ollama timeout in api.py, use smaller model (hermes3:3b), check Ollama performance.

#### Performance Tuning for Laptops
```bash
# Limit Docker memory per service:
deploy: resources: limits: memory: 2G

# Ollama: reduce context window
OLLAMA_NUM_CTX=2048

# PostgreSQL tuning:
command: postgres -c shared_buffers=256MB -c effective_cache_size=512MB -c work_mem=16MB -c max_connections=20

# Use Hermes 3B instead of 8B on 8GB RAM machines
HERMES_MODEL=hermes3:3b
```

---

### 11.21 Scaling Path

#### Laptop → Home Server → VPS
```
Phase 1: Laptop (8-16 GB RAM, 256-512 GB SSD, 1-2 parallel tasks)
Phase 2: Home Server (32-64 GB RAM, 1-2 TB NVMe, 5-10 parallel tasks)
Phase 3: VPS (16-32 GB RAM, optional GPU, 10+ parallel tasks, 99.9% uptime)
```

#### Additional Free Tools to Extend PAIOS

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

#### Resource Requirements by Scale
| Scale | RAM | CPU | Storage | Monthly Cost |
|-------|-----|-----|---------|-------------|
| Laptop (dev) | 8 GB | 4 cores | 50 GB | $0 |
| Laptop (full) | 16 GB | 8 cores | 100 GB | $0 |
| Home Server | 32 GB | 8+ cores | 500 GB | ~$5/mo (electricity) |
| Small VPS | 16 GB | 6 vCPUs | 200 GB | ~$30/mo (Hetzner) |
| GPU VPS | 32 GB | 8 vCPUs + GPU | 500 GB | ~$100/mo |

#### Quick Reference Card
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

## Closing Note

Your AI OS is not a product — it's a **practice**. The tools above are the scaffolding; your judgment in composing them is the architecture.

**Start small:** Docker + Ollama + n8n + OpenCode running locally is a complete, capable AI workstation in under an hour.

**Scale deliberately:** Add tools only when a real problem demands them. A $5 VPS with Docker Compose handles most personal and small-team workloads.

**Own your data:** Self-host Langfuse, Qdrant, and n8n. Your agent traces, knowledge bases, and workflows are proprietary infrastructure — keep them under your control.

**Build in public:** Share your agent workflows, Notion templates, and n8n flows. The AI OS community grows through shared patterns.

---

*This guide reflects verified public information as of June 2026. Free tier limits, model availability, and benchmark scores change frequently. Always verify with the provider's official documentation before building production systems on free tiers.*

*Sources: Google AI Studio docs, Groq rate limit docs, Cerebras pricing, OpenRouter model list, NVIDIA NIM docs, Artificial Analysis Intelligence Index, SWE-Bench leaderboard, Mistral platform docs, provider announcements, OpenCode docs, Claude Code docs, LangChain docs, n8n docs, CrewAI docs, Qdrant docs, Langfuse docs.*
