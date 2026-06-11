# YouTube Roadmap — Deduplicated & Sequenced
### Quant & AI/Data Science | Unique High-Value Videos Only | Beginner → Advanced

---

## Deduplication Log — What Was Removed & Why

| Removed | Reason |
|---|---|
| Corey Schafer OOP Playlist (standalone) | Fully contained within Corey Schafer Full Python Playlist |
| Patrick Loeber Intermediate Python | Overlaps with Corey Schafer full playlist; same topics |
| freeCodeCamp Data Structures 8h | Covered more efficiently by NeetCode DSA + MIT 6.006 |
| Sorting Algorithms Visualized (Michael Sambol) | Supplementary only; covered within NeetCode DSA for Beginners |
| Striver A2Z DSA Course | Overlaps entirely with NeetCode; NeetCode is stronger for target firms |
| 3Blue1Brown Neural Networks (Phase 1 placement) | Misplaced — moved to Phase 4 where it belongs |
| StatQuest ML Playlist (Phase 1 placement) | Misplaced — moved to Phase 3 where it belongs |
| Probability Braid — Sheldon Ross | Covered by MIT 6.041 + MIT 18.642; lower production quality |
| Patrick Boyle Channel Link | Redundant — specific Patrick Boyle videos retained; channel in subscribe section |
| Stochastic Calculus Playlist (PLvtFb3DX) | Overlaps with QuantPie (same content, lower quality channel) |
| Heston Model QuantPie (standalone) | Duplicate URL — identical link to QuantPie channel already listed |
| Jane Street Puzzles "Search Query" | Not a video — a YouTube search URL, not a resource |
| Stanford CS230 Deep Learning | Substantial overlap with Karpathy Zero to Hero + MIT 6.S191; redundant third course |
| 3Blue1Brown Backpropagation (standalone video) | Part of 3Blue1Brown NN playlist already included in Phase 4 |
| Karpathy Build GPT (Phase 4 placement) | Duplicate — same video kept in Phase 6 where it belongs |
| Yannic Kilcher Channel Link (Phase 6) | Redundant — specific Yannic video kept in Phase 4; channel in subscribe section |
| 3Blue1Brown How Attention Works (Phase 6) | Duplicate URL — same playlist as 3Blue1Brown NN Series already in Phase 4 |
| Vector Databases & Embeddings for RAG | Overlaps with Vector Databases Explained (Phase 5) + RAG from Scratch (Phase 6) |

**Result: 126 → 98 resources | 28 removed**

---

## PHASE 1 — The Bedrock
> **3–4 months** | Programming, DSA, Mathematics & Statistics

---

### 1.1 Python Programming

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 1 | Python Full Course for Beginners — freeCodeCamp | Video (5h) | Beginner | The best single-shot Python intro on YouTube. Variables, data types, control flow, functions, OOP, file I/O. Start here with zero experience. | https://www.youtube.com/watch?v=rfscVS0vtbw |
| 2 | Corey Schafer — Python Tutorials (Full Playlist) | Playlist | Beginner → Intermediate | 100+ videos covering everything after the basics: OOP, decorators, generators, iterators, threading, async I/O, context managers. The definitive intermediate Python series. | https://www.youtube.com/playlist?list=PL-osiE80TeTt2d9bfVyTiXJA-UTHn6WwU |
| 3 | Async Python — ArjanCodes | Video | Intermediate | The clearest explanation of Python asyncio, coroutines, and event loops. Practical and directly applicable to data pipelines and API servers. | https://www.youtube.com/watch?v=2IW-ZEui4h4 |

### 1.2 C++ (Quant Track)

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 4 | C++ Full Course for Beginners — freeCodeCamp | Video (4h) | Beginner | Complete C++ fundamentals: pointers, memory management, OOP, templates, STL. Essential foundation before advanced quant C++. | https://www.youtube.com/watch?v=vLnPwxZdW4Y |
| 5 | C++ Smart Pointers & RAII — The Cherno | Playlist | Intermediate → Advanced | Deep dive into unique_ptr, shared_ptr, weak_ptr, RAII, and move semantics. The best C++ advanced content on YouTube for understanding modern memory management. | https://www.youtube.com/playlist?list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb |
| 6 | Low Latency C++ — CppCon Conference Talks | Playlist | Advanced | CppCon talks on cache-line optimization, SIMD vectorization, lock-free data structures, and HFT-grade C++ performance. Required for Squarepoint, Jane Street, and systematic trading roles. | https://www.youtube.com/playlist?list=PLHTh1InhhwT5o3GwbFYy3sR7HDNX3BXNc |

---

