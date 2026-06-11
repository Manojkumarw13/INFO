# 📚 Quant & AI/Data Science Resource Directory: Master Study Planner
### A Unified Phase-by-Phase Learning Path, Tool Index, and Milestone Tracker (2026 Edition)

Welcome to the **Resources & Study Tracks** master guide. This document provides a highly detailed, data-dense synthesis of the seven files in the `resources/` directory. It acts as an interactive study planner, mapping out curriculums, free textbooks, YouTube playlists, development environments, and tracking milestones across three distinct career tracks: **AI & Data Science (AI/DS)**, **Quantitative Finance (Quant)**, and **Hybrid (AI + Quant)**.

---

## 📖 Navigation Hub & Directory Mapping

The study resource workspace contains seven core research files. Use these links to access the original documentation:

*   **[roadmap_differentiated_tracks.md](roadmap_differentiated_tracks.md)** (~35 KB): The definitive track allocation matrix, prioritizing 200+ topics across the three tracks.
*   **[free_resources_roadmap.md](free_resources_roadmap.md)** (~40 KB): Verified free and legal learning resources (MIT, Stanford, Harvard courses, free PDFs, and documentation).
*   **[youtube-roadmap-deduplicated.md](youtube-roadmap-deduplicated.md)** (~30 KB): Curated YouTube playlists categorized by phase and track.
*   **[career_roadmap_checklist_differentiated.md](career_roadmap_checklist_differentiated.md)** (~4 KB): Interactive milestone checklist sorted by track.
*   **[career-roadmap-checklist.md](career-roadmap-checklist.md)** (~4 KB): Core structural tracking sheet for progress mapping.
*   **[tools-master-list.md](tools-master-list.md)** (~15 KB): Comprehensive index of 109 tools, packages, and frameworks sorted by category.
*   **[notebooklm-compatible-resources.md](notebooklm-compatible-resources.md)** (~60 KB): Clean text summaries of all resources compiled for easy ingestion into Google's NotebookLM.

---

## 🗺️ Chronological Learning Lifecycle (8 Phases)

Your study journey is structured into 8 progressive phases over a 12-to-18-month horizon:

```
[ Phase 1: Bedrock Math & DSA ] ──► [ Phase 2: Quant & Markets ] ──► [ Phase 3: Classical ML ] ──► [ Phase 4: Deep Learning & NLP ]
  Months 1–4 (Python, Stats, C++)     Months 4–7 (BSM, Vol, Execution)  Months 7–9 (Scikit, Boost)     Months 9–11 (Transformers, LSTMs)

                                                                                                       │
┌──────────────────────────────────────────────────────────────────────────────────────────────────────┘
│
└──► [ Phase 5: MLOps & scaling ] ──► [ Phase 6: Generative AI ] ──► [ Phase 7: Agents & RL ] ──► [ Phase 8: safety & Portfolio ]
       Months 11–13 (K8s, SQL, Kafka)     Months 13–15 (RAG, LoRA, Fine-tune) Months 15–17 (n8n, Bellman)    Months 17–18 (vLLM, Capstones)
```

---

## 🏛️ Phase-by-Phase Curriculum & Free Resources

### Phase 1 — The Bedrock | Months 1–4
*Core focus: Programming languages, core mathematics, and Data Structures & Algorithms (DSA).*

