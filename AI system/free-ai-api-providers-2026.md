# Free API AI Model Providers — 2026 Reference Guide

> Scope: developer-accessible **free API tiers** only (no local model deployment). Compiled June 2026. Free-tier terms, models, and rate limits change frequently and are revised without notice by providers — treat numeric limits as directional, verify against official docs before building production dependencies.

---

## 1. Provider Profiles

### Cerebras

**Type:** Inference provider (custom Wafer-Scale Engine silicon; hosts open-weight models, does not develop its own LLMs for general chat).

**Free API offering:** [Certain] 1,000,000 tokens/day, no credit card, instant key via `cloud.cerebras.ai`. Requests per minute: 30. Requests per day: 1,000,000 tokens/day. Tokens per minute: 60,000–100,000.

**Available free models:** [Likely] Llama 3.1 70B / 405B, Llama 3.3 70B, Llama 4 Scout (large context), Qwen3 32B, DeepSeek R1 Distill variants. Cerebras supports Llama 4 Scout (10M context), Qwen3 32B (multilingual), Llama 3.1 70B and 405B, and DeepSeek R1 Distill (reasoning). No frontier proprietary models.

**Context limits:** [Certain] Free tier context is capped well below model maximums — a temporary 8,192 token context cap across all free-tier models as of April 2026.

**Strengths:** By far the fastest raw inference speed of any free tier — up to 20x faster throughput than NVIDIA on key large models, with 2,600 tokens/sec on Llama 4 Scout. Highest daily token ceiling among free tiers.

**Weaknesses:** 8K context cap is a hard architectural constraint for RAG/agentic workloads needing long context. 30 RPM is restrictive for chatty agent loops. No proprietary frontier models. [Guessing] Waitlist/approval friction has been reported for some account types, though most current guides describe instant signup.

---

### Groq

**Type:** Inference provider (LPU hardware; open-weight models only, no proprietary models).

**Free API offering:** [Certain] No credit card required, full model catalog accessible. Rate-limited to 30 requests per minute, 6,000 tokens per minute, and 14,400 requests per day. Limits apply at the organization level, multiple API keys don't help. Per-model limits vary — llama-3.3-70b-versatile is listed at 30 RPM, 1K RPD, 12K TPM, and 100K TPD, while openai/gpt-oss-120b is listed at 30 RPM, 1K RPD, 8K TPM, and 200K TPD.

**Available free models:** [Likely] Llama 3.1/3.3 family, Llama 4 Maverick/Scout, Qwen3 32B, GPT-OSS 120B/20B, DeepSeek R1 distillations, Gemma 2 9B, Whisper (audio). Gemma 2 9B is unique at 30 RPM / 15,000 TPM (2.5x higher) / 1,000 RPD with smaller 8K context. Llama 4 Maverick runs at half quota: 15 RPM / 3,000 TPM / 500 RPD.

**Strengths:** Best latency/throughput-per-dollar for open models; 300-1,000 tokens per second on its custom LPU hardware. OpenAI-compatible API, drop-in for most tooling.

**Weaknesses:** TPM caps (often 6K-12K) are the real binding constraint, not RPM — openai/gpt-oss-120b at 2,000 total tokens per call is about 100 calls/day before hitting 200K TPD. Open-source only — no GPT/Claude/Gemini access.

---

### Mistral

**Type:** Model developer + inference provider (La Plateforme, EU-hosted).

**Free API offering:** [Likely] "Experiment" free tier via `console.mistral.ai`, phone verification required, no credit card. The free tier allows approximately 1 billion tokens/month with a limit of ~1 request/second. [Guessing] Some sources describe a much tighter ~25 messages/day cap on certain models via consumer-linked access — treat the 1B tokens/month figure as the API-key "Experiment" plan and verify current limits at signup, since reports diverge.

**Available free models:** [Likely] Mistral Small, Mistral Medium 3, Mistral Large (rate-limited), Codestral, Ministral edge models. Mistral Large 2 supports a 128K token context window. Codestral is tuned for 32K context, optimized for repository-level code completion.

**Strengths:** Native GDPR compliance and EU data residency; a full open-weight model family you can later self-host with zero marginal API cost; Codestral is a genuinely strong dedicated coding model.

**Weaknesses:** Mistral Large generally trails GPT-5-class and Claude Sonnet-class models on the hardest benchmarks (complex math, advanced reasoning); only Large 3 supports vision, no audio or video input. [Guessing] Free-tier data may be used for model improvement unless you opt out.

---

### Nvidia (NIM / build.nvidia.com)

**Type:** Aggregator / inference platform (hosts third-party open-weight models on NVIDIA-optimized infrastructure; does not primarily develop the LLMs it serves, with the exception of its Nemotron line).