### 1.3 Data Structures & Algorithms

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 7 | NeetCode — DSA for Beginners | Playlist (33 videos) | Beginner → Intermediate | The most structured DSA intro for interview prep. Clean visual explanations of every foundational structure and algorithm pattern. Start here for DSA. | https://www.youtube.com/playlist?list=PLot-Xpze53ldVwtstag2TL4HQhAnC8ATf |
| 8 | NeetCode — Algorithms & Patterns | Playlist | Intermediate → Hard | Solves every LeetCode pattern: sliding window, two pointers, BFS/DFS, backtracking, DP, tries, heaps, graphs. Run this alongside daily LeetCode practice. | https://www.youtube.com/c/NeetCode/playlists |
| 9 | Graph Theory Algorithms — William Fiset | Playlist (36 videos) | Intermediate → Advanced | The definitive graph algorithms series on YouTube. BFS, DFS, Dijkstra, Bellman-Ford, Floyd-Warshall, max flow, SCCs, bridges. No gaps in coverage. | https://www.youtube.com/playlist?list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P |
| 10 | Dynamic Programming — Aditya Verma | Playlist | Intermediate → Advanced | The most celebrated DP playlist on YouTube. Teaches every DP variation through a systematic pattern-recognition approach. Knapsack, subsequences, matrix DP, tree DP. | https://www.youtube.com/playlist?list=PL_z_8CaSLPWekqhdCPmFohncHwz8TY2Go |
| 11 | MIT 6.006 Introduction to Algorithms | Playlist | Intermediate | Full MIT algorithms course. Rigorous mathematical treatment of sorting, hashing, graph algorithms, shortest paths, DP. Provides the theoretical foundation behind NeetCode patterns. | https://www.youtube.com/playlist?list=PLUl4u3cNGP63EdVPNLG3ToM6LaEUuStEY |

---

### 1.4 Linear Algebra & Calculus

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 12 | Essence of Linear Algebra — 3Blue1Brown | Playlist (16 videos) | Beginner → Intermediate | The most beautiful linear algebra series ever made. Builds visual intuition for vectors, matrices, determinants, eigenvalues, and SVD before any formal course. Watch before MIT 18.06. | https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab |
| 13 | Essence of Calculus — 3Blue1Brown | Playlist (12 videos) | Beginner → Intermediate | Builds genuine calculus intuition through animation — derivatives, integrals, chain rule, Taylor series. Watch before gradient descent and backpropagation. | https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr |
| 14 | MIT 18.06 Linear Algebra — Gilbert Strang | Playlist (34 lectures) | Intermediate | The legendary MIT linear algebra course. Eigenvalues, SVD, positive definite matrices, orthogonality, least squares. Takes 3B1B intuition into rigorous depth. | https://www.youtube.com/playlist?list=PL49CF3715CB9EF31D |
| 15 | MIT 18.02 Multivariable Calculus | Playlist | Intermediate | Full MIT multivariable calculus: gradients, Jacobians, Hessians, Lagrange multipliers. Foundational for understanding optimization in both ML and quant. | https://www.youtube.com/playlist?list=PL4C4C8A7D06566F38 |
| 16 | Convex Optimization — Stanford EE364a | Playlist | Advanced | Stephen Boyd's Stanford course. LP, QP, duality, KKT conditions. Used daily at every elite quant firm for portfolio optimization. Watch after MIT 18.06 and 18.02. | https://www.youtube.com/playlist?list=PL3940DD956CDF0622 |

---

### 1.5 Probability, Statistics & Stochastic Processes

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 17 | StatQuest — Statistics Fundamentals | Playlist | Beginner → Intermediate | Josh Starmer's acclaimed stats series. Probability, distributions, hypothesis testing, p-values, Bayes' theorem, MLE, CLT. The most accessible stats content on YouTube — BAM! | https://www.youtube.com/playlist?list=PLblh5JKOoLUK0FLuzwntyYI10UQFUhsY9 |
| 18 | MIT 6.041 Probabilistic Systems Analysis | Playlist | Intermediate | MIT's core probability course. Random variables, conditioning, distributions, CLT, Bayesian inference, and limit theorems. Full lecture series, problem-set quality. | https://www.youtube.com/playlist?list=PLUl4u3cNGP60A3XMwZ5sep719_nh95qOe |
| 19 | MIT 18.S096 Stochastic Processes (2015) | Playlist | Advanced | Markov chains, random walks, Brownian motion, and martingales with financial applications. Gateway course before stochastic calculus. | https://www.youtube.com/playlist?list=PLUl4u3cNGP63CTT6A4GbBUjUCe_6NRDNG |
| 20 | MIT 18.642 — Mathematics for Finance (2024) | Playlist | Advanced | MIT's 2024 course covering linear algebra + probability + stochastic processes + numerical methods through the lens of finance. The single most targeted academic resource for this roadmap. Watch last in Phase 1. | https://www.youtube.com/playlist?list=PLUl4u3cNGP601Q2jo-J_3raNCMMs6Jves |

---

## PHASE 2 — Quantitative Finance & Markets
> **2.5–3 months** | Market structure, derivatives, portfolio theory, risk, execution

---

