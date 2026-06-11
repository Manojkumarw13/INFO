# Differentiated Career Roadmap — AI & DS vs Quant vs AI+Quant
### Precise Track Allocation for Every Topic

---

## Legend

| Symbol | Meaning |
|---|---|
| ✅ | Required — core to this track |
| ⚡ | Critical — highest interview weight |
| ◐ | Useful but secondary depth needed |
| — | Not required for this track |

**Track definitions:**
- **AI & DS** → Google, Apple, Microsoft, Meta, NVIDIA, Palantir
- **Quant** → Jane Street, Goldman Sachs, JPMorgan, UBS, Swiss Re, Julius Baer, Pictet, Vontobel, Partners Group
- **AI + Quant** → Squarepoint Capital, Systematica Investments (and any firm requiring both)

---

## Phase 1 — The Bedrock | 3–4 months

### 1.1 Programming Fundamentals

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Variables, Data types, Operators | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Control flow, Functions, Recursion | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Type hinting | ✅ | ✅ | ✅ | High | Python best practice |
| Input / Output, File handling | ✅ | ✅ | ✅ | High | Universal |
| Regular expressions | ✅ | ◐ | ✅ | High | AI: NLP pipelines; Quant: log parsing |
| Memory — Stack & Heap | ✅ | ⚡ | ⚡ | Critical | Quant: deeper for C++ |
| Garbage collection | ✅ | ◐ | ✅ | High | Python internals |
| Reference counting | ◐ | ✅ | ✅ | High | C++ RAII overlap |
| Global Interpreter Lock (GIL) | ✅ | ⚡ | ⚡ | Critical | Quant: concurrency bottleneck |

### 1.2 Advanced Programming & Low-Latency Systems

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Object-Oriented Programming | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Functional Programming | ✅ | ✅ | ✅ | High | Universal |
| Iterators, Generators | ✅ | ✅ | ✅ | High | Data pipelines |
| Decorators | ✅ | ◐ | ✅ | High | AI: MLOps; Quant: less critical |
| Metaprogramming | ◐ | ◐ | ✅ | Medium | Advanced Python only |
| Concurrency & Multithreading | ✅ | ⚡ | ⚡ | Critical | Quant: real-time systems |
| Asynchronous I/O | ✅ | ✅ | ✅ | High | AI: APIs; Quant: feed handling |
| C++ Smart Pointers | — | ⚡ | ⚡ | Critical | Quant only — HFT/low-latency |
| C++ Move Semantics | — | ⚡ | ⚡ | Critical | Quant only |
| RAII (Resource Acquisition Is Initialization) | — | ⚡ | ⚡ | Critical | Quant only |
| SIMD Vectorization | — | ⚡ | ✅ | Critical | Quant: HFT performance |
| Cache-line alignment | — | ⚡ | ✅ | Critical | Quant: HFT performance |
| False sharing prevention | — | ✅ | ✅ | High | Quant: multi-core systems |
| Ring buffers | — | ⚡ | ✅ | Critical | Quant: order book queues |
| Lock-Free Architectures (LMAX Disruptor) | — | ⚡ | ✅ | Critical | Quant: ultra-low latency |
| NUMA awareness | — | ✅ | ✅ | High | Quant: server optimization |

---

### 2.1 Linear & Hash-Based Data Structures

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Arrays, Linked lists | ⚡ | ⚡ | ⚡ | Critical | Universal interview topic |
| Stacks, Queues | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Hash tables, Hash sets | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Collision resolution strategies | ✅ | ✅ | ✅ | High | Systems interviews |
| Bloom filters | ✅ | ◐ | ✅ | High | AI: streaming; Quant: dedup |
| Count-Min Sketch | ✅ | — | ◐ | Medium | AI: frequency estimation |

### 2.2 Tree & Graph Structures

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Binary Search Trees | ⚡ | ✅ | ⚡ | Critical | AI: heavier LeetCode focus |
| AVL trees | ✅ | ◐ | ✅ | High | AI: coding interviews |
| Red-Black trees | ✅ | ◐ | ✅ | High | STL internals (Quant: C++) |
| B-trees | ✅ | ◐ | ✅ | High | Database internals |
| Heaps — Binary & Priority queues | ⚡ | ⚡ | ⚡ | Critical | Universal — order books, Dijkstra |
| Tries | ⚡ | — | ◐ | Critical | AI: NLP/autocomplete interviews |
| Graphs (Directed, Undirected, Weighted) | ⚡ | ✅ | ⚡ | Critical | Universal |
| Adjacency representations | ⚡ | ✅ | ⚡ | Critical | Universal |

---

### 3.1 Core Algorithm Design

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Big-O Time & Space complexity | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Binary search | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Merge sort, Quick sort, Heap sort | ⚡ | ✅ | ⚡ | Critical | AI: more LeetCode weight |
| Divide and conquer | ⚡ | ✅ | ⚡ | Critical | AI: interviews; Quant: algorithms |
| Greedy approaches | ⚡ | ◐ | ✅ | Critical | AI: heavy; Quant: lighter |
| Backtracking | ⚡ | ◐ | ✅ | High | AI: NeetCode patterns |