**Free API offering:** [Likely] Free NVIDIA Developer Program signup, no credit card. You get 1,000 inference credits on signup (up to 5,000 on request) and a 40 requests-per-minute rate limit. No quota limits beyond RPM — default 40 RPM, can apply for 200 RPM upgrade.

**Available free models:** [Likely] Very broad catalog — 46+ models from 12 publishers including MiniMax M2.7, Qwen3 Coder 480B, Mistral Large 3 675B, Meta's Llama 4 Maverick, plus NVIDIA's own Nemotron series. A subset of models (including the GLM family) don't consume the credit balance at all.

**Context limits:** Varies per model, generally matches upstream model specs (e.g., 128K-1M depending on the hosted model).

**Strengths:** Largest free model catalog of any provider here; OpenAI-compatible; works with Aider, Cline, Continue.dev and proxied Claude Code setups; strong function-calling models (Mistral Nemotron variants).

**Weaknesses:** When credits run out, paid models return HTTP 402; smaller models stay free via base daily quotas but flagship models need additional credit requests. Not Claude or GPT-class quality — strongest for open-weight model access, not frontier reasoning. No single published per-model rate-limit table — NVIDIA does not publish one simple token-price table for all hosted NIM catalog calls, so per-model RPM varies and must be checked individually.

---

### OpenRouter

**Type:** Aggregator (unified API gateway routing to 300+ models across all major labs and open-weight hosts).

**Free API offering:** [Certain] No credit card required. 20 RPM cap is consistent — purchasing credits doesn't unlock higher per-minute throughput on free models. The daily limit is the lever: spending $10 once (it never expires) raises the daily floor from 50 to 1000 forever. No token limits — the restriction is on request frequency, not request size; each request can use the model's full context window.

**Available free models:** [Likely] ~26-29 models tagged `:free`. Free models include Qwen3 Coder, DeepSeek V4 Flash, Llama 3.3 70B, Google Gemma 4 31B, NVIDIA Nemotron 3 Super, and OpenAI GPT-OSS 120B. For documents or long context, Llama 4 Maverick's 1M context window is unmatched at the free tier.

**Strengths:** Single API/key for an enormous model roster — best for rapid model-switching and fallback chains. Qwen3 Coder is currently the strongest free coding model on OpenRouter, with a 1M context window and state-of-the-art code generation. DeepSeek V4 Flash is also excellent for reasoning-heavy coding tasks (1M context, native reasoning).

**Weaknesses:** Free models can be removed or adjusted without notice — do not build production apps that depend on a specific free model staying free. 20 RPM applies across *all* free models combined, so multi-model agent fan-out hits the ceiling fast.

---

### Google (Gemini API / AI Studio)

**Type:** Model developer + first-party inference platform.

**Free API offering:** [Likely, with caveats] No credit card for the free tier, but Google has actively reduced limits — Google quietly reduced rate limits across most free tier models in December 2025; rate limits now range from 5-15 requests per minute and 100-1,000 requests per day depending on the model. Pro models moved behind billing — if your project runs on the free tier, you are running on Flash.

**Available free models:** [Likely] Gemini 3 Flash (current recommended free model), Gemini 3.1 Flash-Lite, Gemini 2.5 Flash. Gemini 3.1 Flash-Lite gives 15 RPM — for classification, extraction, or routing rather than long-form reasoning, Flash-Lite buys 50% more throughput on the same free tier.

**Context limits:** [Likely] 1M token context window is standard across Flash models.

**Critical gotcha:** [Certain] Once you enable billing on the Gemini API, the free tier disappears entirely on that project — every call becomes billable from the first token, even calls that would fit inside the free quota. The Flash and Flash-Lite families are what's covered; if you need free testing alongside production, use a separate Google Cloud project for each.

**Strengths:** 1M context at zero cost is unmatched among first-party model developers; multimodal (text, image, some audio); no expiration on the free tier itself.

**Weaknesses:** Pro-tier reasoning models are no longer free; limits can be cut 50-80% without warning, as happened in December 2025; per-project (not per-key) quota means scaling requires multiple GCP projects.

---

### Cohere

**Type:** Model developer (enterprise NLP/RAG focus — Command, Embed, Rerank families).

**Free API offering:** [Certain] Cohere's Trial API key provides 1,000 free API calls per month across all endpoints, with access to all models including Command R+, Rerank 3.5, and Embed 4. Rate limits are 5 calls/minute for Embed and 20 calls/minute for Chat. At 1,000 calls/month, that's about 33 calls per day — enough to evaluate, not enough for ongoing use.

**Critical restriction:** [Certain] Trial API keys cannot be used for production or commercial purposes.