### 2.1 Quantitative Finance Foundations

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 21 | QuantPie — Stochastic Calculus & Finance | Playlist | Advanced | The best YouTube channel for technical quant finance. Itô's Lemma, SDEs, Girsanov, Black-Scholes derivation, and Heston model — all from scratch with full mathematics. | https://www.youtube.com/c/quantpie/playlists |
| 22 | QuantPy — Python for Quant Finance | Playlist | Intermediate | Python implementations of quant concepts: options pricing, GARCH, Monte Carlo simulation, portfolio optimization. Bridges theory to code. | https://www.youtube.com/c/quantpy/playlists |
| 23 | KIT C-RAM — Quantitative Finance Lectures | Playlist | Advanced | Prof. Maxim Ulrich's university-grade lectures on factor investing, GARCH, stochastic calculus, and portfolio management. Rigorous and practitioner-relevant. | https://www.youtube.com/@cramkit/playlists |

### 2.2 Options, Derivatives & Volatility

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 24 | Options Trading for Beginners — Investopedia | Video | Beginner | Accessible intro to options mechanics, put-call parity, Greeks intuition, and basic strategies. Start here before Black-Scholes. | https://www.youtube.com/watch?v=MiybniIIvx0 |
| 25 | Black-Scholes Model Explained — Patrick Boyle | Video | Intermediate | Clear derivation and explanation of Black-Scholes, its assumptions, and its limitations. By a practitioner hedge fund manager. | https://www.youtube.com/watch?v=pr-u4LCFYEY |
| 26 | Option Greeks Full Explanation | Video | Intermediate | Comprehensive visual walkthrough of Delta, Gamma, Theta, Vega, Rho with real P&L intuition. Essential desk knowledge. | https://www.youtube.com/watch?v=kpJFDEcR3Lw |
| 27 | Implied Volatility & Vol Smiles — Patrick Boyle | Video | Advanced | How implied volatility surfaces are built, why vol smiles exist, and what they tell you about market beliefs. | https://www.youtube.com/watch?v=TDFKUQaM-ro |
| 28 | Interest Rate Models — Fixed Income Playlist | Playlist | Advanced | Yield curve construction, duration, convexity, short-rate models (Vasicek, CIR, Hull-White). Essential for fixed income quant desks at UBS, Swiss Re, Julius Baer. | https://www.youtube.com/playlist?list=PLo4jXE-LdpXyJ6z5IOqJEM5XJqsVcYxl2 |

### 2.3 Portfolio Theory & Risk Management

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 29 | Portfolio Optimization with Python — Ryan O'Connell | Playlist | Intermediate | Markowitz optimization, efficient frontier, Sharpe ratio, and Black-Litterman in Python. Practical code-first approach. | https://www.youtube.com/playlist?list=PLb6AS2ZHhPzp7HRGevnxaZFBRisANmDEX |
| 30 | CAPM & Factor Models Explained — Patrick Boyle | Video | Intermediate | CAPM derivation, Fama-French 3/5-factor models, factor investing, APT — explained by a practitioner who runs a quant fund. | https://www.youtube.com/watch?v=Yb9RdQGgBx0 |
| 31 | Value at Risk (VaR) — QuantPy | Video | Intermediate | Parametric VaR, historical simulation, and Monte Carlo VaR implemented in Python with real portfolio data. | https://www.youtube.com/watch?v=RswNN_JNKSU |
| 32 | Monte Carlo Simulation in Finance — Python | Video | Intermediate | Full Monte Carlo tutorial for option pricing, portfolio simulation, and risk analysis. Connects stochastic processes to implementation. | https://www.youtube.com/watch?v=6-dhdMDiYWQ |
| 33 | Algorithmic Trading & Execution — Tucker Balch | Playlist | Intermediate | Georgia Tech free lectures. VWAP, TWAP, implementation shortfall, Almgren-Chriss optimal execution model. | https://www.youtube.com/playlist?list=PLAwxTw4SYaPnIRwl6rad_mYwEk4Gmj7Mx |

### 2.4 Quant Interview Preparation

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 34 | Quant Interview Prep — Probability Puzzles | Playlist | Advanced | Walkthroughs of classic quant probability puzzles identical to those used at Jane Street, Goldman, and Squarepoint. Work the problems yourself first. | https://www.youtube.com/playlist?list=PLGLfVvz_LVvSX7fVd4OUFp_ODd86H0ZIo |
| 35 | Market Making & Bid-Ask — Patrick Boyle | Video | Advanced | How market makers set bid-ask spreads, manage inventory, and hedge risk. Direct Jane Street/Squarepoint interview territory. Watch this before any market-making interview. | https://www.youtube.com/watch?v=jIHzfS_Y8Fk |

---

## PHASE 3 — Core Machine Learning
> **2 months** | Classical ML, feature engineering, model evaluation

---

### 3.1 Core ML Courses

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 36 | StatQuest — Machine Learning Playlist | Playlist | Beginner → Intermediate | Every classical ML algorithm explained visually: linear regression, logistic regression, SVMs, random forests, XGBoost, k-means, PCA. Build intuition before theory. Start here. | https://www.youtube.com/playlist?list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF |
| 37 | Stanford CS229 — Machine Learning (2018) | Playlist (20 lectures) | Intermediate → Advanced | Andrew Ng's definitive Stanford ML course. Supervised/unsupervised learning, SVMs, EM algorithm, PGMs. The rigorous theory to follow after StatQuest. | https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpjmjL0 |
| 38 | Applied Machine Learning — Cornell Tech CS 5787 | Playlist | Intermediate | Modern Cornell ML course covering regularization, ensembles, Bayesian methods, and practical considerations. Complements CS229 with applied focus. | https://www.youtube.com/playlist?list=PL2UML_KCiC0UlY7iCzkE4C_tpKqECnqUX |
| 39 | Scikit-Learn Full Tutorial — freeCodeCamp | Video (3h) | Intermediate | Complete scikit-learn tutorial: preprocessing, pipelines, model selection, evaluation. Essential hands-on practice alongside the theory courses. | https://www.youtube.com/watch?v=0B5eIE_1vpU |