### 3.2 Graph & Dynamic Algorithms

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| BFS, DFS | ⚡ | ✅ | ⚡ | Critical | Universal |
| Dijkstra's algorithm | ⚡ | ✅ | ⚡ | Critical | Universal |
| A* algorithm | ✅ | ◐ | ✅ | High | AI: search; Quant: routing |
| Topological sort | ⚡ | ◐ | ✅ | Critical | AI: DAGs, pipelines |
| Dynamic programming — Memoization | ⚡ | ✅ | ⚡ | Critical | AI: LeetCode critical |
| Dynamic programming — Tabulation | ⚡ | ✅ | ⚡ | Critical | AI: LeetCode critical |
| String matching — KMP | ⚡ | — | ◐ | High | AI: NLP/coding interviews |
| String matching — Rabin-Karp | ✅ | — | ◐ | High | AI: rolling hash pattern |

---

### 4.1 Linear Algebra & Multivariable Calculus

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Vectors, Matrices, Tensors | ⚡ | ⚡ | ⚡ | Critical | Universal math foundation |
| Determinants | ✅ | ⚡ | ⚡ | Critical | Quant: hedging, covariance |
| Eigenvalues & Eigenvectors | ⚡ | ⚡ | ⚡ | Critical | Universal — PCA, risk |
| SVD | ⚡ | ⚡ | ⚡ | Critical | AI: dimensionality; Quant: risk |
| Cholesky decomposition | ◐ | ⚡ | ⚡ | Critical | Quant: covariance matrices |
| LU decomposition | ◐ | ⚡ | ⚡ | Critical | Quant: numerical finance |
| QR decomposition | ✅ | ✅ | ✅ | High | Universal |
| Derivatives, Gradients | ⚡ | ⚡ | ⚡ | Critical | AI: backprop; Quant: Greeks |
| Jacobians, Hessians | ✅ | ⚡ | ⚡ | Critical | AI: optimization; Quant: risk |
| Convex optimization | ✅ | ⚡ | ⚡ | Critical | Quant: portfolio opt |
| Non-convex optimization | ✅ | ✅ | ✅ | High | AI: training NNs |
| Lagrange multipliers | ✅ | ⚡ | ⚡ | Critical | Quant: constrained portfolio opt |
| KKT conditions | ✅ | ⚡ | ⚡ | Critical | Quant: portfolio constraints |

### 4.2 Probability, Statistics & Risk Math

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Probability spaces, Random variables | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Bayes' theorem | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Normal distribution | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Binomial distribution | ✅ | ⚡ | ⚡ | Critical | Quant: brainteasers |
| Poisson distribution | ✅ | ⚡ | ⚡ | Critical | Quant: arrival processes |
| Lognormal distribution | ◐ | ⚡ | ⚡ | Critical | Quant: asset prices |
| Exponential distribution | ✅ | ⚡ | ⚡ | Critical | Quant: event timing |
| Gamma distribution | ✅ | ✅ | ✅ | High | Bayesian inference |
| Hypothesis testing & p-values | ⚡ | ✅ | ⚡ | Critical | AI: experimentation |
| A/B testing | ⚡ | ◐ | ✅ | Critical | AI: product; Quant: signal test |
| Maximum Likelihood Estimation (MLE) | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Central Limit Theorem (CLT) | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Extreme Value Theory (EVT) | — | ⚡ | ✅ | Critical | Quant: tail risk, VaR |
| Copula functions | — | ⚡ | ✅ | Critical | Quant: portfolio risk |

### 4.3 Stochastic Calculus & Econometrics

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Markov chains | ✅ | ⚡ | ⚡ | Critical | AI: RL; Quant: pricing |
| Random walks | ◐ | ⚡ | ⚡ | Critical | Quant: price modelling |
| Brownian motion | — | ⚡ | ⚡ | Critical | Quant: foundational |
| Itô's Lemma | — | ⚡ | ⚡ | Critical | Quant: derivation of BS |
| Stochastic Differential Equations (SDEs) | — | ⚡ | ⚡ | Critical | Quant: option pricing |
| Girsanov theorem | — | ⚡ | ✅ | Critical | Quant: change of measure |
| Time series stationarity | ✅ | ⚡ | ⚡ | Critical | Both: time series modelling |
| Cointegration | ◐ | ⚡ | ⚡ | Critical | Quant: pairs trading |
| ARIMA models | ✅ | ⚡ | ⚡ | Critical | Both: forecasting |
| GARCH models | ◐ | ⚡ | ⚡ | Critical | Quant: volatility modelling |
| Kalman filters | ◐ | ⚡ | ⚡ | Critical | Quant: signal filtering |
| Particle filters | — | ✅ | ✅ | High | Quant: nonlinear estimation |