#### 1.1 Programming Fundamentals
*   **Python:**
    *   *Harvard CS50P:* [Intro to Programming with Python](https://cs50.harvard.edu/python/) (Free Course)
    *   *Automate the Boring Stuff with Python:* [Free Online Book](https://automatetheboringstuff.com/) (Free eBook)
    *   *Corey Schafer:* [Python YouTube Playlist](https://www.youtube.com/@coreyms/playlists) (OOP, decorators, generators)
*   **C++ (Mandatory for Quant & HFT):**
    *   *LearnCpp.com:* [Comprehensive C++ Tutorial](https://www.learncpp.com/) (The gold standard free C++ site)
    *   *freeCodeCamp:* [C++ Full Course](https://www.youtube.com/watch?v=vLnPwxZdW4Y) (4-hour video covering memory, pointers, STL)

#### 1.2 Data Structures & Algorithms (DSA)
*   *MIT 6.006:* [Introduction to Algorithms](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/) (Full course, sorting, hashing, trees, DP)
*   *NeetCode DSA:* [DSA for Beginners Playlist](https://www.youtube.com/playlist?list=PLot-Xpze53ldVwtstag2TL4HQhAnC8ATf) and the [NeetCode 150 Problem Set](https://neetcode.io/practice)

#### 1.3 Linear Algebra & Calculus
*   *3Blue1Brown:* [Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) and [Essence of Calculus](https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr) (Intuition building)
*   *MIT 18.06 (Gilbert Strang):* [Linear Algebra Video Lectures](https://www.youtube.com/playlist?list=PL49CF3715CB9EF31D) (The definitive course)
*   *MIT 18.02:* [Multivariable Calculus](https://ocw.mit.edu/courses/18-02sc-multivariable-calculus-fall-2010/) (Gradients, Jacobians, Hessians, Lagrange multipliers)

#### 1.4 Probability, Statistics & Stochastic Processes
*   *MIT 6.041:* [Probabilistic Systems Analysis](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/) (Bayes, normal/poisson distributions, Central Limit Theorem)
*   *MIT 18.642 (Fall 2024):* [Topics in Mathematics with Applications in Finance](https://www.youtube.com/playlist?list=PLUl4u3cNGP601Q2jo-J_3raNCMMs6Jves) (Latest probability and time series math in finance)
*   *Shreve Notes:* [Stochastic Calculus for Finance](https://math.uchicago.edu/~lawler/finbook.pdf) (Brownian motion, Itô's Lemma, SDEs, Girsanov)

---

### Phase 2 — Quantitative Finance & Markets | Months 4–7
*Core focus: Market microstructure, derivatives pricing, portfolio theory, and risk.*

#### 2.1 Market Architecture & Microstructure (Quant Only)
*   *Tucker Balch:* [Algorithmic Trading & Microstructure](https://www.youtube.com/playlist?list=PLAwxTw4SYaPnIRwl6rad_mYwEk4Gmj7Mx) (Order books, LOB dynamics)
*   *SSRN Research:* [Market Microstructure for Practitioners](https://ssrn.com/abstract=2024360) (SSRN Paper)
*   *QuantLib:* [C++ Quantitative Finance Library Docs](https://www.quantlib.org/docs.shtml)

#### 2.2 Derivatives Pricing & Volatility (Quant Only)
*   *Columbia University:* [Financial Engineering & Risk Management Part I](https://www.coursera.org/learn/financial-engineering-1) (Binomial models, Black-Scholes-Merton)
*   *Paul Wilmott:* [Quantitative Finance Video Lectures](https://www.youtube.com/user/pwilmott) (Volatility modeling)

#### 2.3 Portfolio Theory & Factor Models (Quant Only)
*   *Tidy Finance:* [Empirical Finance in Python/R](https://www.tidy-finance.org/) (Markowitz, Fama-French factor models, backtesting)
*   *Stefan Jansen:* [Machine Learning for Algorithmic Trading Code](https://github.com/stefan-jansen/machine-learning-for-trading) (Alternative data, alpha generation)

#### 2.4 Quant Interview Preparation (Quant Only)
*   *Brainstellar:* [Quant Puzzles](https://brainstellar.com/) (Probability brainteasers, Jane Street style)
*   *Jane Street Puzzles:* [Official Monthly Archive](https://www.janestreet.com/puzzles/)

---

### Phase 3 — Core Machine Learning | Months 7–9
*Core focus: Classical ML algorithms, validation, and feature engineering.*

*   *Stanford CS229 (Andrew Ng):* [Machine Learning Video Lectures](https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU) (The gold standard ML course)
*   *StatQuest:* [Machine Learning Video Playlist](https://www.youtube.com/playlist?list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF) (Visual guides for XGBoost, Random Forests)
*   *DataTalks.Club:* [Machine Learning Zoomcamp](https://github.com/DataTalksClub/machine-learning-zoomcamp) (Cohort-based, deployment focus)
*   *Marcos Lopez de Prado (AFML GitHub):* [Financial Machine Learning Code Answers](https://github.com/hudson-and-thames/mlfinlab) (Purged/embargoed cross-validation, return stationarity)

---

### Phase 4 — Deep Learning & NLP | Months 9–11
*Core focus: Neural networks, Transformers, sequence modeling, and financial NLP.*

*   *Andrej Karpathy:* [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) (Build GPT, backpropagation, and tokenizers from scratch)
*   *MIT 6.S191:* [Introduction to Deep Learning](http://introtodeeplearning.com/) (CNNs, RNNs, Transformers, diffusion models)
*   *Stanford CS224N:* [NLP with Deep Learning Video Lectures](https://www.youtube.com/playlist?list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVx6) (Word2vec, attention, BERT, GPT)
*   *Hugging Face:* [Hugging Face NLP Course](https://huggingface.co/learn/nlp-course/chapter1/1) (Transformers, datasets, tokenizers)
*   *ProsusAI:* [FinBERT GitHub Repository](https://github.com/ProsusAI/finBERT) (Pretrained BERT for financial sentiment analysis)

---

### Phase 5 — The Builder's Toolkit & Infrastructure | Months 11–13
*Core focus: Relational/NoSQL databases, distributed streaming, containerization, and MLOps.*

*   *Mode & SQLZoo:* [Interactive SQL Tutorial](https://mode.com/sql-tutorial/) and [SQLZoo Practice](https://sqlzoo.net/) (SQL joins, window functions, CTEs)
*   *CMU 15-445:* [Database Systems Video Lectures](https://www.youtube.com/playlist?list=PLSE8ODhjZXjbj8BMuIrRcacnQh20hmY9g) (PostgreSQL, indexing, storage, query execution)
*   *donnemartin:* [System Design Primer](https://github.com/donnemartin/system-design-primer) (CAP theorem, load balancers, caching, microservices)
*   *DataTalks.Club:* [Data Engineering Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp) (Terraform, Docker, Spark, Kafka, BigQuery)
*   *DataTalks.Club:* [MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) (Prefect, MLflow, Evidently, K8s)

---

### Phase 6 — The Era of Generative AI | Months 13–15
*Core focus: LLM architectures, fine-tuning (LoRA), RAG pipelines, and prompt compilation.*

*   *Stanford CS336:* [Language Modeling from Scratch Video Lectures](https://www.youtube.com/playlist?list=PLi-z6o4RB2k8VUpNLPNMGSSRHTJ4fWHuZ) (Pretraining, training dynamics, serving)
*   *Jay Alammar:* [Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/) (Visual guide to attention mechanism)
*   *Nir Diamant:* [Advanced RAG Techniques Repository](https://github.com/NirDiamant/RAG_Techniques) (Hybrid search, query routing, re-ranking)
*   *DAIR.AI:* [Prompt Engineering Guide](https://www.promptingguide.ai/) (CoT, ReAct, Tree of Thoughts)
*   *DSPy:* [Declarative LLM Programming Docs](https://dspy.ai/) (Prompt compilation)

---

### Phase 7 — Autonomous Agents & Reinforcement Learning | Months 15–17
*Core focus: Reinforcement learning, multi-agent frameworks, and workflow scheduling.*

*   *David Silver (DeepMind/UCL):* [Introduction to Reinforcement Learning Lectures](https://www.youtube.com/playlist?list=PLqYmG7hTraZDM-OYHWgPebj2MfCFzFObQ) (MDPs, Bellman, Q-learning)
*   *Stanford CS234:* [Reinforcement Learning Video Lectures](https://www.youtube.com/playlist?list=PLoROMvodv4rOSOPzutgyCTapiGlY2Nd8u) (DQN, PPO, Actor-Critic, policy gradients)
*   *Hugging Face:* [Deep RL Course](https://huggingface.co/learn/deep-rl-course/unit0/introduction) (Hands-on RL, stable baselines)
*   *CrewAI & Microsoft AutoGen:* [CrewAI Docs](https://docs.crewai.com/) and [AutoGen Docs](https://microsoft.github.io/autogen/) (Multi-agent orchestration)
*   *n8n & Apache Airflow:* [n8n Docs](https://docs.n8n.io/) and [Airflow Docs](https://airflow.apache.org/) (Agentic pipelines and DAGs)

---

### Phase 8 — Production Safety, Evaluation & Portfolios | Months 17–18
*Core focus: Inference engine deployment, LLM safety guardrails, evaluations, and capstone portfolios.*

*   *vLLM & llama.cpp:* [vLLM Docs](https://docs.vllm.ai/) and [llama.cpp GitHub](https://github.com/ggerganov/llama.cpp) (PagedAttention serving, local GGUF running)
*   *NVIDIA NeMo:* [NeMo Guardrails Docs](https://docs.nvidia.com/nemo/guardrails/index.html) (PII masking, jailbreak defense)
*   *RAGAS:* [RAG Evaluation Framework](https://docs.ragas.io/) (Answer faithfulness, context precision)
*   *LangSmith:* [LLM Trace & Debugging Docs](https://docs.smith.langchain.com/) (Observability)
*   *React Three Fiber & Spline:* [R3F Docs](https://docs.pmnd.rs/react-three-fiber/) and [Spline 3D Design Tool](https://spline.design/) (WebGL 3D portfolio design)
*   *vectorbt:* [Vectorized Strategy Backtesting GitHub](https://github.com/polakowo/vectorbt) (Quant portfolio simulation)

---

## 🛠️ Track-Specific Topic Matrix
*Detail Reference:* [roadmap_differentiated_tracks.md](roadmap_differentiated_tracks.md#topic-count-summary)

This table allocates priority topics across the three career paths (⚡ Critical Weight | ✅ Required | ◐ Secondary | — Not Required):

| Phase | Topic | AI & DS | Quant | AI + Quant | Notes |
| :---: | :--- | :---: | :---: | :---: | :--- |
| **Phase 1** | **DSA (Trees/Graphs)** | ⚡ | ✅ | ⚡ | LeetCode focus for tech interviews |
| | **C++ Smart Pointers / RAII** | — | ⚡ | ⚡ | Quant system engineering |
| | **Itô's Lemma & SDEs** | — | ⚡ | ⚡ | Options pricing mathematics |
| **Phase 2** | **Limit Order Book Dynamics** | — | ⚡ | ⚡ | High-frequency trading models |
| | **Black-Scholes Greeks** | — | ⚡ | ⚡ | Hedging and options trading |
| | **Fama-French Factor Models** | — | ⚡ | ⚡ | Equity alpha research |
| **Phase 3** | **Ensemble Methods (XGBoost)** | ⚡ | ⚡ | ⚡ | Relied on across both tracks |
| | **Purged & Embargoed CV** | — | ⚡ | ⚡ | Prevent time-series data leakage |
| **Phase 4** | **Attention & Transformers** | ⚡ | ✅ | ⚡ | LLM foundational architecture |
| | **FinBERT Sentiment Scoring** | ◐ | ⚡ | ⚡ | Extracting market signals from text |
| **Phase 5** | **Vector Databases (Pinecone)** | ⚡ | — | ✅ | Search and retrieval pipelines |
| | **Kernel Bypass (DPDK/Solarflare)**| — | ⚡ | ✅ | Low-latency HFT connectivity |
| **Phase 6** | **LoRA PEFT Fine-Tuning** | ⚡ | — | ◐ | Parameter-efficient customization |
| **Phase 7** | **LangGraph / CrewAI Agentic Loops**| ⚡ | — | ✅ | Multi-agent autonomous pipelines |
| **Phase 8** | **vLLM / Quantization (AWQ/GGUF)** | ⚡ | — | ◐ | Scaling inference performance |

---

## 📅 Monthly Milestone Checklist

Track your progress across the study cycle using this milestone guide:

*   [ ] **Month 3 (Bedrock Complete):** Harvard CS50 completed. Fluency in Python and C++ basics. Solved 50 LeetCode array/string problems.
*   [ ] **Month 6 (Quant/Math Complete):** Derivation of Black-Scholes-Merton. Finished MIT 18.06 Linear Algebra. Structured 3 mock quantitative or data portfolio pieces on GitHub.
*   [ ] **Month 9 (Classical ML Complete):** Andrew Ng's Stanford CS229 completed. Mastered feature engineering pipelines using scikit-learn.
*   [ ] **Month 12 (Deep Learning & NLP Complete):** Andrej Karpathy's Zero-to-Hero series finished. Trained and fine-tuned a custom transformer model.
*   [ ] **Month 14 (MLOps & Scale Complete):** Built and deployed an end-to-end data pipeline using Docker, PostgreSQL, Apache Airflow, and FastAPI.
*   [ ] **Month 16 (Generative AI Complete):** Constructed a production-grade multi-source RAG assistant evaluated using RAGAS.
*   [ ] **Month 18 (Portfolio Launch):** Deployed a custom 3D WebGL developer portfolio featuring capstone project notebooks (Streamlit apps, backtesting logs).

---

*Last Updated: June 2026. Verify external course URLs and library versions regularly as open-source libraries update.*