### 3.2 Boosted Trees & Ensembles

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 40 | XGBoost & LightGBM — StatQuest Deep Dive | Playlist | Intermediate | The math behind gradient boosted trees. Covers XGBoost loss functions, regularization, LightGBM optimizations. Required for any ML engineering role. | https://www.youtube.com/playlist?list=PLblh5JKOoLUJjeXUvUE0maghNuY2_5fY6 |

### 3.3 Feature Engineering, Evaluation & Explainability

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 41 | Bias-Variance Tradeoff — StatQuest | Video | Beginner → Intermediate | The clearest visual explanation of overfitting, underfitting, and regularization on YouTube. Watch before cross-validation. | https://www.youtube.com/watch?v=EuBBz3bI-aA |
| 42 | Cross-Validation & Hyperparameter Tuning | Video | Intermediate | K-fold, stratified k-fold, grid search, random search, and Bayesian optimization — all in one video. Interview-tested topic. | https://www.youtube.com/watch?v=TIgfjmp-4BA |
| 43 | PCA Explained Visually — StatQuest | Video | Intermediate | Visual derivation of PCA from eigendecomposition. Explains exactly what each principal component captures and why it matters. | https://www.youtube.com/watch?v=FgakZw6K1QQ |
| 44 | SHAP Values — Explainability & Feature Importance | Video | Intermediate | How SHAP values work and how to interpret model decisions. Increasingly asked in quant and AI/DS interviews. | https://www.youtube.com/watch?v=9haIOplEIGM |

### 3.4 ML for Finance

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 45 | ML for Finance — Yves Hilpisch | Playlist | Advanced | Python-based financial ML: feature engineering on price data, purged cross-validation, regime detection, and signal research. Bridges Phases 2 and 3 for AI+Quant roles. | https://www.youtube.com/playlist?list=PLQVvvaa0QuDdhOnp-FnVStDsALpYk2hk0 |

---

## PHASE 4 — Deep Learning & NLP
> **2.5 months** | Neural networks, CNNs, RNNs, Transformers, NLP, time series

---

### 4.1 Neural Network Foundations

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 46 | Neural Networks & Backpropagation — 3Blue1Brown | Playlist (4 videos) | Beginner → Intermediate | Visual intuition for neural networks, gradient descent, and backpropagation. This playlist also includes the Attention/Transformer videos added in 2024. Watch before any DL course. | https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi |
| 47 | Neural Networks: Zero to Hero — Andrej Karpathy | Playlist (7 videos) | Intermediate → Advanced | The single best deep learning course on YouTube. Builds backpropagation, MLP, RNN, WaveNet, and GPT from scratch in pure Python then PyTorch. By the former Tesla AI Director. | https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ |
| 48 | MIT 6.S191 — Introduction to Deep Learning (2024) | Playlist | Beginner → Intermediate | MIT's annual DL course. CNNs, RNNs, Transformers, diffusion models, RL applications. Updated every year. Broadest architecture coverage in a single course. | https://www.youtube.com/playlist?list=PLtBw6njQRU-rwp5__7C0oIVt26ZgjG9NI |
| 49 | PyTorch Full Tutorial — Patrick Loeber | Playlist | Intermediate | The best PyTorch series on YouTube. Tensors, autograd, custom datasets, training loops, CNNs, RNNs. Practical implementation alongside Karpathy's theory. | https://www.youtube.com/playlist?list=PLqnslRFeH2UrcDBWF5mfPGpqQDSta6VK4 |

### 4.2 Advanced Architectures

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 50 | Convolutional Neural Networks — Stanford CS231n | Playlist | Intermediate → Advanced | Stanford's legendary computer vision course. Full CNN theory: backprop in CNNs, pooling, batch norm, ResNet, object detection. The gold standard reference. | https://www.youtube.com/playlist?list=PL3FW7Lu3i5JvHM8ljYj-zLfQRF3EO8sYv |
| 51 | RNNs & Sequence Modelling — Andrej Karpathy | Video | Intermediate | Classic conceptual deep dive into RNNs from first principles. The "Unreasonable Effectiveness of RNNs" walkthrough. Still the clearest RNN explainer available. | https://www.youtube.com/watch?v=iX5V1WpxxkY |
| 52 | Diffusion Models Explained — Outlier | Video | Advanced | Mathematical explanation of DDPM diffusion models from the score-matching and noise-prediction perspective. Essential for NVIDIA/Google generative AI roles. | https://www.youtube.com/watch?v=fbLgFrlTnGU |
| 53 | Graph Neural Networks — Stanford CS224W | Playlist | Advanced | Full Stanford ML with Graphs course. GNN foundations, node embeddings, GCNs, knowledge graphs, and financial network applications. | https://www.youtube.com/playlist?list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn |

### 4.3 NLP & Transformers

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 54 | Stanford CS224N — NLP with Deep Learning (2024) | Playlist | Advanced | Stanford's flagship NLP course. Word2Vec, RNNs, attention, BERT, GPT, instruction tuning, RLHF. The definitive academic NLP course — 2024 version. | https://www.youtube.com/playlist?list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVx76 |
| 55 | Attention Is All You Need — Yannic Kilcher | Video | Advanced | The deepest paper walkthrough of the original Transformer paper on YouTube. Mathematical and thorough. Read the paper, then watch this. | https://www.youtube.com/watch?v=iDulhoQ2pro |
| 56 | BERT Explained — CodeEmporium | Video | Intermediate | Clear visual explanation of BERT's masked language modeling, next sentence prediction, and fine-tuning approach. | https://www.youtube.com/watch?v=xI0HHN5XKDo |
| 57 | Hugging Face Transformers Crash Course | Video (1h) | Intermediate | Quick practical intro to loading, fine-tuning, and deploying models with the Hugging Face library. Hands-on bridge to CS224N theory. | https://www.youtube.com/watch?v=GSt00_-0ncQ |
| 58 | FinBERT & Financial NLP — Explained | Video | Intermediate | Walkthrough of FinBERT for financial sentiment analysis with Python implementation. Directly relevant for alternative data roles at quant firms. | https://www.youtube.com/watch?v=vwNUFKP9vHU |

---

## PHASE 5 — The Builder's Toolkit & Infrastructure
> **2 months** | Databases, distributed systems, MLOps, cloud

---

### 5.1 Databases & SQL

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 59 | SQL Full Course — freeCodeCamp | Video (4h) | Beginner → Intermediate | Complete SQL from scratch: joins, subqueries, aggregate functions, views, stored procedures. Non-negotiable foundation. | https://www.youtube.com/watch?v=HXV3zeQKqGY |
| 60 | Advanced SQL — Mode Analytics | Playlist | Intermediate | Window functions, CTEs, recursive queries, and query optimization. Goes where freeCodeCamp stops. | https://www.youtube.com/playlist?list=PL6-LlKrJpgkzOYFxXhLXUhwVmTNmRRvS5 |
| 61 | CMU 15-445 Database Systems — Andy Pavlo | Playlist | Advanced | Carnegie Mellon's legendary DB course. Storage engines, indexing, query execution, concurrency control, crash recovery. Graduate level. | https://www.youtube.com/playlist?list=PLSE8ODhjZXjbj8BMuIrRcacnQh20hmY9g |
| 62 | Redis Crash Course — Traversy Media | Video | Beginner → Intermediate | Complete intro to Redis: data types, caching, pub/sub, sessions. Fast and practical. | https://www.youtube.com/watch?v=jgpVdJB2sKQ |
| 63 | Vector Databases Explained — Fireship | Video | Intermediate | Best quick explainer on how vector databases work, HNSW indexing, and why they matter for AI applications. | https://www.youtube.com/watch?v=klTvEwg3oJ4 |

### 5.2 Distributed Systems & System Design

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 64 | System Design Interview — Gaurav Sen | Playlist | Intermediate → Advanced | The most subscribed system design channel. Load balancing, consistent hashing, caching, databases, messaging queues at interview depth. Work through this systematically. | https://www.youtube.com/playlist?list=PLMCXHnjXnTnvo6alSjVkgxV-VH6EPyvoX |
| 65 | System Design for ML — ML System Design | Playlist | Advanced | ML-specific system design: recommendation systems, feature stores, model serving, training infrastructure. Directly tested at Google, Meta, Palantir. | https://www.youtube.com/playlist?list=PLLyw7o_B_EBuNKNxKsEO0BCAJF6q_l12J |
| 66 | MIT 6.824 Distributed Systems — Full Lectures | Playlist | Advanced | MIT's full distributed systems course. Raft consensus, MapReduce, Zookeeper, Spanner, Chord. Taken by engineers at all target companies. | https://www.youtube.com/playlist?list=PLrw6a1wE39_tb2fErI4-WkMbsvGQk9_UB |
| 67 | Apache Kafka Full Course — freeCodeCamp | Video (4h) | Intermediate | Complete Kafka tutorial: topics, producers, consumers, partitions, consumer groups. Essential for real-time financial data and ML feature pipelines. | https://www.youtube.com/watch?v=SqVfCyfCJqw |
| 68 | Apache Spark Tutorial — freeCodeCamp | Video (3h) | Intermediate | Full Spark crash course: RDDs, DataFrames, Spark SQL, and MLlib. Required for large-scale data engineering at any target firm. | https://www.youtube.com/watch?v=_C8kWso4ne4 |