---

## Phase 2 — Quantitative Finance & Markets | 2–3 months

### 5.1 Exchange Mechanics & Dynamics

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Market participants | — | ⚡ | ✅ | Critical | Quant: interview context |
| Matching engines | — | ⚡ | ✅ | Critical | Quant: HFT, order execution |
| Order types | — | ⚡ | ✅ | Critical | Quant: desk knowledge |
| Limit Order Book (LOB) dynamics | — | ⚡ | ⚡ | Critical | Quant: market making |
| Bid-ask spread mechanics | — | ⚡ | ⚡ | Critical | Jane Street core topic |
| Order flow toxicity | — | ⚡ | ✅ | Critical | Quant: adverse selection |
| Market impact modeling | — | ⚡ | ⚡ | Critical | Quant: execution cost |
| Hawkes processes | — | ✅ | ✅ | High | Quant: event clustering |

### 5.2 Algorithmic Execution

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| VWAP | — | ⚡ | ✅ | Critical | Quant: execution benchmark |
| TWAP | — | ⚡ | ✅ | Critical | Quant: execution benchmark |
| Implementation Shortfall minimization | — | ⚡ | ✅ | Critical | Quant: optimal execution |
| Almgren-Chriss optimal execution model | — | ⚡ | ⚡ | Critical | Quant: execution theory |
| Inventory risk management | — | ⚡ | ⚡ | Critical | Quant: market making risk |

---

### 6.1 Fixed Income & Credit

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Yield curve bootstrapping | — | ⚡ | ✅ | Critical | Quant: rates desks |
| Duration, Convexity | — | ⚡ | ✅ | Critical | Quant: bond risk |
| Vasicek model | — | ⚡ | ✅ | Critical | Quant: short-rate |
| Hull-White model | — | ⚡ | ✅ | Critical | Quant: interest rate products |
| Credit Risk — Merton model | — | ⚡ | ✅ | Critical | Quant: credit desks |
| Credit Default Swaps (CDS) | — | ⚡ | ✅ | Critical | Quant: credit derivatives |

### 6.2 Derivatives & Advanced Volatility

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Vanilla options pricing | — | ⚡ | ⚡ | Critical | Quant: foundational |
| Exotic options pricing | — | ⚡ | ✅ | Critical | Quant: structuring desks |
| Black-Scholes-Merton paradigm | — | ⚡ | ⚡ | Critical | Quant: must derive |
| Delta, Gamma, Theta, Vega | — | ⚡ | ⚡ | Critical | Quant: desk interview staple |
| Implied volatility surfaces | — | ⚡ | ⚡ | Critical | Quant: vol trading |
| Implied volatility smiles | — | ⚡ | ⚡ | Critical | Quant: market insight |
| Local Volatility — Dupire model | — | ⚡ | ✅ | Critical | Quant: vol modelling |
| Stochastic Volatility — Heston model | — | ⚡ | ⚡ | Critical | Quant: advanced vol |
| Stochastic Volatility — SABR model | — | ⚡ | ✅ | Critical | Quant: rates/FX |
| Fractional calculus | — | ✅ | ✅ | High | Quant: rough vol |
| Rough Volatility modeling | — | ✅ | ✅ | High | Quant: cutting-edge |
| CVA, DVA, FVA (XVA) | — | ⚡ | ✅ | Critical | Quant: bank desks |

---

### 7.1 Portfolio Theory

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Markowitz mean-variance optimization | — | ⚡ | ⚡ | Critical | Quant: foundational |
| Capital Asset Pricing Model (CAPM) | — | ⚡ | ⚡ | Critical | Quant: equity |
| Efficient frontier | — | ⚡ | ⚡ | Critical | Quant: portfolio opt |
| Fama-French factor models | — | ⚡ | ⚡ | Critical | Quant: equity alpha |
| Arbitrage Pricing Theory (APT) | — | ⚡ | ✅ | Critical | Quant: multi-factor |
| Black-Litterman model | — | ⚡ | ✅ | Critical | Quant: active management |
| Hierarchical Risk Parity (HRP) | — | ✅ | ⚡ | High | AI+Quant: ML-based portfolio |

### 7.2 Alpha Research & Risk Infrastructure

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Parametric VaR | — | ⚡ | ✅ | Critical | Quant: risk management |
| Historical VaR | — | ⚡ | ✅ | Critical | Quant: risk management |
| Monte Carlo VaR | ◐ | ⚡ | ⚡ | Critical | Both: simulation |
| Expected Shortfall (CVaR) | — | ⚡ | ✅ | Critical | Quant: tail risk |
| Satellite imagery (alt data) | ◐ | ◐ | ⚡ | High | AI+Quant: alternative data |
| SEC filings NLP | ◐ | ◐ | ⚡ | High | AI+Quant: NLP on filings |
| Web scraping pipelines | ✅ | ◐ | ⚡ | High | AI+Quant: data collection |
| Signal decay analysis | — | ⚡ | ⚡ | Critical | Quant: alpha research |
| Alpha capacity constraints | — | ⚡ | ⚡ | Critical | Quant: strategy scaling |