**Strengths:** Embed v4 and Rerank are genuinely best-in-class for RAG pipelines — Embed v3 feeds a vector store, Rerank v3 boosts top-K precision, and Command R/R+ generate grounded answers with inline citations.

**Weaknesses:** Far too low-volume for any sustained agent use; explicitly non-commercial trial; Command R+ pricing once you go paid ($2.50/$10 per 1M) is mid-pack, not cheap.

**Fit for PAIOS:** Cohere's free tier is realistically only useful as an **embedding/rerank quality benchmark**, not as a production component — your stack already plans pgvector + a free embedding source for the actual RAG layer.

---

### Hugging Face (Inference Providers)

**Type:** Aggregator / hub (routes to many third-party inference backends; also hosts the model/dataset repository itself).

**Free API offering:** [Guessing — documentation is inconsistent] The Hub itself is free and unlimited for browsing/downloading. The Hugging Face Hub is completely free, with unlimited access to thousands of pre-trained AI models and datasets. The hosted Inference API/Inference Providers free quota is described as variable and unpredictable: Hugging Face offers a free tier for their hosted Inference API giving access to thousands of open-source models, best for exploring the ecosystem and prototyping — though free tier performance can be variable. Community reports on rate limits are sparse and largely unanswered even in HF's own forums.

**Strengths:** Unmatched model variety for niche/specialized tasks (translation, NER, sentiment, classification, embeddings) beyond general chat LLMs.

**Weaknesses:** [Likely] Free Inference Providers routing has queue delays, cold-start latency, and inconsistent availability — not suitable as a primary inference path for agent loops. Best treated as a fallback/specialty tool, not a core provider.

---

### Baseten

**Type:** Inference platform / model-hosting infrastructure (primarily for custom and dedicated model deployments, billed on compute).

**Free API offering:** [Guessing] No broadly-advertised standalone "free tier" for general chat-model API access comparable to the others on this list was found in current sources. Baseten's positioning is dedicated GPU deployment (pay-per-compute), typically used once you're past the free-tier-aggregator stage and need dedicated throughput for a specific model.

**Fit for PAIOS:** [Likely] Not a fit for a zero-cost stack. Worth revisiting only if/when "scaling up" moves toward dedicated inference for a specific fine-tuned or self-hosted model — i.e., post-prototype, not part of the current free-tier blueprint.

---

### DeepSeek

**Type:** Model developer + first-party inference API.

**Free API offering:** [Certain] DeepSeek gives 5 million free tokens to new users on sign-up. Their API has no rate limits — they serve every request they can. DeepSeek also offers free unlimited access through chat.deepseek.com. Beyond the grant, pricing is extremely low: V4 Flash at $0.14/$0.28 per million tokens (cache miss/output) — up to 99% cheaper than GPT-5.5.

**Available models:** [Likely] DeepSeek V4 Flash and V4 Pro (replacing V3.2/R1 lineup as of April 2026). V4 ships with a 1M-token context window and unified 384K max output tokens across both thinking and non-thinking modes. Automatic context caching is enabled by default — cache hits cost $0.0028/M on V4 Flash, 98% cheaper than cache miss.

**Migration note:** [Certain] The deepseek-reasoner alias now routes to V4 Flash, not Pro — if you were using deepseek-reasoner for heavy reasoning and want equivalent capability, you need to explicitly switch to deepseek-v4-pro. Old model name aliases (V3.2, R1) reportedly stop working after July 24, 2026, 15:59 UTC, with no extension announced.

**Strengths:** 1M context standard, no rate limits, OpenAI- and Anthropic-compatible endpoints (OpenAI-compatible at the default base URL and Anthropic-compatible at `https://api.deepseek.com/anthropic`). Genuinely strong on coding/agentic benchmarks — V4 scores Codeforces 3,206, described as open-source SOTA in agentic coding.

**Weaknesses:** [Guessing] 5M-token grant is a one-time allowance, not recurring; after that it's pay-as-you-go (albeit very cheap). Data-residency/privacy considerations apply for some users given DeepSeek's origin.

---

### SiliconFlow

**Type:** Aggregator / inference platform (China-based, primarily serves Chinese-developed open models — Qwen, DeepSeek, GLM, Kimi — via unified OpenAI-compatible API).

**Free API offering:** [Likely] ¥14 free credits on signup; some smaller models (e.g., Qwen2.5-7B) are free forever. Free model access varies by model — RPM/TPM and context limits should be checked in the console.

**Strengths:** Optimized inference with low latency and high throughput; unified OpenAI-compatible API across many open-source models. Good China-region access/latency if relevant.