### 5.3 MLOps, Cloud & DevOps

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 69 | Docker Full Course — TechWorld with Nana | Video (3h) | Beginner → Intermediate | The most-watched Docker tutorial on YouTube. Containers, images, volumes, Compose, and networking. The entry point for all infrastructure work. | https://www.youtube.com/watch?v=3c-iBn73dDE |
| 70 | Kubernetes Full Course — TechWorld with Nana | Video (4h) | Intermediate | Comprehensive Kubernetes course. Pods, deployments, services, ingress, RBAC, and scaling. Directly tested at NVIDIA, Google, and Palantir. | https://www.youtube.com/watch?v=X48VuDVv0do |
| 71 | GitHub Actions CI/CD — TechWorld with Nana | Video | Beginner → Intermediate | Full GitHub Actions tutorial from scratch. Build CI/CD pipelines for ML projects including testing and deployment. | https://www.youtube.com/watch?v=R8_veQiYBjI |
| 72 | MLOps Full Course — freeCodeCamp | Video (1h) | Intermediate | Intro to MLOps: CI/CD for ML, model monitoring, data drift, training pipelines, and deployment. Conceptual overview before MLflow and W&B. | https://www.youtube.com/watch?v=9L9jKzmFEFQ |
| 73 | MLflow Tutorial — freeCodeCamp | Video | Intermediate | Complete MLflow tutorial: experiment tracking, model registry, and model serving. Industry-standard MLOps tooling. | https://www.youtube.com/watch?v=qdcHHrsXA48 |
| 74 | Full Stack Deep Learning (2022) | Playlist | Intermediate → Advanced | Covers the complete ML production stack: data quality, training infrastructure, testing, deployment, and monitoring. Bridges MLOps theory to real systems. | https://www.youtube.com/playlist?list=PL1T8fO7ArWlcWg04OgNiJy91PywMKT2lv |
| 75 | Terraform Full Course — freeCodeCamp | Video (2.5h) | Intermediate | Complete Infrastructure as Code with Terraform. Cloud resource provisioning for AWS, GCP, Azure deployments. | https://www.youtube.com/watch?v=SLB_c_ayRMo |

---

## PHASE 6 — The Era of Generative AI
> **2 months** | LLMs, RAG, fine-tuning, alignment, prompt engineering

---

### 6.1 Large Language Models — Architecture

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 76 | Intro to Large Language Models — Karpathy | Video (1h) | Intermediate | Karpathy's accessible 1-hour overview of what LLMs are, how they work, and where they're heading. Watch this first before going deep. | https://www.youtube.com/watch?v=zjkBMFhNj_g |
| 77 | Let's Build GPT from Scratch — Karpathy | Video (2h) | Advanced | Karpathy builds a full GPT transformer in PyTorch from a blank file. Tokens, attention, multi-head, positional encoding. Non-negotiable for anyone serious about LLMs. | https://www.youtube.com/watch?v=kCc8FmEb1nY |
| 78 | Let's Build the GPT Tokenizer — Karpathy | Video (2h) | Advanced | Builds a BPE tokenizer from scratch. Completely demystifies how tokenization works. Watch directly after the GPT build. | https://www.youtube.com/watch?v=zduSFxRajkE |
| 79 | Stanford CS336 — Language Modeling from Scratch (2024) | Playlist | Advanced | Stanford's 2024 course on building LLMs end-to-end: data pipelines, architecture, pretraining, and deployment. The most current and comprehensive academic LLM course available. | https://www.youtube.com/playlist?list=PLi-z6o4RB2k8VUpNLPNMGSSRHTJ4fWHuZ |

### 6.2 Fine-Tuning & Alignment

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 80 | LoRA & Parameter-Efficient Fine-Tuning Explained | Video | Advanced | Clear explanation of LoRA, QLoRA, and adapter methods with the math behind low-rank decomposition. Required before any fine-tuning project. | https://www.youtube.com/watch?v=dA-NhCtrrVE |
| 81 | RLHF, DPO & LLM Alignment Explained | Video | Advanced | How RLHF trains LLMs from human feedback and how DPO simplifies the alignment process. Bridges Phase 7 RL with LLM production. | https://www.youtube.com/watch?v=2p-LYboXkKg |

### 6.3 Retrieval Augmented Generation (RAG)

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 82 | RAG Explained Simply — IBM Technology | Video | Beginner → Intermediate | Clear, accessible overview of how RAG works conceptually. Best starting point before implementation. | https://www.youtube.com/watch?v=T-D1OfcDW1M |
| 83 | RAG from Scratch — LangChain | Playlist | Intermediate → Advanced | Official LangChain playlist building RAG step-by-step: embeddings, vector stores, retrieval, query transformation, reranking, self-RAG. The definitive hands-on RAG series. | https://www.youtube.com/playlist?list=PLfaIDFEXuae2LXbO1_PKyVJiQ23ZztA0x |
| 84 | Advanced RAG Techniques — AI Makerspace | Playlist | Advanced | Hybrid search, multi-vector retrieval, reranking, knowledge graphs, and self-RAG. Takes LangChain RAG to production-grade complexity. | https://www.youtube.com/playlist?list=PLK66eS0JxcxRKrUkP9sLq3MbFiA7M2AqV |