---

## Phase 3 — Core Machine Learning | 2–3 months

### 8.1 Learning Paradigms & Data Preparation

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Supervised learning | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Unsupervised learning | ⚡ | ✅ | ⚡ | Critical | Universal |
| Reinforcement learning (concept) | ⚡ | ✅ | ⚡ | Critical | AI: deep; Quant: trading strategies |
| Active learning | ✅ | — | ◐ | High | AI: labelling workflows |
| Semi-supervised learning | ✅ | — | ◐ | High | AI: limited labels |
| Self-supervised learning | ⚡ | — | ◐ | Critical | AI: foundation model training |
| Imputation | ✅ | ⚡ | ⚡ | Critical | Both: missing data |
| Outlier detection | ✅ | ⚡ | ⚡ | Critical | Both: data quality |
| Feature scaling | ⚡ | ✅ | ⚡ | Critical | Universal |
| Categorical encoding | ⚡ | ✅ | ⚡ | Critical | Universal |
| Fractional differentiation | — | ⚡ | ⚡ | Critical | Quant: financial stationarity |
| Return stationarity conversions | — | ⚡ | ⚡ | Critical | Quant: financial ML |

### 8.2 Evaluation & Validation

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Accuracy, Precision, Recall, F1 | ⚡ | ✅ | ⚡ | Critical | AI: interview staple |
| ROC curve & AUC | ⚡ | ✅ | ⚡ | Critical | AI: classification |
| Confusion matrix | ⚡ | ✅ | ⚡ | Critical | Universal |
| K-fold cross-validation | ⚡ | ✅ | ⚡ | Critical | Universal |
| Purged cross-validation | — | ⚡ | ⚡ | Critical | Quant: financial ML anti-leakage |
| Embargoed cross-validation | — | ⚡ | ⚡ | Critical | Quant: financial ML anti-leakage |
| Grid search | ⚡ | ✅ | ⚡ | Critical | Universal |
| Random search | ⚡ | ✅ | ⚡ | Critical | Universal |
| Bayesian optimization | ⚡ | ✅ | ⚡ | Critical | Universal |

---

### 9.1 Supervised Learning

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Ridge regression (L2) | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Lasso regression (L1) | ⚡ | ⚡ | ⚡ | Critical | Universal — feature selection |
| ElasticNet | ✅ | ✅ | ✅ | High | Universal |
| Support Vector Machines (SVM) | ⚡ | ◐ | ✅ | Critical | AI: interviews; Quant: less used |
| K-Nearest Neighbors (KNN) | ⚡ | ◐ | ✅ | High | AI: interviews |
| Naive Bayes | ✅ | — | ◐ | High | AI: NLP classification |
| Random forests | ⚡ | ⚡ | ⚡ | Critical | Universal |
| XGBoost | ⚡ | ⚡ | ⚡ | Critical | Universal — industry standard |
| LightGBM | ⚡ | ⚡ | ⚡ | Critical | Universal — faster XGBoost |
| CatBoost | ✅ | ✅ | ✅ | High | Universal |

### 9.2 Unsupervised Learning & Dimensionality Reduction

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| K-means clustering | ⚡ | ✅ | ⚡ | Critical | Universal |
| Hierarchical clustering | ✅ | ✅ | ✅ | High | Quant: HRP hierarchy |
| DBSCAN | ✅ | ◐ | ✅ | High | AI: anomaly detection |
| HDBSCAN | ✅ | ◐ | ✅ | High | AI: density clustering |
| PCA | ⚡ | ⚡ | ⚡ | Critical | Universal — risk factors, features |
| t-SNE | ⚡ | ◐ | ✅ | High | AI: visualization |
| UMAP | ⚡ | ◐ | ✅ | High | AI: embedding visualization |

---

## Phase 4 — Deep Learning & NLP | 2–3 months

### 10.1 Network Mechanics

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Feedforward networks | ⚡ | ✅ | ⚡ | Critical | Universal DL foundation |
| Backpropagation | ⚡ | ◐ | ⚡ | Critical | AI: must derive; Quant: awareness |
| Gradient descent variants | ⚡ | ◐ | ⚡ | Critical | AI: training; Quant: optimization |
| Adam, AdamW optimizers | ⚡ | ◐ | ⚡ | Critical | AI: standard training |
| Learning rate schedulers | ⚡ | — | ✅ | High | AI: training |
| Activation functions | ⚡ | ◐ | ⚡ | Critical | AI: architecture design |
| Dropout regularization | ⚡ | ◐ | ✅ | Critical | AI: overfitting prevention |
| BatchNorm, LayerNorm | ⚡ | ◐ | ✅ | Critical | AI: training stability |