**Weaknesses:** Free allowance is small (~¥14, roughly $2) and model-dependent; documentation is less mature in English than Western aggregators; [Guessing] best treated as a secondary/regional fallback rather than a primary free-tier pillar.

---

### Poe (API)

**Type:** Consumer aggregator app with a developer "Protocol," **not** a general free-inference API in the sense of the other providers.

**Reality check:** [Certain] The Poe Protocol allows developers to host their own bot logic while using Poe as the frontend interface — it functions as a proxy/orchestration layer that manages the API handshake between the user and model providers, rather than giving direct programmatic access to underlying models for arbitrary use. Poe's own free tier is effectively a trial — daily credit limits run out quickly on any model worth using, and responses run noticeably slower through Poe than at native interfaces.

**Fit for PAIOS:** Not recommended as an inference backend for an agentic/RAG stack. It's a consumer multi-model chat product with a bot-hosting protocol, not a drop-in OpenAI-compatible endpoint for model access. **Excluded from the comparison tables below.**

---

### Sarvam (Sarvam AI)

**Type:** Model developer + platform, India-focused (sovereign/Indic-language models and speech APIs).

**Free API offering:** [Likely] All plans include ₹1,000 free credits, with pay-per-use pricing thereafter (Speech-to-Text ₹30/hour, Text-to-Speech ₹15-30/10K chars, Translation ₹20/10K chars). Some sources cite a smaller ₹100 grant — every new user receives ₹100 worth of free credits to explore all APIs — so treat the exact figure as unverified pending console confirmation. [Likely] A separate startup program exists offering larger multi-month credit grants: 6-12 months of credits, matched to scale and usage, for Speech-to-Text, Text-to-Speech, Translation, Chat Completion, and Document Intelligence APIs.

**Available models:** [Likely] Sarvam-M (chat/LLM), open-sourced Sarvam 30B/105B base models, Bulbul (TTS), Saaras/Saarika (STT/translation) — conversational agents fluent across 22 Indian languages.

**Strengths:** Unmatched for Indic-language tasks (Hindi, Tamil, Telugu, Bengali, etc., plus code-switching) — no Western provider matches this depth.

**Weaknesses:** Free credits are small and one-time; general (English/global) reasoning and coding quality not competitive with Western frontier-adjacent free models. INR billing is a plus for Indian developers specifically but irrelevant for general-purpose PAIOS reasoning/coding tasks.

**Fit for PAIOS:** [Likely] Niche component — useful *only* if a specific Indic-language or voice/translation feature is on the roadmap. Not a general reasoning/coding provider.

---

### OpenCode Go

**Type:** Subscription gateway (run by the OpenCode team), **not a free API tier** — included here because it was requested, but it does not fit the "free API" framework of the other 13 providers.

**Reality:** [Certain] OpenCode Go gives you access to these models for $5 for your first month, then $10/month. Limits are defined in dollar value — your actual request count depends on the model you use; cheaper models like DeepSeek V4 Flash allow more requests, higher-cost models like GLM-5.1 allow fewer. It provides generous limits and reliable access to the most capable open-source models: Big Pickle and free models, GLM-5.1, Qwen3.7 Max, Kimi K2.7 Code, MiMo-V2.5-Pro, DeepSeek V4 Pro, Qwen3.7 Plus, MiniMax M3, MiMo-V2.5, DeepSeek V4 Flash.

**The one actually-free component:** [Certain] "Big Pickle" remains available as a free model, suitable for simple code reviews, once your Go quota is exhausted.

**Fit for PAIOS:** Excluded from the zero-cost comparison tables. If Manoj is willing to spend $10/month, Go is a reasonable *coding-agent-specific* supplement (one key, 14 curated coding models, zero-retention policy per the providers follow a zero-retention policy, meaning your code does not get used for training) — but it competes with, rather than complements, the "zero paid APIs" constraint.

---

### OpenCode Zen

**Type:** Pay-as-you-go curated model gateway (also run by the OpenCode team) for premium models (GPT, Claude, Gemini, etc.) at cost-plus pricing.

**Reality:** [Certain] Zen is a pay-as-you-go service offering curated, tested models from OpenAI, Anthropic, Google, and other providers — charged per request, with credits added to your account. Credit card fees are passed along at cost (4.4% + $0.30 per transaction); the only markup is to cover processing fees.

**Free component:** [Certain, but time-limited] DeepSeek V4 Flash Free is available on OpenCode for a limited time.

**Fit for PAIOS:** Excluded from the zero-cost tables for the same reason as Go — it's a pass-through billing layer for premium models, not a free tier. The single free DeepSeek V4 Flash offering is redundant with DeepSeek's own free grant and OpenRouter's `:free` DeepSeek V4 Flash, both already covered above.

---