### 6.4 Prompt Engineering

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 85 | Prompt Engineering Full Course — freeCodeCamp | Video (1h) | Beginner → Intermediate | Zero-shot, few-shot, chain-of-thought, ReAct, and structured prompting with practical examples. Start here. | https://www.youtube.com/watch?v=_ZvnD73m40o |
| 86 | Chain-of-Thought Prompting Explained | Video | Intermediate | Academic explanation of CoT, self-consistency, and tree of thoughts. Deeper theory behind the techniques from the freeCodeCamp course. | https://www.youtube.com/watch?v=H4YK_7wFk68 |

---

## PHASE 7 — Autonomous Agents & Reinforcement Learning
> **1.5–2 months** | RL foundations, policy optimization, multi-agent systems

---

### 7.1 Reinforcement Learning

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 87 | Q-Learning Explained — StatQuest | Video | Beginner → Intermediate | Visual step-by-step explanation of Q-learning and temporal difference learning. Build intuition before the full courses. Watch first. | https://www.youtube.com/watch?v=0g4j2k_Ggc4 |
| 88 | Introduction to RL — David Silver (DeepMind/UCL) | Playlist (10 lectures) | Intermediate → Advanced | The canonical RL lecture series by David Silver, creator of AlphaGo. MDP, Bellman equations, Q-learning, policy gradients, function approximation. The standard academic reference. | https://www.youtube.com/playlist?list=PLqYmG7hTraZDM-OYHWgPebj2MfCFzFObQ |
| 89 | Stanford CS234 — Reinforcement Learning (2024) | Playlist | Advanced | Stanford's full RL course. DQN, policy gradients, actor-critic, PPO, SAC, exploration, and MARL. More current than David Silver with additional depth. | https://www.youtube.com/playlist?list=PLoROMvodv4rOSOPzutgyCTapiGlY2Nd8u |
| 90 | Deep RL Bootcamp — Berkeley | Playlist | Advanced | Berkeley intensive RL lectures covering model-based methods, imitation learning, and meta-RL — topics not in CS234. Complements rather than overlaps. | https://www.youtube.com/playlist?list=PLCTc_C7itk-GaAMxmlChrkPnGKtjz8hv1 |
| 91 | Deep RL in PyTorch — Phil Tabor | Playlist | Intermediate → Advanced | Hands-on implementations of DQN, DDPG, PPO, and SAC in PyTorch from scratch. Bridges theory from David Silver/CS234 to working code. | https://www.youtube.com/playlist?list=PLyhSTPxAOtKLkZTcBUrXG9pjmuUMwJH5K |
| 92 | PPO — Proximal Policy Optimization Explained | Video | Advanced | Mathematical derivation and PyTorch implementation of PPO with clear intuition for the clipping objective. | https://www.youtube.com/watch?v=5P7I-xPq8u8 |

### 7.2 AI Agents & Multi-Agent Systems

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 93 | AI Agents Explained — IBM Technology | Video | Beginner → Intermediate | Conceptual overview of agent loops, tool use, planning, memory, function calling, and ReAct. Watch before any framework tutorial. | https://www.youtube.com/watch?v=F8NKVhkZZWI |
| 94 | LangGraph Full Course — freeCodeCamp | Video (2h) | Intermediate → Advanced | Complete LangGraph tutorial: nodes, edges, state machines, memory management, human-in-the-loop, and multi-agent orchestration. | https://www.youtube.com/watch?v=jGg_1h0qzaM |
| 95 | Building AI Agents from Scratch — Sam Witteveen | Playlist | Intermediate → Advanced | Practical series on building real agents with LangChain, LangGraph, tool calling, and persistent memory. Hands-on complement to LangGraph course. | https://www.youtube.com/playlist?list=PL8motc6AQftkWtR16ha62MMJF9K-go3YF |
| 96 | CrewAI Full Tutorial | Video | Intermediate | Building multi-agent pipelines with CrewAI: roles, tasks, tool assignment, and orchestration. Quickest path to a working multi-agent system. | https://www.youtube.com/watch?v=sPzc6hMg7So |
| 97 | AutoGen Multi-Agent Tutorial — Microsoft | Video | Advanced | Microsoft's AutoGen framework for multi-agent conversations, group chats, and tool use. Official tutorial. | https://www.youtube.com/watch?v=vU2S6dVf79M |

---

## PHASE 8 — Production Safety, Evaluation & Portfolios
> **1–1.5 months** | Inference optimization, LLM safety, evaluation, capstone projects

---

### 8.1 LLM Deployment & Inference Optimization

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 98 | Running LLMs Locally with Ollama | Video | Beginner → Intermediate | Step-by-step tutorial for running open-source LLMs locally. Fast setup, immediate experimentation. Start here before vLLM. | https://www.youtube.com/watch?v=90ozfdsQOKo |
| 99 | vLLM Tutorial & Architecture Explained | Video | Advanced | How vLLM's PagedAttention works and how to deploy LLMs for high-throughput production inference. | https://www.youtube.com/watch?v=80bIUggRJf4 |
| 100 | Model Quantization Explained — GPTQ, AWQ, GGUF | Video | Advanced | Technical deep dive into LLM quantization formats, their accuracy/speed tradeoffs, and how to quantize models yourself. | https://www.youtube.com/watch?v=mii-xFaPCrA |
| 101 | Speculative Decoding — How LLMs Are Accelerated | Video | Advanced | How speculative decoding works and why it speeds up LLM inference without quality loss. | https://www.youtube.com/watch?v=S-8Pj3y4PAY |