### 10.2 Advanced Neural Topologies

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Convolutional Neural Networks (CNNs) | ⚡ | — | ◐ | Critical | AI: vision, pattern recognition |
| RNNs (vanilla) | ✅ | ✅ | ⚡ | High | Both: sequence modelling |
| LSTMs | ⚡ | ⚡ | ⚡ | Critical | Both: time series |
| GRUs | ⚡ | ✅ | ⚡ | Critical | Both: faster LSTM |
| Autoencoders | ✅ | ◐ | ✅ | High | AI: anomaly detection |
| Variational Autoencoders (VAEs) | ✅ | — | ◐ | High | AI: generative modelling |
| Generative Adversarial Networks (GANs) | ✅ | — | ◐ | High | AI: generative; Quant: scenario gen |
| Diffusion models | ⚡ | — | ◐ | Critical | AI: NVIDIA, Google roles |
| Temporal Fusion Transformers (TFT) | ✅ | ⚡ | ⚡ | Critical | Both: financial forecasting |
| N-BEATS | ✅ | ⚡ | ⚡ | High | Both: time series |
| Graph Neural Networks (GNNs) | ✅ | ◐ | ⚡ | High | AI+Quant: financial networks |

---

### 11.1 Text Representation

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Tokenization | ⚡ | — | ✅ | Critical | AI: NLP foundation |
| Stemming, Lemmatization | ✅ | — | ◐ | High | AI: NLP preprocessing |
| Bag of Words (BoW), TF-IDF | ✅ | ◐ | ✅ | High | AI: classic NLP; Quant: alt data |
| Named Entity Recognition (NER) | ⚡ | ◐ | ✅ | Critical | AI: information extraction |
| Sentiment analysis | ✅ | ⚡ | ⚡ | Critical | Quant: news/earnings signals |
| Word2Vec, GloVe, FastText | ✅ | ◐ | ✅ | High | AI: embeddings |
| Sentence embeddings | ⚡ | ◐ | ⚡ | Critical | AI: RAG; Quant: semantic search |

### 11.2 Domain-Specific & Sequence NLP

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Financial NLP — Loughran-McDonald | — | ⚡ | ⚡ | Critical | Quant: earnings call analysis |
| FinBERT | ◐ | ⚡ | ⚡ | Critical | Quant: sentiment scoring |
| Transformer — Attention mechanisms | ⚡ | ✅ | ⚡ | Critical | Universal |
| Transformer — Encoder-decoder architecture | ⚡ | ✅ | ⚡ | Critical | Universal |

---

## Phase 5 — The Builder's Toolkit & Infrastructure | 2–3 months

### 12.1 Relational & Distributed Storage

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| SQL joins (all types) | ⚡ | ⚡ | ⚡ | Critical | Universal |
| SQL indexing & query optimization | ⚡ | ⚡ | ⚡ | Critical | Universal |
| ACID properties | ⚡ | ✅ | ⚡ | Critical | AI: system design |
| PostgreSQL | ⚡ | ⚡ | ⚡ | Critical | Universal |
| MongoDB (NoSQL document) | ⚡ | ◐ | ✅ | High | AI: unstructured data |
| Redis (NoSQL key-value) | ⚡ | ◐ | ✅ | High | AI: caching; Quant: tick cache |
| Parquet, Apache Arrow | ⚡ | ⚡ | ⚡ | Critical | Both: efficient data storage |
| Data warehouses (BigQuery, Snowflake) | ⚡ | ✅ | ⚡ | Critical | AI: primary; Quant: analytics |
| Vector databases (FAISS, Pinecone) | ⚡ | — | ✅ | Critical | AI: RAG pipelines |
| HNSW algorithm | ⚡ | — | ✅ | High | AI: vector search |

### 13.1 System Architecture

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Fault tolerance | ⚡ | ✅ | ⚡ | Critical | AI: system design rounds |
| Load balancing | ⚡ | ◐ | ⚡ | Critical | AI: system design rounds |
| CAP theorem | ⚡ | ◐ | ⚡ | Critical | AI: system design rounds |
| Consensus protocols (Raft, Paxos) | ⚡ | ◐ | ✅ | High | AI: distributed systems |
| Apache Kafka | ⚡ | ⚡ | ⚡ | Critical | Both: real-time data streaming |
| RabbitMQ | ✅ | ◐ | ✅ | High | AI: message queues |
| ETL / ELT pipelines | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Apache Spark | ⚡ | ✅ | ⚡ | Critical | Both: large-scale data |

### 13.2 Ultra-Low Latency Engineering

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Kernel bypass networking (DPDK) | — | ⚡ | ✅ | Critical | Quant: HFT infrastructure |
| Solarflare OpenOnload | — | ⚡ | ✅ | Critical | Quant: HFT NIC bypass |
| FPGA acceleration concepts | — | ✅ | ✅ | High | Quant: co-location |
| Hardware acceleration | ◐ | ✅ | ✅ | High | AI: GPU; Quant: FPGA/ASIC |
| FIX protocol socket streams | — | ⚡ | ✅ | Critical | Quant: exchange connectivity |

