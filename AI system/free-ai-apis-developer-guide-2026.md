# Free AI APIs for Developers: The Definitive 2026 Guide

> **Data current as of June 2026.** Free tiers change frequently. Always verify limits at provider dashboards before building production pipelines.

---

## Table of Contents

1. [Quick Reality Check](#quick-reality-check)
2. [Provider Profiles](#provider-profiles)
3. [Model Capability Evaluations](#model-capability-evaluations)
4. [Use-Case Rankings (Top 3 per category)](#use-case-rankings)
5. [Comparison Tables](#comparison-tables)
6. [Recommendations](#recommendations)
7. [Practical Stacks](#practical-stacks)
8. [Final Decision Matrix](#final-decision-matrix)

---

## Quick Reality Check

Before you read anything else: **free API tiers in 2026 are real but stratified.** There are three tiers of "free":

| Tier | What It Means | Examples |
|------|--------------|---------|
| **Permanently free** | No expiry, no card, rate limits only | Google AI Studio (Flash), Groq, Cerebras, NVIDIA NIM |
| **Trial credits** | One-time budget that exhausts | DeepSeek ($5M tokens), Sarvam (₹100), SiliconFlow (¥14) |
| **Restricted free** | Evaluation-only, no commercial use | Cohere (1,000 calls/month) |

**The hidden cost of "free":** Most providers allow Google or OpenAI to use your prompts for model training on free tiers. If data privacy matters, check terms before building.

---

## Provider Profiles

### 1. Cerebras

**Type:** Inference provider (custom hardware, not a model creator)
**Model creators hosted:** Meta (Llama), Alibaba (Qwen), DeepSeek

**Free Tier:**
- 1,000,000 tokens/day — the highest daily token volume of any free LLM API as of 2026
- No credit card required, no expiry
- 30 requests/minute, 60,000–100,000 TPM
- Context cap: currently 8,192 tokens on free tier (temporary limitation being expanded)
- Models: Llama 4 Scout, Qwen3 32B, Llama 3.1 70B/405B, DeepSeek R1 Distill

**Inference speed:** 2,600+ tokens/second on Llama 4 Scout — among the fastest hosted inference available.

**Strengths:**
- Most generous daily token budget of any free tier
- Exceptional raw speed (Wafer-Scale Engine chips)
- OpenAI-compatible endpoint

**Weaknesses:**
- 8K context cap on free tier is a hard ceiling for long-context tasks
- No proprietary frontier models (no GPT, Claude, Gemini)
- Model catalog changes without notice
- Groq edges it out on per-minute burst speed

**Best for:** High-volume classification, summarization pipelines, daily report automation, anything needing fast inference at scale within short context.

---

### 2. Cohere

**Type:** Model creator AND inference provider
**Notable models:** Command R, Command R+, Command A, Embed 4, Rerank 3.5

**Free Tier:**
- Trial API key: 1,000 API calls/month across all endpoints
- Rate limits: 5 calls/minute (Embed), 20 calls/minute (Chat)
- Includes Command R+, Rerank 3.5, Embed 4
- **No commercial use** — evaluation only
- No card required

**Strengths:**
- Only provider with native RAG stack (Embed + Rerank + Command) on one API
- Command R+ is genuinely strong at grounded, citation-aware generation
- Embed v3 and Rerank v3.5 are industry-leading for retrieval
- Good multilingual embeddings

**Weaknesses:**
- 1,000 calls/month is extremely tight — it's purely for evaluation, not development
- No commercial use on trial key
- Not competitive for raw general reasoning vs. DeepSeek or Gemini
- Command A Reasoning requires contacting sales even for paid access

**Best for:** Evaluating RAG pipelines, testing retrieval quality, enterprise teams scoping an NLP stack. Not useful for production anything on free tier.

---

### 3. Groq

**Type:** Inference provider (custom LPU hardware)
**Model creators hosted:** Meta, DeepSeek, Mistral, Google, Qwen

**Free Tier:**
- No credit card required
- Rate limits are **per model** (tracked independently):
  - Most models: 30 RPM / 6,000–12,000 TPM / 1,000 RPD
  - Llama 4 Maverick: 15 RPM / 3,000 TPM / 500 RPD (deprecated in some regions)
  - Gemma 2 9B: 30 RPM / 15,000 TPM / 1,000 RPD (8K context only)
- Free models: Llama 3.3 70B, Llama 3.1 8B, Llama 4 Scout, DeepSeek R1 Distill 70B, Mistral Saba 24B, Qwen QwQ 32B, Gemma 2 9B, Allam 2 7B, GPT-OSS 120B
- Limits reset daily at midnight UTC

**Inference speed:** 300–1,000+ tokens/second on LPU hardware — typically the fastest hosted inference available.

**Strengths:**
- Fastest inference on the market (sub-200ms TTFT on most models)
- Very broad free model catalog
- Per-model limits mean you can stack models (1,000 RPD on Llama 70B AND 1,000 RPD on DeepSeek R1 simultaneously)
- OpenAI-compatible, no card, excellent latency

**Weaknesses:**
- 6,000 TPM is the most binding limit — large context requests exhaust it in minutes
- Open-source only — no GPT, Claude, Gemini
- 1,000 RPD cap is tight for multi-user apps
- Rate limits were reduced in 2026 from previous higher limits

**Best for:** Latency-critical prototypes, real-time chat, voice AI frontends, coding assistants, anything where speed is the primary requirement.

---

### 4. Mistral AI

**Type:** Model creator AND inference provider (European-based)
**Notable models:** Mistral Large 3, Mistral Small 4, Mistral Medium 3, Codestral, Devstral, Pixtral, Mistral Nemo

**Free Tier:**

*La Plateforme API (developer API):*
- Experimental/free access to select models with 1 RPS, 500K TPM
- Devstral Small 2505: **currently $0 per token** via API (effectively free)
- Mistral Small 4: free tier with basic limits
- Mistral Medium 3: free evaluation access
- Context: up to 256K tokens depending on model
- No card required for API key; evaluation-grade limits

*Le Chat (chat interface — not a developer API):*
- ~25 messages/day soft cap
- Access to Mistral Medium and Small models
- Not usable for programmatic integration

**Strengths:**
- EU-based, GDPR-friendly, strong data privacy posture
- Devstral is purpose-built for software engineering agents (genuinely strong at SWE-bench)
- Codestral is among the best purpose-built coding models
- Apache 2.0 licensed open weights for most models
- Mistral Nemo is the cheapest production API at ~$0.02/M input tokens when you upgrade

**Weaknesses:**
- Free API limits are genuinely tight for development — 1 RPS burns fast
- Codestral through API is **not covered** by any subscription — billed separately
- Le Chat free doesn't give you programmatic API access
- Smaller ecosystem and community than OpenAI or Anthropic

**Best for:** European developers needing data sovereignty, software engineering agents (Devstral), coding workflows (Codestral), and teams who need OpenAI parity at lower cost on paid tiers.

---

### 5. NVIDIA (NIM — NVIDIA Inference Microservices)

**Type:** Infrastructure/inference provider (not a model creator for LLMs)
**Model creators hosted:** Meta, Mistral, DeepSeek, Qwen, MiniMax, GLM/Z.AI, Google (Gemma), NVIDIA (Nemotron)

**Free Tier (build.nvidia.com):**
- NVIDIA Developer Program membership required (free, email only, no card)
- ~40 requests/minute rate limit (can apply for 200 RPM upgrade)
- Credit-based system (credits consumed per request, model-dependent)
- 100+ models available including: Llama 4 Maverick, Qwen3 Coder 480B, Mistral Large 3 675B, MiniMax M2.7, Nemotron 3 Super 120B, DeepSeek R1 671B, Gemma 4 31B, GLM-5 744B
- No hard daily token limit published — credits are the constraint
- No commercial production guarantees on free tier

**Strengths:**
- Largest free model catalog of any provider (100+)
- Includes genuinely frontier-class open-weight models at no cost
- Same OpenAI-compatible API interface used in self-hosted NIM containers
- Unique access to very large models (671B, 744B parameters) on free tier
- Domain-specific models: protein folding (BioNeMo), speech (Riva), weather (FourCastNet)

**Weaknesses:**
- Credit quota is opaque — hard to predict when you'll exhaust it
- No SLA, no production guarantees
- 40 RPM will bottleneck automated pipelines
- The free tier is explicitly a funnel to NVIDIA AI Enterprise ($4,500+/GPU/year)
- Prompts may be logged for abuse prevention

**Best for:** Exploring large open-weight models (especially 100B+ range), benchmarking, enterprise POCs before self-hosting on NIM, researchers needing access to specialized models.

---

### 6. OpenRouter

**Type:** Aggregator/router (not a model creator, not an inference provider)
**Model creators routed to:** 60+ providers including OpenAI, Anthropic, Google, Meta, DeepSeek, Mistral, xAI, and more

**Free Tier:**
- No credit card for API key
- 28+ models available with `:free` suffix (e.g., `deepseek/deepseek-r1:free`)
- Rate limit: 20 RPM on free model variants
- Daily limit: **50 requests/day** without any paid balance; raises to **1,000/day** after purchasing $10+ of credits once (never expires)
- Free models as of June 2026 include: DeepSeek R1, Llama 4 Scout (1M context), Llama 3.3 70B, Qwen3 Coder 480B, GPT-OSS 120B, Gemma 3/4, NVIDIA Nemotron Super
- BYOK (Bring Your Own Key): 1M free routing requests/month when using your own provider keys; 5% fee thereafter
- A new `openrouter/free` router auto-selects from free pool (launched Feb 2026)

**Strengths:**
- Single API key to access 300+ models from 60+ providers
- Best tool for A/B testing models or building provider-agnostic apps
- Free tier includes genuinely strong frontier-class open models
- Llama 4 Maverick's 1M context window available free
- Model fallbacks and routing logic built in

**Weaknesses:**
- 50 RPD base limit is the tightest of any major provider without paying first
- Free models can be removed without notice — don't hard-code them in production
- 5.5% fee on paid usage adds up
- Shared infrastructure means variable latency
- Privacy: prompts forwarded to upstream providers, each with their own data policies
- The `openrouter/free` router gives non-deterministic outputs (model changes request-to-request)

**Best for:** Exploring and comparing models, building provider-agnostic applications, teams that want one integration for the entire model ecosystem.

---

### 7. Google (AI Studio / Gemini API)

**Type:** Model creator AND inference provider
**Notable models:** Gemini 2.5 Flash, Gemini 2.5 Flash-Lite, Gemini 3 Flash, Gemini 3.1 Flash-Lite (free); Gemini 2.5 Pro, Gemini 3.1 Pro (paid-only as of April 2026)

**Free Tier:**
- No credit card required through AI Studio
- **Gemini 2.5 Flash:** 1,500 RPD / 15 RPM / 1,000,000 TPM
- **Gemini 2.5 Flash-Lite:** 1,500 RPD / 30 RPM / 1,000,000 TPM
- **Gemini 2.5 Pro:** 50 RPD / 5 RPM (heavily restricted; effectively testing-only)
- **Gemini 3 Flash / 3.1 Flash-Lite:** Available free with similar Flash limits
- Context: 1M tokens (Flash models), 2M tokens (Pro, paid only)
- **Caveat:** Google may use free-tier prompts for model training. Paid/Vertex AI does not.
- Limits reset at midnight Pacific Time

**History note:** Google cut free limits by 50–92% in December 2025. Pro models moved fully behind billing in April 2026. Flash remains the free workhorse.

**Strengths:**
- 1M TPM is by far the most tokens/minute available on any free tier
- 1,500 RPD is the highest request count of any free LLM provider
- Gemini 2.5 Flash is genuinely strong — competitive with mid-tier paid models on many tasks
- Native multimodal (vision, audio, video) on Flash
- Best free tier for sustained daily volume after Cerebras' token ceiling
- Context window of 1M tokens on Flash (even on free tier)

**Weaknesses:**
- Pro models gone from free tier — you lose access to the best Google reasoning model
- Google owns your prompts on free tier (training data policy)
- 15 RPM on Flash is low — bursting a pipeline hits it fast
- Reliability has been inconsistent during traffic spikes
- Gemini model naming is confusing (Flash, Flash-Lite, Pro, Ultra, 2.5, 3.0, 3.1...)

**Best for:** High-volume applications, multimodal pipelines, long-document processing, the single best permanent free tier for developers who need volume over latency.

---

### 8. Hugging Face

**Type:** Platform/community hub (not a primary model creator, not an inference provider — routes to inference providers)
**Model creators hosted:** Thousands (community + labs)

**Free Tier (three separate products):**

*Serverless Inference API:*
- Free to all registered users
- A few hundred requests/hour (dynamically adjusted, not published)
- Limited to models ~<10B parameters on free tier
- Cold starts on unpopular models: 10–30 seconds
- $0.10/month in Inference Provider credits included

*Inference Providers (Groq, Together, Fireworks, Cerebras, etc.):*
- Routes to third-party providers using your HF account
- Rate limits follow the upstream provider
- More reliable than Serverless for popular models

*ZeroGPU (Spaces):*
- Shared GPU pool for Spaces apps
- Free: ~3.5 minutes/day GPU time
- PRO ($9/month): 25–40 minutes/day with priority

**Strengths:**
- Access to 2M+ models including niche, fine-tuned, and domain-specific ones
- Best platform for model evaluation and research
- Inference Providers gives unified access to multiple backends
- No credit card for base access
- Largest open model community and ecosystem

**Weaknesses:**
- Free Serverless API is too unreliable for production (unpredictable latency, cold starts)
- Rate limits are not published — discovered empirically
- Popular models have long queue times (30 seconds to minutes)
- Free tier is not suitable for any latency-sensitive or production use
- PRO required for meaningful GPU access

**Best for:** Model exploration, research, fine-tuning evaluation, accessing long-tail specialized models not available elsewhere.

---

### 9. Baseten

**Type:** ML deployment platform (not a model creator)
**Notable feature:** Deploy custom models, including fine-tuned ones

**Free Tier:**
- Baseten has historically offered startup credits and a free trial but does **not** maintain a permanent, documented free inference tier comparable to Groq or Google
- New accounts may receive limited trial compute
- Primary value is in production deployment, not free inference
- The free tier is not competitive with Groq, Cerebras, or Google for zero-cost model access

**Strengths:**
- Excellent for deploying private/custom model weights
- Production-grade infrastructure
- Truss framework for model packaging

**Weaknesses:**
- Not a genuine free API tier for most developers
- Requires paid plans for meaningful use
- Not suitable for developers seeking free LLM access — use Groq or NVIDIA NIM instead

**Verdict:** Baseten's strength is in custom model deployment, not free access. Do not include it in your free-tier stack unless you specifically need to self-host a fine-tuned model.

---

### 10. DeepSeek

**Type:** Model creator AND inference provider (Chinese lab)
**Notable models:** DeepSeek V4 Flash, DeepSeek V4 Pro, DeepSeek R1 (reasoning), DeepSeek Coder V2

**Free Tier:**
- New accounts: **5 million free tokens** as granted credits (does not expire on use, consumed first before paid balance)
- After credits: paid tier starts at $0.14/M input (V4 Flash) — cheapest frontier API
- No hard rate limit published; official docs say "serve every request we can" within concurrency limits (10–30 RPM typical)
- Context: 64K–1M tokens depending on model
- Model names `deepseek-chat` and `deepseek-reasoner` will alias to V4-Flash modes after July 2026

**Access note:** DeepSeek is also available via OpenRouter (`:free` variants), SiliconFlow, and other aggregators — often the better choice for non-Chinese developers due to latency.

**Strengths:**
- V4 Pro is among the top 3 open-weight coding models available
- R1 reasoning model is competitive with o1/o3 on math and science
- Among the cheapest frontier-quality APIs when paid credits kick in
- Open weights available for self-hosting (V4, R1)
- Very fast inference on direct API (Chinese users); international latency varies

**Weaknesses:**
- Service reliability issues (downtime during high demand)
- International latency can be high — routing through OpenRouter/SiliconFlow often better
- Data privacy concerns for enterprise use (Chinese jurisdiction)
- Free credits exhaust; then requires funding an account
- Context window limits can surprise you (some models cap at 64K not 1M)

**Best for:** Researchers needing frontier reasoning (R1), developers wanting the cheapest path to GPT-4-class quality (V4 Flash/Pro), open-source enthusiasts who can self-host.

---

### 11. SiliconFlow

**Type:** Inference provider/aggregator (Chinese cloud)
**Model creators hosted:** DeepSeek, Qwen, Meta, Mistral, GLM, MiniMax, and many others

**Free Tier:**
- ¥14 (~$2) in free credits on signup (effectively trial credits)
- Some smaller models (e.g., Qwen2.5-7B, DeepSeek-R1-Distill-Qwen-7B) are **permanently free**
- Free models: 30 RPM, 60,000 TPM
- Context: 131K tokens on free models
- 200+ models available in catalog; free subset is smaller
- OpenAI-compatible API; good accessibility from mainland China

**Strengths:**
- Primary value for Chinese developers who can't access Groq/Google AI Studio reliably
- 200+ model catalog including many Chinese-lab models not available elsewhere
- Very low paid pricing when credits run out
- Free models cover basic Qwen and DeepSeek distill variants
- OpenAI SDK compatible

**Weaknesses:**
- ¥14 credits deplete quickly; not a genuine permanent free tier
- Free permanent models are small (7B range) — limited capability
- Chinese infrastructure; higher latency for non-Chinese developers
- Less documentation in English
- Not competitive for non-Chinese developers vs. Groq/Cerebras/Google

**Best for:** Chinese developers needing reliable access to Chinese-lab models, teams building for Chinese-language applications, DeepSeek/Qwen access from mainland China.

---

### 12. Poe (by Quora)

**Type:** Consumer AI aggregator with developer API (not a model creator)
**Model creators available:** OpenAI, Anthropic, Google, Meta, Mistral, and 100+ more

**Developer API Access:**
- Poe launched a developer API in 2025 with OpenAI-compatible chat completions endpoint
- **Not free** — usage billed via Poe's point system (subscription or add-on tokens)
- Plans: $4.99/mo (10K pts/day), $19.99/mo (1M pts/month), up to $249.99/mo
- Add-on tokens: $30 per 1M points
- Free account: limited compute points, enough for personal use only
- No true free API tier for production or developer use

**Developer use cases:**
- Build server bots that run inside Poe's platform (distributes to Poe's users)
- Access to 100+ models including multimodal (image, video, voice) via one interface
- Creator monetization: set per-message fees for your bots

**Strengths:**
- Access to proprietary frontier models (GPT-5, Claude, Gemini) via one bill
- Multimodal models (Imagen 4, Veo 3, ElevenLabs) not available elsewhere on free tiers
- Developer bot monetization — can earn from your bots
- OpenAI-compatible API for compatible tools (Cursor, Cline, Continue)

**Weaknesses:**
- No genuine free tier for developer API use
- Point system pricing is opaque and expensive relative to direct APIs
- Data passes through Poe and then the underlying provider
- Not suitable for production apps — use direct APIs for lower cost and more control

**Verdict:** Poe is useful for personal exploration and for building bots distributed to Poe users. It is **not a free developer API** in the same category as the others in this guide. Included here for completeness since it was specifically requested.

---

### 13. Sarvam AI

**Type:** Model creator AND inference provider (Indian-focused)
**Notable models:** Saaras (30B and 105B Indian-language LLMs), Bulbul (speech), Mayura (translation)

**Free Tier:**
- **₹100 (~$1.20) in free credits** on signup — universal, never expire
- Rate limits: 30 RPM (Starter, per API type)
- APIs: Chat completion (Saaras 30B and 105B), Speech-to-Text, Text-to-Speech, Translation, Document Parsing, Vision
- All 22 Indian scheduled languages supported
- Models benchmarked competitively against Gemma 27B, Mistral 32B, Qwen 30B on Indian language tasks

**Pricing when credits exhaust:**
- Input: ₹4/1M tokens; Output: ₹16/1M tokens (Saaras 105B)
- Cheaper smaller variant available
- Speech: ₹45/hour
- Translation: ₹30/10K chars

**Strengths:**
- Only provider with production-grade Indian-language AI (all 22 scheduled languages)
- Voice-first architecture — not an afterthought
- Models specifically trained on Indian linguistic patterns, not translated
- Extremely low cost for Indian-language tasks

**Weaknesses:**
- ₹100 in credits depletes quickly
- Not competitive for general English-language tasks vs. Groq/Google/Cerebras
- Smaller context window (32K for 30B, 128K for 105B)
- Very niche — irrelevant if not building for Indian language users
- Limited developer community outside India

**Best for:** Any application targeting Indian language users (Bharat market), fintech, agritech, healthtech, government services in India. Irrelevant for other use cases.

---

### 14. OpenCode (Go and Zen)

**Clarification:** OpenCode is **not an API provider**. It is an open-source terminal-based AI coding agent (a tool, not an inference service).

- OpenCode supports 75+ LLM providers via their API keys
- **OpenCode itself is free and open-source** (95K+ GitHub stars as of 2026)
- **OpenCode Zen** is a curated list of models verified to work well with OpenCode — these are served via various providers (not OpenCode's own infrastructure)
- Zen free models include: Big Pickle, MiniMax M2.5 Free, MiMo V2, and other free-tier models from underlying providers

**What this means for developers:** You need a third-party free API key (Groq, Cerebras, Google AI Studio, NVIDIA NIM, etc.) to use OpenCode. OpenCode itself costs $0. The LLM inference costs depend on which provider you connect.

**Strengths of OpenCode the tool:**
- Terminal-native with LSP integration
- Multi-session parallel agents
- Supports local models (Ollama) for zero-cost inference
- OpenCode Zen provides curated free-model recommendations

**Does OpenCode provide a developer API?** No. It is a coding assistant client, not a server. It does not belong in the same category as Groq or Cerebras.

---

## Model Capability Evaluations

*Models evaluated are those accessible free-of-charge via the providers above. Ratings: ⭐⭐⭐⭐⭐ = Excellent, ⭐⭐⭐⭐ = Strong, ⭐⭐⭐ = Moderate, ⭐⭐ = Weak, ⭐ = Poor*

### Free Models Assessed

| Model | Via (Free) | Context | Coding | Agentic Coding | Reasoning | Math | Research | Writing | Tool Use | Long-Ctx | Multilingual | Speed |
|-------|-----------|---------|--------|---------------|-----------|------|----------|---------|---------|---------|-------------|-------|
| Gemini 2.5 Flash | Google AI Studio | 1M | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| Gemini 3.1 Flash-Lite | Google AI Studio | 1M | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| DeepSeek R1 (Distill 70B) | Groq, OpenRouter, Cerebras | 128K | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| DeepSeek V4 Flash | DeepSeek (5M credit), OpenRouter | 64K–1M | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| Llama 3.3 70B | Groq, Cerebras, OpenRouter | 128K | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Llama 4 Scout | Groq, Cerebras | 10M | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Qwen3 32B | Groq (QwQ), Cerebras, OpenRouter | 131K | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| Qwen3 Coder 480B | OpenRouter, NVIDIA NIM | 262K | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ |
| Mistral Small 4 | Mistral API (limited free) | 256K | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| Devstral Small | Mistral API (free/$0) | 128K | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| Nemotron 3 Super 120B | NVIDIA NIM | 128K | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| MiniMax M2.7 | NVIDIA NIM | 1M | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| GPT-OSS 120B | Groq, OpenRouter | 128K | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| Command R+ | Cohere (1K calls/month) | 128K | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| Llama 3.1 8B | Groq (instant), Cerebras | 128K | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ |
| Saaras 105B | Sarvam | 128K | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ (Indian langs) | ⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ (Indian) | ⭐⭐⭐ |
| Qwen2.5-7B | SiliconFlow (free perm.) | 131K | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |

---

## Use-Case Rankings

### 🖥️ Coding

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | Qwen3 Coder 480B | OpenRouter (:free), NVIDIA NIM | SWE-bench leader among free models, agentic code loops, 262K context | Slow inference, 20 RPM on OpenRouter, NIM credits limited | Overkill | ✅ Best choice |
| 2 | DeepSeek V4 Flash | DeepSeek (5M credits), OpenRouter | Top-3 coding benchmark scores, fast, 1M context, MIT license | International latency, credits exhaust | ✅ Great | ✅ Strong |
| 3 | Gemini 2.5 Flash | Google AI Studio | 1M context, multimodal code+image, 1,500 RPD, consistent | Not specialized for code, weaker at agentic loops | ✅ Reliable | ✅ Good |

### 🤖 Software Engineering Agents

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | Devstral Small | Mistral API (free/$0) | Purpose-built for SWE agents, trained on software repos, Mistral's tool-use format | Only 128K context, low free throughput, limited agentic loop depth | ✅ Good | ✅ Specialized |
| 2 | Qwen3 Coder 480B | OpenRouter (:free), NVIDIA NIM | Largest open coding model, strong multi-step task completion | Very slow, NIM rate limits bind, not reliable for sustained loops | Overkill | ✅ Capable |
| 3 | DeepSeek V4 Flash | DeepSeek (credits), OpenRouter | Strong agentic planning, reliable tool use, fast | Credits exhaust, latency from China | ✅ Solid | ✅ Capable |

### 🧠 Reasoning

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | DeepSeek R1 (70B Distill) | Groq, OpenRouter (:free) | Chain-of-thought reasoning, competitive with o1 on MATH/AIME, transparent thinking | 128K context only, thinking tokens inflate cost, slow for simple tasks | Overkill | ✅ Excellent |
| 2 | Qwen3 32B (QwQ) | Groq (free), Cerebras | Hybrid thinking/non-thinking modes, MATH benchmark leader in its class | 131K context cap, thinking mode slow | ✅ Good (non-thinking) | ✅ Strong |
| 3 | Gemini 2.5 Flash | Google AI Studio | Strong reasoning with massive 1M context, good at multi-step analysis | Not a dedicated reasoning model, no chain-of-thought transparency | ✅ Reliable | ✅ Good |

### ➕ Mathematics

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | DeepSeek R1 (70B Distill) | Groq, OpenRouter | AIME/MATH benchmark strength, shows work, competitive with o3-mini | Slow for simple arithmetic, context limited | ✅ Fine | ✅ Best |
| 2 | Qwen3 32B (QwQ) | Groq, Cerebras | Strong MATH/AMC scores, thinking mode helps | Thinking mode adds latency | ✅ Good | ✅ Strong |
| 3 | Gemini 2.5 Flash | Google AI Studio | Good math at scale, handles multi-page problem sets via 1M context | Not specialized for competition math | ✅ Reliable | ✅ Capable |

### 🔬 Research & Analysis

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | Gemini 2.5 Flash | Google AI Studio | 1M context for entire papers/codebases, multimodal (PDF+images), 1,500 RPD | May hallucinate citations, privacy concern on free tier | ✅ Excellent | ✅ Best |
| 2 | Llama 4 Scout | Groq, Cerebras | 10M context window (!), strong document recall, fast on Cerebras | Not a reasoning specialist, limited to open weights | ✅ Good | ✅ Long-context champion |
| 3 | DeepSeek R1 (70B Distill) | Groq, OpenRouter | Deep analytical reasoning, great for systematic analysis | Shorter context (128K), slow for rapid-fire queries | ✅ OK | ✅ Deep analysis |

### ✍️ Writing & Content Creation

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | Gemini 2.5 Flash | Google AI Studio | Fluent, coherent long-form content, instruction-following, 1M context | Less personality than Claude/GPT, Google owns prompt data | ✅ Fast and reliable | ✅ Long-form strong |
| 2 | GPT-OSS 120B | Groq, OpenRouter | OpenAI training pedigree, strong instruction following, good style | Not Claude-level nuance; Groq limits are strict | ✅ Good | ✅ Capable |
| 3 | Llama 3.3 70B | Groq, Cerebras | Fast, decent writing quality, very low latency for iterative editing | Lacks personality and polish of frontier models | ✅ Fast iteration | ✅ Acceptable |

### 🔧 Tool Use / Function Calling

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | Gemini 2.5 Flash | Google AI Studio | Native function calling, parallel tool calls, strong JSON adherence | Data privacy on free tier | ✅ Reliable | ✅ Parallel calls |
| 2 | DeepSeek V4 Flash | DeepSeek, OpenRouter | Strong tool call accuracy, good at multi-tool orchestration | Latency for international users | ✅ Good | ✅ Capable |
| 3 | Llama 3.3 70B | Groq | Fast tool dispatch, good JSON formatting, wide tool call compatibility | Less reliable on complex nested tool schemas | ✅ Fast and easy | ✅ Basic pipelines |

### 📄 Long-Context Processing

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | Llama 4 Scout | Cerebras (10M ctx), Groq | 10M token context window — nothing else at free tier comes close | 8K context cap on Cerebras free tier (!); Groq is better for actual long context | N/A | ✅ Unique capability |
| 2 | Gemini 2.5 Flash | Google AI Studio (1M ctx) | Reliable 1M context, high recall fidelity, 1,500 RPD | Google's free-tier data policy | ✅ Most reliable | ✅ Best practical choice |
| 3 | MiniMax M2.7 | NVIDIA NIM (1M ctx) | 1M context, competitive with Gemini on recall | NIM rate limits, credits opaque | N/A | ✅ Strong alternative |

**Note:** Cerebras' 8K free-tier context cap contradicts Llama 4 Scout's native 10M context. To actually use Scout's long context on free, Groq is the better provider (128K context on free tier).

### 🌍 Multilingual Tasks

| Rank | Model | Provider (Free) | Strengths | Weaknesses | Simple Tasks | Complex Tasks |
|------|-------|----------------|-----------|------------|-------------|--------------|
| 1 | Qwen3 32B | Groq (QwQ), Cerebras | Native Chinese/Asian language strength, 29+ languages, strong code+language crossover | Focused on Asian languages; European language support weaker than Gemini | ✅ Excellent (Asian) | ✅ Best for CJK |
| 2 | Gemini 2.5 Flash | Google AI Studio | Strong across 40+ languages, Google's multilingual training, native code-switching | Not specialized; Indian languages weaker than Sarvam | ✅ Best general | ✅ Broad coverage |
| 3 | Saaras 105B | Sarvam | All 22 Indian scheduled languages, native-quality (not translated), voice-optimized | Credits only ₹100; irrelevant outside India | ✅ Indian lang only | ✅ Best for India |

### ⚡ Fast Inference / Low Latency

| Rank | Model | Provider | Speed | Context | Tradeoff |
|------|-------|---------|-------|---------|---------|
| 1 | Llama 3.1 8B | Groq | ~1,000+ TPS, <100ms TTFT | 128K | Weaker capability |
| 2 | Llama 4 Scout | Cerebras | 2,600+ TPS | 10M (8K on free) | Context cap on free |
| 3 | Llama 3.3 70B | Groq | ~300–500 TPS, <200ms TTFT | 128K | Tighter rate limits |

---

## Comparison Tables

### Provider Overview

| Provider | Type | Best Free Models | Max Context (Free) | Speed | Coding | Reasoning | Tool Use | Reliability | Rate Limits | Open-Source | Data Privacy | API Quality |
|---------|------|-----------------|-------------------|-------|--------|-----------|---------|------------|-------------|-------------|-------------|-------------|
| **Google AI Studio** | Creator+Infra | Gemini 2.5 Flash | 1M | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | 1,500 RPD / 15 RPM | No (proprietary) | ⚠️ Trains on free prompts | ⭐⭐⭐⭐⭐ |
| **Groq** | Inference | Llama 3.3 70B, DeepSeek R1 70B, QwQ 32B | 128K | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | 1,000 RPD / 30 RPM | Yes (all) | ✅ Does not train | ⭐⭐⭐⭐⭐ |
| **Cerebras** | Inference | Llama 4 Scout, Qwen3 32B | 8K (free cap) | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | 1M tokens/day | Yes (all) | ✅ | ⭐⭐⭐⭐ |
| **OpenRouter** | Aggregator | DeepSeek R1, Qwen3 Coder 480B, Llama 4 | 1M (Llama 4 Maverick) | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | 50–1,000 RPD / 20 RPM | Yes (free models) | ⚠️ Routes to upstream | ⭐⭐⭐⭐ |
| **NVIDIA NIM** | Infra | Nemotron 3 Super, MiniMax M2.7, Qwen3 Coder | 1M | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | 40 RPM / credits-based | Yes (all) | ⚠️ May log for abuse | ⭐⭐⭐⭐ |
| **Mistral** | Creator+Infra | Devstral Small, Mistral Small 4 | 256K | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | 1 RPS / 500K TPM | Yes (most) | ✅ EU/GDPR | ⭐⭐⭐⭐ |
| **DeepSeek** | Creator+Infra | V4 Flash, R1 | 64K–1M | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ~10–30 RPM (unofficial) | Yes (open weights) | ⚠️ Chinese jurisdiction | ⭐⭐⭐⭐ |
| **Hugging Face** | Platform | Thousands (small models best) | Varies | ⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐ | ~hundreds/hour | Yes (all) | Varies by model | ⭐⭐⭐ |
| **Cohere** | Creator+Infra | Command R+ | 128K | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | 1,000 calls/month | No (proprietary) | ✅ | ⭐⭐⭐⭐ |
| **SiliconFlow** | Infra (CN) | Qwen2.5-7B, DeepSeek Distill 7B | 131K | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | 30 RPM / 60K TPM (free models) | Yes (all) | ⚠️ Chinese jurisdiction | ⭐⭐⭐ |
| **Sarvam** | Creator+Infra | Saaras 105B | 128K | ⭐⭐⭐ | ⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | 30 RPM | Yes (open weights) | ✅ India | ⭐⭐⭐ |
| **Baseten** | Deployment | None (no free inference tier) | N/A | N/A | N/A | N/A | N/A | ⭐⭐⭐⭐ | No free tier | Yes (deployable) | ✅ | ⭐⭐⭐⭐ |
| **Poe** | Aggregator | None (point-based, not free) | Varies | N/A | N/A | N/A | N/A | ⭐⭐⭐ | Subscription only | No | ⚠️ Routes to upstream | ⭐⭐⭐ |

### Rate Limits Snapshot

| Provider | RPM (Free) | RPD (Free) | TPM (Free) | Daily Tokens | Card Required |
|---------|-----------|-----------|-----------|-------------|--------------|
| Google AI Studio | 15–30 | 1,500 | 1,000,000 | ~Very high | No |
| Cerebras | 30 | ~1,400 (30M/mo est.) | 60–100K | 1,000,000 | No |
| Groq | 30 (per model) | 1,000 (per model) | 6,000–15,000 | ~100,000 | No |
| OpenRouter | 20 (free models) | 50–1,000 | Upstream limited | Low | No |
| NVIDIA NIM | 40 | Unlimited (credit-based) | Upstream limited | Credit-based | No |
| Mistral | 60 RPS limit | High | 500,000 | High | No |
| DeepSeek | 10–30 | No published limit | No published limit | 5M token trial | No |
| Cohere | 20 | 1,000 calls/month total | N/A | Low | No |
| SiliconFlow | 30 (free models) | 100 (some models) | 60,000 | Low | No |
| Hugging Face | ~hundreds/hr | No hard limit | Not published | Low | No |
| Sarvam | 30 | Not published | Not published | ₹100 credits | No |

---

## Recommendations

### Best Overall Free Model
**Gemini 2.5 Flash (Google AI Studio)**

Nothing else matches its combination of quality, context length (1M), volume (1,500 RPD), and permanence. The data privacy concern is real but acceptable for most non-sensitive applications.

### Best Overall Free Provider
**Google AI Studio** for volume + quality. **Groq** for speed + privacy + reliability. Use both together.

### Best Coding Model (Free)
**Qwen3 Coder 480B** via OpenRouter or NVIDIA NIM. If rate limits are a problem, use **DeepSeek V4 Flash** via its trial credits or **Gemini 2.5 Flash** as the high-volume fallback.

### Best Reasoning Model (Free)
**DeepSeek R1 Distill 70B** via Groq. Thinking-mode reasoning at free tier, fast via LPU, 1,000 RPD. **Qwen3 32B (QwQ)** via Groq/Cerebras is a close second.

### Best Math Model (Free)
**DeepSeek R1 Distill 70B** via Groq. Shows chain-of-thought work, strong on AIME/MATH benchmarks, transparent reasoning.

### Best Research Model (Free)
**Gemini 2.5 Flash** — the 1M context window is the single most important feature for research (drop entire papers, codebases, datasets), and 1,500 RPD means you can run pipelines. For deep reasoning on shorter documents, pair with DeepSeek R1.

### Best Writing Model (Free)
**Gemini 2.5 Flash** for volume, **GPT-OSS 120B** via Groq for OpenAI-training-pedigree writing style.

### Best Agent Model (Free)
**Devstral Small** (Mistral, free/$0) for software engineering agents. **Qwen3 Coder 480B** for the most capable option when rate limits allow. **Gemini 2.5 Flash** for general-purpose agents that need tool calling + long context together.

### Best Long-Context Model (Free)
**Gemini 2.5 Flash** — 1M tokens is the practical maximum at free tier with reliable recall and 1,500 RPD. **Llama 4 Scout** via Groq (128K on free) or the 10M context via a provider not cap-limiting it.

### Fastest Model (Free)
**Llama 3.1 8B on Groq** — 1,000+ TPS, sub-100ms TTFT. **Llama 4 Scout on Cerebras** at 2,600+ TPS if context requirements are under 8K.

### Best Multilingual Model (Free)
**Qwen3 32B** for Chinese/Japanese/Korean/Asian languages. **Gemini 2.5 Flash** for broadest coverage across 40+ languages. **Saaras 105B** if and only if you need Indian languages.

### Best Open-Source Model (Free)
**DeepSeek R1** (open weights, MIT) and **Qwen3-Coder 480B** (Apache 2.0) for top performance. **Llama 3.3 70B** (Llama license) for the most widely supported and deployable option.

### Best for Startups
**Stack:** Google AI Studio (primary, Gemini 2.5 Flash) + Groq (fallback for speed, DeepSeek R1 for reasoning). Zero cost, no card needed, scales until you're ready to pay.

### Best for Personal Projects
**Cerebras** — 1M tokens/day, no card, high speed. Enough for any personal project that doesn't need frontier reasoning.

### Best for Production Prototypes
**Google AI Studio** — 1,500 RPD, 1M TPM, 1M context, multimodal, stable API. The only free tier realistically suitable for early production traffic. Swap to paid when data privacy matters.

---

## Practical Stacks

### 🤖 Coding Agent Stack

```
Primary model:    Devstral Small (Mistral free/$0)     → Agent backbone, SWE-focused
Fallback/heavy:   Qwen3 Coder 480B (OpenRouter :free)  → Complex multi-file changes
Fast iteration:   Llama 3.3 70B (Groq free)            → Quick completions, fast loops
Execution layer:  OpenCode (open-source tool) + Ollama  → Zero LLM cost for small tasks
```

### 🔬 Research Agent Stack

```
Long-context:     Gemini 2.5 Flash (Google AI Studio)  → Full paper/codebase ingestion
Reasoning:        DeepSeek R1 70B (Groq free)           → Deep analysis, chain-of-thought
Retrieval:        Cohere Embed + Rerank (trial)          → Build the RAG retrieval layer
Orchestration:    1,500 RPD on Gemini = ~100 deep research sessions/day for free
```

### 📋 Productivity Assistant Stack

```
Primary:          Gemini 2.5 Flash (Google AI Studio)  → Writing, summarization, analysis
Speed layer:      Llama 3.3 70B (Groq)                  → Quick Q&A, chat
Specialist:       Qwen3 32B (Groq/Cerebras)             → When user needs math or reasoning
Fallback:         OpenRouter :free router               → Model unavailability hedge
```

### 🕸️ Multi-Agent System Stack

```
Planner:          Gemini 2.5 Flash (1M context, tool calling)
Executor:         Llama 3.3 70B (Groq) — fast loops
Reasoner:         DeepSeek R1 70B (Groq) — complex decisions
Code writer:      Devstral Small (Mistral) — agent code generation
Router:           OpenRouter (single API key for all above if budget tightens)
Cost:             $0 on free tiers for low-volume agents
```

### 💰 Cost-Optimized Startup Stack (Zero to First Revenue)

```
Phase 1 (0 users):
  → Cerebras free (1M tokens/day) for all generation
  → Google AI Studio free for long-context and multimodal
  → Groq free for latency-critical paths
  → Cost: $0

Phase 2 (first users, <10K requests/day):
  → Add DeepSeek V4 Flash (~$0.14/M input) for quality boost
  → Keep Google Flash free for bulk tasks
  → Cost: <$5/month

Phase 3 (scaling):
  → DeepSeek for cost-sensitive paths
  → Claude Haiku 4.5 or Gemini Flash (paid) for quality
  → Cost: scales linearly with usage
```

---

## Final Decision Matrix

| Use Case | Best Free Model | Provider | Best for Simple Tasks | Best for Complex Tasks | Notes |
|---------|----------------|---------|----------------------|----------------------|-------|
| General coding | DeepSeek V4 Flash | DeepSeek (trial) | Gemini 2.5 Flash (reliable) | Qwen3 Coder 480B (NVIDIA/OpenRouter) | V4 Flash is fastest path to strong code; Qwen3 Coder 480B for hardest tasks |
| Agentic software engineering | Devstral Small | Mistral API (free) | Devstral Small | Devstral Small | Only purpose-built SWE agent model available free |
| Chain-of-thought reasoning | DeepSeek R1 70B | Groq | Qwen3 32B (faster) | DeepSeek R1 70B (deeper) | R1 shows its work; better for auditable decisions |
| Competition math | DeepSeek R1 70B | Groq | Qwen3 32B | DeepSeek R1 70B | R1 is the free-tier AIME/MATH leader |
| Research & document analysis | Gemini 2.5 Flash | Google AI Studio | Gemini 2.5 Flash | Gemini 2.5 Flash + R1 for synthesis | 1M context is non-negotiable for full-doc research |
| Writing & content | Gemini 2.5 Flash | Google AI Studio | Gemini 2.5 Flash | GPT-OSS 120B (Groq) | Flash for volume; GPT-OSS for OpenAI-pedigree style |
| Tool/function calling | Gemini 2.5 Flash | Google AI Studio | Llama 3.3 70B (fast) | Gemini 2.5 Flash (parallel calls) | Gemini has native parallel tool calls; Llama fast for simple dispatch |
| Long-context (>128K) | Gemini 2.5 Flash | Google AI Studio | Gemini 2.5 Flash | Gemini 2.5 Flash | Nothing else on free tier handles 1M context reliably |
| Multilingual (global) | Gemini 2.5 Flash | Google AI Studio | Gemini 2.5 Flash | Qwen3 32B (Asian langs) | Flash for 40+ languages; Qwen3 better for CJK specifically |
| Multilingual (India) | Saaras 105B | Sarvam | Saaras 105B | Saaras 105B | Only native option; ₹100 credits are minimal but unique capability |
| Low-latency chat | Llama 3.1 8B | Groq | Llama 3.1 8B | Llama 3.3 70B | 8B for <100ms; 70B for better quality at still-fast speed |
| High-volume pipelines | Gemini 2.5 Flash | Google AI Studio | Gemini 2.5 Flash-Lite | Gemini 2.5 Flash | 1,500 RPD beats every other free tier for request volume |
| RAG / retrieval | Command R+ + Embed | Cohere (1K calls/month) | Cohere Embed+Rerank | Cohere Command R+ | Only provider with full RAG stack on one API; very limited free tier |
| European/privacy-first | Devstral / Mistral Small | Mistral (EU) | Mistral Small 4 | Devstral Small | Only EU-based major provider; GDPR-native |
| Chinese/Asian market | Qwen3 32B | Groq / SiliconFlow | Qwen2.5-7B (SF free) | Qwen3 32B (Groq) | Strong CJK languages; SiliconFlow for China-accessible API |
| Startup zero-budget | Gemini 2.5 Flash | Google AI Studio | Gemini Flash | Cerebras + Groq combo | Flash is the only permanently free tier worth building on |
| Model exploration | Any :free model | OpenRouter | openrouter/free router | Specific :free models | OpenRouter for breadth; spend $10 once to raise daily limit to 1,000 |

---

## Appendix: Provider Legitimacy Check

These providers were listed in the original request. Here's the clarification on which are genuine free API providers:

| Provider | Genuine Free API Tier | Notes |
|---------|----------------------|-------|
| Cerebras | ✅ Yes | 1M tokens/day, permanent |
| Cohere | ⚠️ Evaluation only | 1K calls/month, no commercial use |
| Groq | ✅ Yes | 1K RPD/model, permanent |
| Mistral | ⚠️ Partial | Devstral Small free; other models limited |
| NVIDIA | ✅ Yes | Credits-based, 40 RPM, 100+ models |
| OpenRouter | ✅ Yes | 50–1,000 RPD on :free models |
| Google | ✅ Yes | 1,500 RPD, Flash models only |
| Hugging Face | ✅ Yes (limited) | Unreliable for production; good for exploration |
| Baseten | ❌ No genuine free tier | Custom deployment platform; no free inference |
| DeepSeek | ✅ Trial credits | 5M tokens on signup; not permanent |
| SiliconFlow | ⚠️ Partial | ¥14 trial + small permanent-free models |
| Poe | ❌ Not for developers | Consumer app with API; point-based, not free |
| Sarvam | ⚠️ Trial credits | ₹100 on signup; Indian-language specialist |
| OpenCode (Go/Zen) | N/A — not an API | Open-source coding tool that uses other APIs |

---

*Guide compiled June 2026. Verify all limits at provider documentation before building. Free tiers are the most volatile aspect of the AI API market — providers add, reduce, and remove free access with minimal notice.*