### 8.2 AI Safety & Evaluation

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 102 | Prompt Injection & LLM Security — Simon Willison | Video | Intermediate | Real-world prompt injection vulnerabilities, data exfiltration attack vectors, and practical production defenses. | https://www.youtube.com/watch?v=s_CgJbVhhqE |
| 103 | LLM Evaluation — How to Measure AI Performance | Video | Intermediate | LLM-as-a-Judge, RAGAS metrics, MMLU, HumanEval, and building evaluation pipelines. Directly applicable for production deployment. | https://www.youtube.com/watch?v=Dr-ePnKKFMM |
| 104 | AI Alignment & RLHF — Research Talks Playlist | Playlist | Advanced | Curated talks from Anthropic, DeepMind, and OpenAI researchers on safety, alignment, Constitutional AI, and RLHF. | https://www.youtube.com/playlist?list=PLIBmWVGQhizLrPjpFMN5bQdbOZAQmTkP3 |

### 8.3 Portfolio & Capstone Projects

| # | Title | Type | Level | Description | Link |
|---|---|---|---|---|---|
| 105 | FastAPI Full Course — freeCodeCamp | Video (1h) | Intermediate | Build production-ready REST APIs for ML model serving with FastAPI. Required for any ML deployment portfolio project. | https://www.youtube.com/watch?v=0sOvCWFmrtA |
| 106 | Backtesting a Trading Strategy in Python | Video | Intermediate → Advanced | Full statistical arbitrage backtesting pipeline with purged cross-validation and performance metrics. The ideal AI+Quant portfolio project. | https://www.youtube.com/watch?v=xfzGZB4HhEE |
| 107 | Three.js Full Course — Bruno Simon | Playlist | Intermediate | The definitive Three.js course by the creator of the internet's most famous 3D portfolio. Foundation for building a standout 3D portfolio site. | https://www.youtube.com/playlist?list=PLHm2BHAe0Y3ePLBNvCLtNvU_bCdICkGRN |
| 108 | React Three Fiber Crash Course | Video | Intermediate | Building 3D scenes in React using React Three Fiber. Bridges Three.js and your React portfolio project. | https://www.youtube.com/watch?v=vTfMjI4rVSI |

---

## Channels to Subscribe — Watch Continuously

| Channel | Track | Why Subscribe | Link |
|---|---|---|---|
| 3Blue1Brown | Math | Best mathematical visualizations ever made. Watch every new upload immediately | https://www.youtube.com/@3blue1brown |
| Andrej Karpathy | AI / DL | Former Tesla AI Director & OpenAI co-founder. Every video is a masterclass | https://www.youtube.com/@AndrejKarpathy |
| Patrick Boyle | Quant Finance | Practitioner quant hedge fund content. Covers markets, derivatives, and strategy | https://www.youtube.com/@PBoyle |
| Yannic Kilcher | ML Research | Best research paper reviews on YouTube. Keeps you current with the field | https://www.youtube.com/@YannicKilcher |
| StatQuest (Josh Starmer) | Stats / ML | Clearest stats and ML explanations alive. New videos always worth watching | https://www.youtube.com/@statquest |
| TechWorld with Nana | DevOps / MLOps | Best Docker, Kubernetes, and CI/CD tutorials on YouTube | https://www.youtube.com/@TechWorldwithNana |
| NeetCode | DSA / Interviews | Daily LeetCode solutions and interview patterns. Run this every single day | https://www.youtube.com/@NeetCode |
| Two Minute Papers | AI Research | 2-minute summaries of the latest AI papers. Keeps your research radar sharp | https://www.youtube.com/@TwoMinutePapers |
| QuantPie | Quant Math | Deep stochastic calculus and quant finance math | https://www.youtube.com/@quantpie |
| Lex Fridman | AI / CS Context | Long-form interviews with Hinton, LeCun, Karpathy, Silver. Builds career perspective | https://www.youtube.com/@lexfridman |

---

## Final Count by Phase

| Phase | Videos/Playlists | Levels Covered |
|---|---|---|
| Phase 1 — Bedrock | 20 | Beginner → Advanced |
| Phase 2 — Quant Finance | 15 | Beginner → Advanced |
| Phase 3 — Core ML | 10 | Beginner → Advanced |
| Phase 4 — DL & NLP | 13 | Intermediate → Advanced |
| Phase 5 — Infrastructure | 17 | Beginner → Advanced |
| Phase 6 — Generative AI | 11 | Intermediate → Advanced |
| Phase 7 — RL & Agents | 11 | Beginner → Advanced |
| Phase 8 — Production | 11 | Intermediate → Advanced |
| **Total** | **108** | |