### 14.1 CI/CD & Development Workflows

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Git workflows | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Unit testing | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Integration testing | ⚡ | ✅ | ⚡ | Critical | Universal |
| End-to-end testing | ⚡ | ◐ | ✅ | High | AI: ML pipelines |
| CI pipelines (GitHub Actions) | ⚡ | ✅ | ⚡ | Critical | AI: MLOps |
| CD pipelines | ⚡ | ✅ | ⚡ | Critical | AI: production deployment |
| Code linting | ⚡ | ✅ | ⚡ | Critical | Universal |
| Microservices architectures | ⚡ | ◐ | ✅ | Critical | AI: system design |
| Event-driven architectures | ⚡ | ✅ | ⚡ | Critical | AI: async; Quant: market events |

### 14.2 MLOps & Production Monitoring

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| MLflow | ⚡ | ◐ | ⚡ | Critical | AI: experiment tracking |
| Weights & Biases | ⚡ | ◐ | ⚡ | Critical | AI: experiment tracking |
| Continuous training pipelines | ⚡ | ✅ | ⚡ | Critical | AI: production ML |
| Data drift monitoring | ⚡ | ✅ | ⚡ | Critical | AI: production health |
| Concept drift monitoring | ⚡ | ✅ | ⚡ | Critical | AI: production health |
| FastAPI | ⚡ | ◐ | ⚡ | Critical | AI: model serving |
| Flask | ✅ | ◐ | ✅ | High | AI: rapid prototyping |
| gRPC | ⚡ | ✅ | ⚡ | Critical | AI: high-performance APIs |
| API gateways | ⚡ | ◐ | ✅ | High | AI: microservices |
| OAuth, JWT, RBAC | ⚡ | ◐ | ✅ | High | AI: security layer |

### 15.1 Cloud & Containerization

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Linux server management | ⚡ | ⚡ | ⚡ | Critical | Universal |
| Docker engines | ⚡ | ✅ | ⚡ | Critical | Universal |
| Docker Compose | ⚡ | ✅ | ⚡ | Critical | Universal |
| Kubernetes pod orchestration | ⚡ | ◐ | ⚡ | Critical | AI: model serving at scale |
| Multi-node scaling | ⚡ | ◐ | ⚡ | Critical | AI: distributed training |
| AWS / GCP / Azure | ⚡ | ✅ | ⚡ | Critical | AI: primary; Quant: storage/compute |
| ARM-based instances | ✅ | ◐ | ✅ | High | AI: cost optimization |
| Terraform (IaC) | ⚡ | ◐ | ⚡ | Critical | AI: MLOps infra |
| CUDA GPU provisioning | ⚡ | ◐ | ⚡ | Critical | AI: model training |

---

## Phase 6 — Generative AI | 2 months

### 16.1 LLM Architecture & Mechanics

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Tokens & context windows | ⚡ | ◐ | ✅ | Critical | AI: LLM fundamentals |
| Temperature & sampling strategies | ⚡ | — | ✅ | Critical | AI: LLM control |
| FlashAttention | ⚡ | — | ◐ | Critical | AI: efficiency at scale |
| Multi-Query Attention (MQA) | ⚡ | — | ◐ | High | AI: inference speed |
| Grouped-Query Attention (GQA) | ⚡ | — | ◐ | High | AI: LLM architecture |
| Rotary Position Embedding (RoPE) | ⚡ | — | ◐ | High | AI: LLM architecture |
| Mixture of Experts (MoE) | ⚡ | — | ◐ | High | AI: scaling |
| Small Language Models (SLMs) | ✅ | ◐ | ✅ | High | AI: on-device deployment |
| Knowledge distillation | ⚡ | — | ◐ | Critical | AI: model compression |

### 16.2 Alignment & Customization

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Pretraining | ⚡ | — | ◐ | Critical | AI: LLM lifecycle |
| Fine-tuning | ⚡ | ◐ | ✅ | Critical | AI: customization; Quant: FinBERT |
| RLHF | ⚡ | — | ◐ | Critical | AI: alignment |
| Direct Preference Optimization (DPO) | ⚡ | — | ◐ | High | AI: alignment |
| Kahneman-Tversky Optimization (KTO) | ✅ | — | — | Medium | AI: advanced alignment |
| Instruction tuning | ⚡ | — | ◐ | Critical | AI: task-specific models |
| LoRA (Parameter-Efficient Fine-Tuning) | ⚡ | — | ◐ | Critical | AI: efficient fine-tuning |

---

### 17.1 RAG — Core Systems & Retrieval

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Semantic search | ⚡ | ◐ | ⚡ | Critical | AI: RAG; Quant: document search |
| Hybrid search | ⚡ | ◐ | ✅ | Critical | AI: retrieval accuracy |
| Vector embeddings | ⚡ | ◐ | ⚡ | Critical | Universal for LLM apps |
| Chunking strategies | ⚡ | — | ✅ | Critical | AI: document ingestion |
| Metadata handling | ⚡ | — | ✅ | High | AI: retrieval filtering |
| Indexing | ⚡ | ◐ | ⚡ | Critical | AI: search performance |
| Query transformation | ⚡ | — | ✅ | High | AI: RAG accuracy |
| Query routing | ⚡ | — | ✅ | High | AI: multi-source RAG |
| Re-ranking | ⚡ | — | ✅ | Critical | AI: retrieval precision |

### 17.2 Advanced RAG Methodologies

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Knowledge graphs | ⚡ | ◐ | ⚡ | High | AI: structured retrieval; Quant: financial graphs |
| Multi-modal RAG | ⚡ | — | ◐ | High | AI: vision+text |
| Document parsing | ⚡ | ◐ | ⚡ | High | Both: alternative data |
| Self-RAG | ✅ | — | ◐ | High | AI: advanced retrieval |

---

### 18.1 Prompt Engineering & Reasoning

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Chain-of-Thought (CoT) prompting | ⚡ | ◐ | ✅ | Critical | AI: reasoning tasks |
| ReAct prompting | ⚡ | — | ✅ | Critical | AI: agent tools |
| Tree of Thoughts (ToT) | ✅ | — | ◐ | High | AI: complex reasoning |
| Self-reflection prompting | ✅ | — | ◐ | High | AI: output quality |
| DSPy (Declarative AI) | ✅ | — | ◐ | High | AI: programmatic prompting |
| Prompt compilation | ✅ | — | ◐ | High | AI: optimization |

---

## Phase 7 — Agents & Reinforcement Learning | 1.5–2 months

### 19.1 RL Fundamentals & Value-Based Methods

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Markov Decision Processes (MDPs) | ⚡ | ⚡ | ⚡ | Critical | AI: RL; Quant: trading strategy |
| Bellman equations | ⚡ | ⚡ | ⚡ | Critical | Universal RL foundation |
| Q-Learning | ⚡ | ✅ | ⚡ | Critical | Universal |
| Deep Q-Networks (DQN) | ⚡ | ✅ | ⚡ | Critical | Universal |

### 19.2 Advanced RL Frameworks

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Policy gradients (REINFORCE) | ⚡ | ◐ | ⚡ | Critical | AI: primary; Quant: strategy research |
| Proximal Policy Optimization (PPO) | ⚡ | ◐ | ⚡ | Critical | AI: RLHF; Quant: strategy |
| Soft Actor-Critic (SAC) | ⚡ | ◐ | ✅ | High | AI: continuous control |
| Multi-Agent RL (MARL) | ⚡ | ◐ | ⚡ | High | AI: multi-agent; Quant: market sim |

---

### 20.1 Agent Architecture

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Agent loops | ⚡ | — | ✅ | Critical | AI: agentic systems |
| Tool usage schemas | ⚡ | — | ✅ | Critical | AI: function-calling agents |
| Function calling | ⚡ | — | ✅ | Critical | AI: LLM tool integration |
| Stateful memory management | ⚡ | — | ✅ | Critical | AI: persistent agents |
| Human-in-the-loop workflows | ⚡ | ◐ | ✅ | High | AI: production safety |

### 20.2 Frameworks & Routing Logic

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| OpenRouter integrations | ✅ | — | ◐ | High | AI: multi-LLM routing |
| n8n workflow automation | ✅ | — | ◐ | Medium | AI: visual pipelines |
| Apache Airflow | ⚡ | ✅ | ⚡ | Critical | Both: pipeline orchestration |
| LangGraph | ⚡ | — | ✅ | Critical | AI: stateful agents |
| AutoGen | ⚡ | — | ◐ | High | AI: multi-agent |
| CrewAI | ✅ | — | ◐ | High | AI: role-based agents |

---

## Phase 8 — Production Safety, Evaluation & Portfolios | 1–1.5 months

### 21.1 LLM Deployment & Inference Optimization

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| AWQ quantization | ⚡ | — | ◐ | Critical | AI: efficient inference |
| GPTQ quantization | ⚡ | — | ◐ | Critical | AI: efficient inference |
| GGUF quantization | ⚡ | — | ◐ | Critical | AI: local LLM deployment |
| vLLM inference engine | ⚡ | — | ◐ | Critical | AI: high-throughput serving |
| Ollama | ✅ | — | ◐ | High | AI: local development |
| TensorRT-LLM | ⚡ | — | ◐ | Critical | AI: NVIDIA GPU inference |
| KV cache optimization | ⚡ | — | ◐ | Critical | AI: latency reduction |
| Prompt caching | ⚡ | — | ◐ | High | AI: API cost reduction |
| Speculative decoding | ⚡ | — | ◐ | High | AI: inference acceleration |

### 22.1 AI Safety & Guardrails

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Prompt injection defenses | ⚡ | — | ◐ | Critical | AI: production security |
| Data exfiltration defenses | ⚡ | ✅ | ⚡ | Critical | Both: compliance |
| Jailbreaking defenses | ⚡ | — | ◐ | Critical | AI: product safety |
| NeMo Guardrails | ✅ | — | ◐ | High | AI: LLM safety layer |
| PII masking | ⚡ | ⚡ | ⚡ | Critical | Both: regulatory compliance |
| AI watermarking | ✅ | — | ◐ | High | AI: content attribution |

### 22.2 Evaluation Metrics

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| LLM-as-a-Judge | ⚡ | — | ◐ | Critical | AI: model evaluation |
| Context precision & recall | ⚡ | — | ✅ | Critical | AI: RAG evaluation |
| MMLU benchmark | ⚡ | — | ◐ | High | AI: capability evaluation |
| HumanEval benchmark | ⚡ | ◐ | ✅ | High | AI: code evaluation |
| Needle-in-a-Haystack testing | ✅ | — | ◐ | High | AI: long context eval |
| LLM tracing | ⚡ | — | ◐ | Critical | AI: debugging agents |
| LangSmith | ⚡ | — | ◐ | Critical | AI: agent observability |
| Phoenix (Arize) | ✅ | — | ◐ | High | AI: LLM monitoring |

---

### 23.1 & 23.2 Capstone Engineering Portfolios

| Topic | AI & DS | Quant | AI + Quant | Priority | Notes |
|---|:---:|:---:|:---:|---|---|
| Robust server environments | ✅ | ✅ | ✅ | High | Universal |
| Containerized environments (Docker) | ⚡ | ✅ | ⚡ | Critical | Universal |
| Multi-node environments | ⚡ | ◐ | ✅ | High | AI: distributed training |
| Continuous model training pipelines | ⚡ | ✅ | ⚡ | Critical | Both: production ML |
| Full-stack portfolio websites | ✅ | ✅ | ✅ | High | Universal |
| 3D portfolio websites (Three Fiber, Spline) | ✅ | — | ◐ | Medium | AI: visual differentiation |
| Backend data pipeline visualization | ✅ | ✅ | ✅ | High | Universal |
| Financial sentiment analysis engine | ◐ | ✅ | ⚡ | Critical | AI+Quant: bridge project |
| Statistical arbitrage backtesting pipeline | — | ⚡ | ⚡ | Critical | Quant+AI: hiring signal |
| Multi-agent orchestration (project) | ⚡ | — | ✅ | Critical | AI: showcase |
| Purged cross-validation implementation | — | ⚡ | ⚡ | Critical | Quant: anti-leakage |

---

## Topic Count Summary

| Track | ⚡ Critical | ✅ High | ◐ Secondary | — Not Required |
|---|:---:|:---:|:---:|:---:|
| **AI & DS only** | 67 | 38 | 24 | 59 |
| **Quant only** | 71 | 29 | 41 | 47 |
| **AI + Quant (both)** | 138 | 52 | — | 0 |

---

## Track Differentiation by Phase — Quick Reference

| Phase | AI & DS Focus | Quant Focus | Shared / Overlap |
|---|---|---|---|
| **Phase 1** | Heavy DSA (LeetCode patterns), GIL, async I/O, probabilistic ML | C++ memory management, SIMD/cache, lock-free, stochastic calculus, Itô, Girsanov, copulas | Core Python, linear algebra, probability, sorting, graphs |
| **Phase 2** | (Not primary — skim) | Everything: microstructure, LOB, Greeks, Black-Scholes, XVA, Markowitz, VaR | Alternative data (satellite, NLP on filings) |
| **Phase 3** | Self-supervised learning, active learning, full eval suite (ROC, F1) | Fractional differentiation, purged/embargoed CV, return stationarity | Regularized regression, ensembles, clustering, PCA |
| **Phase 4** | CNNs, diffusion models, full NLP stack, autoencoders, VAEs, GANs | LSTMs/GRUs (time series), FinBERT, Loughran-McDonald, TFT/N-BEATS | Transformers, attention, sentence embeddings, GNNs |
| **Phase 5** | Vector databases, Kubernetes, Kafka, system design rounds, MLOps, cloud | Kernel bypass (DPDK), FIX protocol, FPGA, ultra-low latency | SQL, Parquet, Docker, ETL/Spark, Git, CI/CD |
| **Phase 6** | All of it: LLM arch, LoRA, RLHF, DPO, full RAG stack, prompt engineering | Skim architecture only; fine-tuning FinBERT relevant | Semantic search, knowledge graphs, document parsing |
| **Phase 7** | Full agent stack: LangGraph, AutoGen, CrewAI, PPO/SAC, MARL | MDPs, Bellman, Q-Learning, DQN (for strategy research) | MDPs, Bellman equations, Q-Learning |
| **Phase 8** | Full LLM deployment: vLLM, quantization, safety, eval benchmarks | PII masking, data exfiltration defenses (compliance) | Containerized infra, backtesting portfolio, training pipelines |
