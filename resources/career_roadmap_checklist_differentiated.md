# Differentiated Career Roadmap Checklists
This document provides personalized, track-specific checklists extracted from the master career roadmap. Choose your track below to view and complete your specific requirements.

---

## Table of Contents
- [AI & DS Track Checklist](#ai--ds-track-checklist)
- [Quant Track Checklist](#quant-track-checklist)
- [AI + Quant (Hybrid) Track Checklist](#ai-+-quant-hybrid-track-checklist)

---

# AI & DS Track Checklist
### Track Placement: Google · Meta · Apple · Microsoft · NVIDIA · Palantir · more

**Legend:**
- `⚡` Critical — highest interview weight
- `✅` Required — core to this track
- `◐` Useful but secondary depth needed

## Phase 1 — The Bedrock

### 1.1 Programming Fundamentals
- [ ] **Variables, Data types, Operators** `[⚡ Critical]`
- [ ] **Control flow, Functions, Recursion** `[⚡ Critical]`
- [ ] **Type hinting** `[✅ Required]` — *Python best practice*
- [ ] **Input / Output, File handling** `[✅ Required]`
- [ ] **Regular expressions** `[✅ Required]` — *AI: NLP pipelines; Quant: log parsing*
- [ ] **Memory — Stack & Heap** `[✅ Required]` — *Quant: deeper for C++*
- [ ] **Garbage collection** `[✅ Required]` — *Python internals*
- [ ] **Reference counting** `[◐ Secondary]` — *C++ RAII overlap*
- [ ] **Global Interpreter Lock (GIL)** `[✅ Required]` — *Quant: concurrency bottleneck*

### 1.2 Advanced Programming & Low-Latency Systems
- [ ] **Object-Oriented Programming** `[⚡ Critical]`
- [ ] **Functional Programming** `[✅ Required]`
- [ ] **Iterators, Generators** `[✅ Required]` — *Data pipelines*
- [ ] **Decorators** `[✅ Required]` — *AI: MLOps; Quant: less critical*
- [ ] **Metaprogramming** `[◐ Secondary]` — *Advanced Python only*
- [ ] **Concurrency & Multithreading** `[✅ Required]` — *Quant: real-time systems*
- [ ] **Asynchronous I/O** `[✅ Required]` — *AI: APIs; Quant: feed handling*

### 2.1 Linear & Hash-Based Data Structures
- [ ] **Arrays, Linked lists** `[⚡ Critical]` — *Universal interview topic*
- [ ] **Stacks, Queues** `[⚡ Critical]`
- [ ] **Hash tables, Hash sets** `[⚡ Critical]`
- [ ] **Collision resolution strategies** `[✅ Required]` — *Systems interviews*
- [ ] **Bloom filters** `[✅ Required]` — *AI: streaming; Quant: dedup*
- [ ] **Count-Min Sketch** `[✅ Required]` — *AI: frequency estimation*

### 2.2 Tree & Graph Structures
- [ ] **Binary Search Trees** `[⚡ Critical]` — *AI: heavier LeetCode focus*
- [ ] **AVL trees** `[✅ Required]` — *AI: coding interviews*
- [ ] **Red-Black trees** `[✅ Required]` — *STL internals (Quant: C++)*
- [ ] **B-trees** `[✅ Required]` — *Database internals*
- [ ] **Heaps — Binary & Priority queues** `[⚡ Critical]` — *Universal — order books, Dijkstra*
- [ ] **Tries** `[⚡ Critical]` — *AI: NLP/autocomplete interviews*
- [ ] **Graphs (Directed, Undirected, Weighted)** `[⚡ Critical]`
- [ ] **Adjacency representations** `[⚡ Critical]`

### 3.1 Core Algorithm Design
- [ ] **Big-O Time & Space complexity** `[⚡ Critical]`
- [ ] **Binary search** `[⚡ Critical]`
- [ ] **Merge sort, Quick sort, Heap sort** `[⚡ Critical]` — *AI: more LeetCode weight*
- [ ] **Divide and conquer** `[⚡ Critical]` — *AI: interviews; Quant: algorithms*
- [ ] **Greedy approaches** `[⚡ Critical]` — *AI: heavy; Quant: lighter*
- [ ] **Backtracking** `[⚡ Critical]` — *AI: NeetCode patterns*

### 3.2 Graph & Dynamic Algorithms
- [ ] **BFS, DFS** `[⚡ Critical]`
- [ ] **Dijkstra's algorithm** `[⚡ Critical]`
- [ ] **A* algorithm** `[✅ Required]` — *AI: search; Quant: routing*
- [ ] **Topological sort** `[⚡ Critical]` — *AI: DAGs, pipelines*
- [ ] **Dynamic programming — Memoization** `[⚡ Critical]` — *AI: LeetCode critical*
- [ ] **Dynamic programming — Tabulation** `[⚡ Critical]` — *AI: LeetCode critical*
- [ ] **String matching — KMP** `[⚡ Critical]` — *AI: NLP/coding interviews*
- [ ] **String matching — Rabin-Karp** `[✅ Required]` — *AI: rolling hash pattern*

### 4.1 Linear Algebra & Multivariable Calculus
- [ ] **Vectors, Matrices, Tensors** `[⚡ Critical]` — *Universal math foundation*
- [ ] **Determinants** `[✅ Required]` — *Quant: hedging, covariance*
- [ ] **Eigenvalues & Eigenvectors** `[⚡ Critical]` — *Universal — PCA, risk*
- [ ] **SVD** `[⚡ Critical]` — *AI: dimensionality; Quant: risk*
- [ ] **Cholesky decomposition** `[◐ Secondary]` — *Quant: covariance matrices*
- [ ] **LU decomposition** `[◐ Secondary]` — *Quant: numerical finance*
- [ ] **QR decomposition** `[✅ Required]`
- [ ] **Derivatives, Gradients** `[⚡ Critical]` — *AI: backprop; Quant: Greeks*
- [ ] **Jacobians, Hessians** `[✅ Required]` — *AI: optimization; Quant: risk*
- [ ] **Convex optimization** `[✅ Required]` — *Quant: portfolio opt*
- [ ] **Non-convex optimization** `[✅ Required]` — *AI: training NNs*
- [ ] **Lagrange multipliers** `[✅ Required]` — *Quant: constrained portfolio opt*
- [ ] **KKT conditions** `[✅ Required]` — *Quant: portfolio constraints*

### 4.2 Probability, Statistics & Risk Math
- [ ] **Probability spaces, Random variables** `[⚡ Critical]`
- [ ] **Bayes' theorem** `[⚡ Critical]`
- [ ] **Normal distribution** `[⚡ Critical]`
- [ ] **Binomial distribution** `[✅ Required]` — *Quant: brainteasers*
- [ ] **Poisson distribution** `[✅ Required]` — *Quant: arrival processes*
- [ ] **Lognormal distribution** `[◐ Secondary]` — *Quant: asset prices*
- [ ] **Exponential distribution** `[✅ Required]` — *Quant: event timing*
- [ ] **Gamma distribution** `[✅ Required]` — *Bayesian inference*
- [ ] **Hypothesis testing & p-values** `[⚡ Critical]` — *AI: experimentation*
- [ ] **A/B testing** `[⚡ Critical]` — *AI: product; Quant: signal test*
- [ ] **Maximum Likelihood Estimation (MLE)** `[⚡ Critical]`
- [ ] **Central Limit Theorem (CLT)** `[⚡ Critical]`

### 4.3 Stochastic Calculus & Econometrics
- [ ] **Markov chains** `[✅ Required]` — *AI: RL; Quant: pricing*
- [ ] **Random walks** `[◐ Secondary]` — *Quant: price modelling*
- [ ] **Time series stationarity** `[✅ Required]` — *Both: time series modelling*
- [ ] **Cointegration** `[◐ Secondary]` — *Quant: pairs trading*
- [ ] **ARIMA models** `[✅ Required]` — *Both: forecasting*
- [ ] **GARCH models** `[◐ Secondary]` — *Quant: volatility modelling*
- [ ] **Kalman filters** `[◐ Secondary]` — *Quant: signal filtering*

---

## Phase 2 — Quantitative Finance & Markets

### 7.2 Alpha Research & Risk Infrastructure
- [ ] **Monte Carlo VaR** `[◐ Secondary]` — *Both: simulation*
- [ ] **Satellite imagery (alt data)** `[◐ Secondary]` — *AI+Quant: alternative data*
- [ ] **SEC filings NLP** `[◐ Secondary]` — *AI+Quant: NLP on filings*
- [ ] **Web scraping pipelines** `[✅ Required]` — *AI+Quant: data collection*

---

## Phase 3 — Core Machine Learning

### 8.1 Learning Paradigms & Data Preparation
- [ ] **Supervised learning** `[⚡ Critical]`
- [ ] **Unsupervised learning** `[⚡ Critical]`
- [ ] **Reinforcement learning (concept)** `[⚡ Critical]` — *AI: deep; Quant: trading strategies*
- [ ] **Active learning** `[✅ Required]` — *AI: labelling workflows*
- [ ] **Semi-supervised learning** `[✅ Required]` — *AI: limited labels*
- [ ] **Self-supervised learning** `[⚡ Critical]` — *AI: foundation model training*
- [ ] **Imputation** `[✅ Required]` — *Both: missing data*
- [ ] **Outlier detection** `[✅ Required]` — *Both: data quality*
- [ ] **Feature scaling** `[⚡ Critical]`
- [ ] **Categorical encoding** `[⚡ Critical]`

### 8.2 Evaluation & Validation
- [ ] **Accuracy, Precision, Recall, F1** `[⚡ Critical]` — *AI: interview staple*
- [ ] **ROC curve & AUC** `[⚡ Critical]` — *AI: classification*
- [ ] **Confusion matrix** `[⚡ Critical]`
- [ ] **K-fold cross-validation** `[⚡ Critical]`
- [ ] **Grid search** `[⚡ Critical]`
- [ ] **Random search** `[⚡ Critical]`
- [ ] **Bayesian optimization** `[⚡ Critical]`

### 9.1 Supervised Learning
- [ ] **Ridge regression (L2)** `[⚡ Critical]`
- [ ] **Lasso regression (L1)** `[⚡ Critical]` — *Universal — feature selection*
- [ ] **ElasticNet** `[✅ Required]`
- [ ] **Support Vector Machines (SVM)** `[⚡ Critical]` — *AI: interviews; Quant: less used*
- [ ] **K-Nearest Neighbors (KNN)** `[⚡ Critical]` — *AI: interviews*
- [ ] **Naive Bayes** `[✅ Required]` — *AI: NLP classification*
- [ ] **Random forests** `[⚡ Critical]`
- [ ] **XGBoost** `[⚡ Critical]` — *Universal — industry standard*
- [ ] **LightGBM** `[⚡ Critical]` — *Universal — faster XGBoost*
- [ ] **CatBoost** `[✅ Required]`

### 9.2 Unsupervised Learning & Dimensionality Reduction
- [ ] **K-means clustering** `[⚡ Critical]`
- [ ] **Hierarchical clustering** `[✅ Required]` — *Quant: HRP hierarchy*
- [ ] **DBSCAN** `[✅ Required]` — *AI: anomaly detection*
- [ ] **HDBSCAN** `[✅ Required]` — *AI: density clustering*
- [ ] **PCA** `[⚡ Critical]` — *Universal — risk factors, features*
- [ ] **t-SNE** `[⚡ Critical]` — *AI: visualization*
- [ ] **UMAP** `[⚡ Critical]` — *AI: embedding visualization*

---

## Phase 4 — Deep Learning & NLP

### 10.1 Network Mechanics
- [ ] **Feedforward networks** `[⚡ Critical]` — *Universal DL foundation*
- [ ] **Backpropagation** `[⚡ Critical]` — *AI: must derive; Quant: awareness*
- [ ] **Gradient descent variants** `[⚡ Critical]` — *AI: training; Quant: optimization*
- [ ] **Adam, AdamW optimizers** `[⚡ Critical]` — *AI: standard training*
- [ ] **Learning rate schedulers** `[⚡ Critical]` — *AI: training*
- [ ] **Activation functions** `[⚡ Critical]` — *AI: architecture design*
- [ ] **Dropout regularization** `[⚡ Critical]` — *AI: overfitting prevention*
- [ ] **BatchNorm, LayerNorm** `[⚡ Critical]` — *AI: training stability*

### 10.2 Advanced Neural Topologies
- [ ] **Convolutional Neural Networks (CNNs)** `[⚡ Critical]` — *AI: vision, pattern recognition*
- [ ] **RNNs (vanilla)** `[✅ Required]` — *Both: sequence modelling*
- [ ] **LSTMs** `[⚡ Critical]` — *Both: time series*
- [ ] **GRUs** `[⚡ Critical]` — *Both: faster LSTM*
- [ ] **Autoencoders** `[✅ Required]` — *AI: anomaly detection*
- [ ] **Variational Autoencoders (VAEs)** `[✅ Required]` — *AI: generative modelling*
- [ ] **Generative Adversarial Networks (GANs)** `[✅ Required]` — *AI: generative; Quant: scenario gen*
- [ ] **Diffusion models** `[⚡ Critical]` — *AI: NVIDIA, Google roles*
- [ ] **Temporal Fusion Transformers (TFT)** `[✅ Required]` — *Both: financial forecasting*
- [ ] **N-BEATS** `[✅ Required]` — *Both: time series*
- [ ] **Graph Neural Networks (GNNs)** `[✅ Required]` — *AI+Quant: financial networks*

### 11.1 Text Representation
- [ ] **Tokenization** `[⚡ Critical]` — *AI: NLP foundation*
- [ ] **Stemming, Lemmatization** `[✅ Required]` — *AI: NLP preprocessing*
- [ ] **Bag of Words (BoW), TF-IDF** `[✅ Required]` — *AI: classic NLP; Quant: alt data*
- [ ] **Named Entity Recognition (NER)** `[⚡ Critical]` — *AI: information extraction*
- [ ] **Sentiment analysis** `[✅ Required]` — *Quant: news/earnings signals*
- [ ] **Word2Vec, GloVe, FastText** `[✅ Required]` — *AI: embeddings*
- [ ] **Sentence embeddings** `[⚡ Critical]` — *AI: RAG; Quant: semantic search*

### 11.2 Domain-Specific & Sequence NLP
- [ ] **FinBERT** `[◐ Secondary]` — *Quant: sentiment scoring*
- [ ] **Transformer — Attention mechanisms** `[⚡ Critical]`
- [ ] **Transformer — Encoder-decoder architecture** `[⚡ Critical]`

---

## Phase 5 — The Builder's Toolkit & Infrastructure

### 12.1 Relational & Distributed Storage
- [ ] **SQL joins (all types)** `[⚡ Critical]`
- [ ] **SQL indexing & query optimization** `[⚡ Critical]`
- [ ] **ACID properties** `[⚡ Critical]` — *AI: system design*
- [ ] **PostgreSQL** `[⚡ Critical]`
- [ ] **MongoDB (NoSQL document)** `[⚡ Critical]` — *AI: unstructured data*
- [ ] **Redis (NoSQL key-value)** `[⚡ Critical]` — *AI: caching; Quant: tick cache*
- [ ] **Parquet, Apache Arrow** `[⚡ Critical]` — *Both: efficient data storage*
- [ ] **Data warehouses (BigQuery, Snowflake)** `[⚡ Critical]` — *AI: primary; Quant: analytics*
- [ ] **Vector databases (FAISS, Pinecone)** `[⚡ Critical]` — *AI: RAG pipelines*
- [ ] **HNSW algorithm** `[⚡ Critical]` — *AI: vector search*

### 13.1 System Architecture
- [ ] **Fault tolerance** `[⚡ Critical]` — *AI: system design rounds*
- [ ] **Load balancing** `[⚡ Critical]` — *AI: system design rounds*
- [ ] **CAP theorem** `[⚡ Critical]` — *AI: system design rounds*
- [ ] **Consensus protocols (Raft, Paxos)** `[⚡ Critical]` — *AI: distributed systems*
- [ ] **Apache Kafka** `[⚡ Critical]` — *Both: real-time data streaming*
- [ ] **RabbitMQ** `[✅ Required]` — *AI: message queues*
- [ ] **ETL / ELT pipelines** `[⚡ Critical]`
- [ ] **Apache Spark** `[⚡ Critical]` — *Both: large-scale data*

### 13.2 Ultra-Low Latency Engineering
- [ ] **Hardware acceleration** `[◐ Secondary]` — *AI: GPU; Quant: FPGA/ASIC*

### 14.1 CI/CD & Development Workflows
- [ ] **Git workflows** `[⚡ Critical]`
- [ ] **Unit testing** `[⚡ Critical]`
- [ ] **Integration testing** `[⚡ Critical]`
- [ ] **End-to-end testing** `[⚡ Critical]` — *AI: ML pipelines*
- [ ] **CI pipelines (GitHub Actions)** `[⚡ Critical]` — *AI: MLOps*
- [ ] **CD pipelines** `[⚡ Critical]` — *AI: production deployment*
- [ ] **Code linting** `[⚡ Critical]`
- [ ] **Microservices architectures** `[⚡ Critical]` — *AI: system design*
- [ ] **Event-driven architectures** `[⚡ Critical]` — *AI: async; Quant: market events*

### 14.2 MLOps & Production Monitoring
- [ ] **MLflow** `[⚡ Critical]` — *AI: experiment tracking*
- [ ] **Weights & Biases** `[⚡ Critical]` — *AI: experiment tracking*
- [ ] **Continuous training pipelines** `[⚡ Critical]` — *AI: production ML*
- [ ] **Data drift monitoring** `[⚡ Critical]` — *AI: production health*
- [ ] **Concept drift monitoring** `[⚡ Critical]` — *AI: production health*
- [ ] **FastAPI** `[⚡ Critical]` — *AI: model serving*
- [ ] **Flask** `[✅ Required]` — *AI: rapid prototyping*
- [ ] **gRPC** `[⚡ Critical]` — *AI: high-performance APIs*
- [ ] **API gateways** `[⚡ Critical]` — *AI: microservices*
- [ ] **OAuth, JWT, RBAC** `[⚡ Critical]` — *AI: security layer*

### 15.1 Cloud & Containerization
- [ ] **Linux server management** `[⚡ Critical]`
- [ ] **Docker engines** `[⚡ Critical]`
- [ ] **Docker Compose** `[⚡ Critical]`
- [ ] **Kubernetes pod orchestration** `[⚡ Critical]` — *AI: model serving at scale*
- [ ] **Multi-node scaling** `[⚡ Critical]` — *AI: distributed training*
- [ ] **AWS / GCP / Azure** `[⚡ Critical]` — *AI: primary; Quant: storage/compute*
- [ ] **ARM-based instances** `[✅ Required]` — *AI: cost optimization*
- [ ] **Terraform (IaC)** `[⚡ Critical]` — *AI: MLOps infra*
- [ ] **CUDA GPU provisioning** `[⚡ Critical]` — *AI: model training*

---

## Phase 6 — Generative AI

### 16.1 LLM Architecture & Mechanics
- [ ] **Tokens & context windows** `[⚡ Critical]` — *AI: LLM fundamentals*
- [ ] **Temperature & sampling strategies** `[⚡ Critical]` — *AI: LLM control*
- [ ] **FlashAttention** `[⚡ Critical]` — *AI: efficiency at scale*
- [ ] **Multi-Query Attention (MQA)** `[⚡ Critical]` — *AI: inference speed*
- [ ] **Grouped-Query Attention (GQA)** `[⚡ Critical]` — *AI: LLM architecture*
- [ ] **Rotary Position Embedding (RoPE)** `[⚡ Critical]` — *AI: LLM architecture*
- [ ] **Mixture of Experts (MoE)** `[⚡ Critical]` — *AI: scaling*
- [ ] **Small Language Models (SLMs)** `[✅ Required]` — *AI: on-device deployment*
- [ ] **Knowledge distillation** `[⚡ Critical]` — *AI: model compression*

### 16.2 Alignment & Customization
- [ ] **Pretraining** `[⚡ Critical]` — *AI: LLM lifecycle*
- [ ] **Fine-tuning** `[⚡ Critical]` — *AI: customization; Quant: FinBERT*
- [ ] **RLHF** `[⚡ Critical]` — *AI: alignment*
- [ ] **Direct Preference Optimization (DPO)** `[⚡ Critical]` — *AI: alignment*
- [ ] **Kahneman-Tversky Optimization (KTO)** `[✅ Required]` — *AI: advanced alignment*
- [ ] **Instruction tuning** `[⚡ Critical]` — *AI: task-specific models*
- [ ] **LoRA (Parameter-Efficient Fine-Tuning)** `[⚡ Critical]` — *AI: efficient fine-tuning*

### 17.1 RAG — Core Systems & Retrieval
- [ ] **Semantic search** `[⚡ Critical]` — *AI: RAG; Quant: document search*
- [ ] **Hybrid search** `[⚡ Critical]` — *AI: retrieval accuracy*
- [ ] **Vector embeddings** `[⚡ Critical]` — *Universal for LLM apps*
- [ ] **Chunking strategies** `[⚡ Critical]` — *AI: document ingestion*
- [ ] **Metadata handling** `[⚡ Critical]` — *AI: retrieval filtering*
- [ ] **Indexing** `[⚡ Critical]` — *AI: search performance*
- [ ] **Query transformation** `[⚡ Critical]` — *AI: RAG accuracy*
- [ ] **Query routing** `[⚡ Critical]` — *AI: multi-source RAG*
- [ ] **Re-ranking** `[⚡ Critical]` — *AI: retrieval precision*

### 17.2 Advanced RAG Methodologies
- [ ] **Knowledge graphs** `[⚡ Critical]` — *AI: structured retrieval; Quant: financial graphs*
- [ ] **Multi-modal RAG** `[⚡ Critical]` — *AI: vision+text*
- [ ] **Document parsing** `[⚡ Critical]` — *Both: alternative data*
- [ ] **Self-RAG** `[✅ Required]` — *AI: advanced retrieval*

### 18.1 Prompt Engineering & Reasoning
- [ ] **Chain-of-Thought (CoT) prompting** `[⚡ Critical]` — *AI: reasoning tasks*
- [ ] **ReAct prompting** `[⚡ Critical]` — *AI: agent tools*
- [ ] **Tree of Thoughts (ToT)** `[✅ Required]` — *AI: complex reasoning*
- [ ] **Self-reflection prompting** `[✅ Required]` — *AI: output quality*
- [ ] **DSPy (Declarative AI)** `[✅ Required]` — *AI: programmatic prompting*
- [ ] **Prompt compilation** `[✅ Required]` — *AI: optimization*

---

## Phase 7 — Agents & Reinforcement Learning

### 19.1 RL Fundamentals & Value-Based Methods
- [ ] **Markov Decision Processes (MDPs)** `[⚡ Critical]` — *AI: RL; Quant: trading strategy*
- [ ] **Bellman equations** `[⚡ Critical]` — *Universal RL foundation*
- [ ] **Q-Learning** `[⚡ Critical]`
- [ ] **Deep Q-Networks (DQN)** `[⚡ Critical]`

### 19.2 Advanced RL Frameworks
- [ ] **Policy gradients (REINFORCE)** `[⚡ Critical]` — *AI: primary; Quant: strategy research*
- [ ] **Proximal Policy Optimization (PPO)** `[⚡ Critical]` — *AI: RLHF; Quant: strategy*
- [ ] **Soft Actor-Critic (SAC)** `[⚡ Critical]` — *AI: continuous control*
- [ ] **Multi-Agent RL (MARL)** `[⚡ Critical]` — *AI: multi-agent; Quant: market sim*

### 20.1 Agent Architecture
- [ ] **Agent loops** `[⚡ Critical]` — *AI: agentic systems*
- [ ] **Tool usage schemas** `[⚡ Critical]` — *AI: function-calling agents*
- [ ] **Function calling** `[⚡ Critical]` — *AI: LLM tool integration*
- [ ] **Stateful memory management** `[⚡ Critical]` — *AI: persistent agents*
- [ ] **Human-in-the-loop workflows** `[⚡ Critical]` — *AI: production safety*

### 20.2 Frameworks & Routing Logic
- [ ] **OpenRouter integrations** `[✅ Required]` — *AI: multi-LLM routing*
- [ ] **n8n workflow automation** `[✅ Required]` — *AI: visual pipelines*
- [ ] **Apache Airflow** `[⚡ Critical]` — *Both: pipeline orchestration*
- [ ] **LangGraph** `[⚡ Critical]` — *AI: stateful agents*
- [ ] **AutoGen** `[⚡ Critical]` — *AI: multi-agent*
- [ ] **CrewAI** `[✅ Required]` — *AI: role-based agents*

---

## Phase 8 — Production Safety, Evaluation & Portfolios

### 21.1 LLM Deployment & Inference Optimization
- [ ] **AWQ quantization** `[⚡ Critical]` — *AI: efficient inference*
- [ ] **GPTQ quantization** `[⚡ Critical]` — *AI: efficient inference*
- [ ] **GGUF quantization** `[⚡ Critical]` — *AI: local LLM deployment*
- [ ] **vLLM inference engine** `[⚡ Critical]` — *AI: high-throughput serving*
- [ ] **Ollama** `[✅ Required]` — *AI: local development*
- [ ] **TensorRT-LLM** `[⚡ Critical]` — *AI: NVIDIA GPU inference*
- [ ] **KV cache optimization** `[⚡ Critical]` — *AI: latency reduction*
- [ ] **Prompt caching** `[⚡ Critical]` — *AI: API cost reduction*
- [ ] **Speculative decoding** `[⚡ Critical]` — *AI: inference acceleration*

### 22.1 AI Safety & Guardrails
- [ ] **Prompt injection defenses** `[⚡ Critical]` — *AI: production security*
- [ ] **Data exfiltration defenses** `[⚡ Critical]` — *Both: compliance*
- [ ] **Jailbreaking defenses** `[⚡ Critical]` — *AI: product safety*
- [ ] **NeMo Guardrails** `[✅ Required]` — *AI: LLM safety layer*
- [ ] **PII masking** `[⚡ Critical]` — *Both: regulatory compliance*
- [ ] **AI watermarking** `[✅ Required]` — *AI: content attribution*

### 22.2 Evaluation Metrics
- [ ] **LLM-as-a-Judge** `[⚡ Critical]` — *AI: model evaluation*
- [ ] **Context precision & recall** `[⚡ Critical]` — *AI: RAG evaluation*
- [ ] **MMLU benchmark** `[⚡ Critical]` — *AI: capability evaluation*
- [ ] **HumanEval benchmark** `[⚡ Critical]` — *AI: code evaluation*
- [ ] **Needle-in-a-Haystack testing** `[✅ Required]` — *AI: long context eval*
- [ ] **LLM tracing** `[⚡ Critical]` — *AI: debugging agents*
- [ ] **LangSmith** `[⚡ Critical]` — *AI: agent observability*
- [ ] **Phoenix (Arize)** `[✅ Required]` — *AI: LLM monitoring*

### 23.1 & 23.2 Capstone Engineering Portfolios
- [ ] **Robust server environments** `[✅ Required]`
- [ ] **Containerized environments (Docker)** `[⚡ Critical]`
- [ ] **Multi-node environments** `[⚡ Critical]` — *AI: distributed training*
- [ ] **Continuous model training pipelines** `[⚡ Critical]` — *Both: production ML*
- [ ] **Full-stack portfolio websites** `[✅ Required]`
- [ ] **3D portfolio websites (Three Fiber, Spline)** `[✅ Required]` — *AI: visual differentiation*
- [ ] **Backend data pipeline visualization** `[✅ Required]`
- [ ] **Financial sentiment analysis engine** `[◐ Secondary]` — *AI+Quant: bridge project*
- [ ] **Multi-agent orchestration (project)** `[⚡ Critical]` — *AI: showcase*

---

# Quant Track Checklist
### Track Placement: Jane Street · Goldman Sachs · JPMorgan · UBS · Swiss Re · Partners Group · more

**Legend:**
- `⚡` Critical — highest interview weight
- `✅` Required — core to this track
- `◐` Useful but secondary depth needed

## Phase 1 — The Bedrock

### 1.1 Programming Fundamentals
- [ ] **Variables, Data types, Operators** `[⚡ Critical]`
- [ ] **Control flow, Functions, Recursion** `[⚡ Critical]`
- [ ] **Type hinting** `[✅ Required]` — *Python best practice*
- [ ] **Input / Output, File handling** `[✅ Required]`
- [ ] **Regular expressions** `[◐ Secondary]` — *AI: NLP pipelines; Quant: log parsing*
- [ ] **Memory — Stack & Heap** `[⚡ Critical]` — *Quant: deeper for C++*
- [ ] **Garbage collection** `[◐ Secondary]` — *Python internals*
- [ ] **Reference counting** `[✅ Required]` — *C++ RAII overlap*
- [ ] **Global Interpreter Lock (GIL)** `[⚡ Critical]` — *Quant: concurrency bottleneck*

### 1.2 Advanced Programming & Low-Latency Systems
- [ ] **Object-Oriented Programming** `[⚡ Critical]`
- [ ] **Functional Programming** `[✅ Required]`
- [ ] **Iterators, Generators** `[✅ Required]` — *Data pipelines*
- [ ] **Decorators** `[◐ Secondary]` — *AI: MLOps; Quant: less critical*
- [ ] **Metaprogramming** `[◐ Secondary]` — *Advanced Python only*
- [ ] **Concurrency & Multithreading** `[⚡ Critical]` — *Quant: real-time systems*
- [ ] **Asynchronous I/O** `[✅ Required]` — *AI: APIs; Quant: feed handling*
- [ ] **C++ Smart Pointers** `[⚡ Critical]` — *Quant only — HFT/low-latency*
- [ ] **C++ Move Semantics** `[⚡ Critical]` — *Quant only*
- [ ] **RAII (Resource Acquisition Is Initialization)** `[⚡ Critical]` — *Quant only*
- [ ] **SIMD Vectorization** `[⚡ Critical]` — *Quant: HFT performance*
- [ ] **Cache-line alignment** `[⚡ Critical]` — *Quant: HFT performance*
- [ ] **False sharing prevention** `[✅ Required]` — *Quant: multi-core systems*
- [ ] **Ring buffers** `[⚡ Critical]` — *Quant: order book queues*
- [ ] **Lock-Free Architectures (LMAX Disruptor)** `[⚡ Critical]` — *Quant: ultra-low latency*
- [ ] **NUMA awareness** `[✅ Required]` — *Quant: server optimization*

### 2.1 Linear & Hash-Based Data Structures
- [ ] **Arrays, Linked lists** `[⚡ Critical]` — *Universal interview topic*
- [ ] **Stacks, Queues** `[⚡ Critical]`
- [ ] **Hash tables, Hash sets** `[⚡ Critical]`
- [ ] **Collision resolution strategies** `[✅ Required]` — *Systems interviews*
- [ ] **Bloom filters** `[◐ Secondary]` — *AI: streaming; Quant: dedup*

### 2.2 Tree & Graph Structures
- [ ] **Binary Search Trees** `[✅ Required]` — *AI: heavier LeetCode focus*
- [ ] **AVL trees** `[◐ Secondary]` — *AI: coding interviews*
- [ ] **Red-Black trees** `[◐ Secondary]` — *STL internals (Quant: C++)*
- [ ] **B-trees** `[◐ Secondary]` — *Database internals*
- [ ] **Heaps — Binary & Priority queues** `[⚡ Critical]` — *Universal — order books, Dijkstra*
- [ ] **Graphs (Directed, Undirected, Weighted)** `[✅ Required]`
- [ ] **Adjacency representations** `[✅ Required]`

### 3.1 Core Algorithm Design
- [ ] **Big-O Time & Space complexity** `[⚡ Critical]`
- [ ] **Binary search** `[⚡ Critical]`
- [ ] **Merge sort, Quick sort, Heap sort** `[✅ Required]` — *AI: more LeetCode weight*
- [ ] **Divide and conquer** `[✅ Required]` — *AI: interviews; Quant: algorithms*
- [ ] **Greedy approaches** `[◐ Secondary]` — *AI: heavy; Quant: lighter*
- [ ] **Backtracking** `[◐ Secondary]` — *AI: NeetCode patterns*

### 3.2 Graph & Dynamic Algorithms
- [ ] **BFS, DFS** `[✅ Required]`
- [ ] **Dijkstra's algorithm** `[✅ Required]`
- [ ] **A* algorithm** `[◐ Secondary]` — *AI: search; Quant: routing*
- [ ] **Topological sort** `[◐ Secondary]` — *AI: DAGs, pipelines*
- [ ] **Dynamic programming — Memoization** `[✅ Required]` — *AI: LeetCode critical*
- [ ] **Dynamic programming — Tabulation** `[✅ Required]` — *AI: LeetCode critical*

### 4.1 Linear Algebra & Multivariable Calculus
- [ ] **Vectors, Matrices, Tensors** `[⚡ Critical]` — *Universal math foundation*
- [ ] **Determinants** `[⚡ Critical]` — *Quant: hedging, covariance*
- [ ] **Eigenvalues & Eigenvectors** `[⚡ Critical]` — *Universal — PCA, risk*
- [ ] **SVD** `[⚡ Critical]` — *AI: dimensionality; Quant: risk*
- [ ] **Cholesky decomposition** `[⚡ Critical]` — *Quant: covariance matrices*
- [ ] **LU decomposition** `[⚡ Critical]` — *Quant: numerical finance*
- [ ] **QR decomposition** `[✅ Required]`
- [ ] **Derivatives, Gradients** `[⚡ Critical]` — *AI: backprop; Quant: Greeks*
- [ ] **Jacobians, Hessians** `[⚡ Critical]` — *AI: optimization; Quant: risk*
- [ ] **Convex optimization** `[⚡ Critical]` — *Quant: portfolio opt*
- [ ] **Non-convex optimization** `[✅ Required]` — *AI: training NNs*
- [ ] **Lagrange multipliers** `[⚡ Critical]` — *Quant: constrained portfolio opt*
- [ ] **KKT conditions** `[⚡ Critical]` — *Quant: portfolio constraints*

### 4.2 Probability, Statistics & Risk Math
- [ ] **Probability spaces, Random variables** `[⚡ Critical]`
- [ ] **Bayes' theorem** `[⚡ Critical]`
- [ ] **Normal distribution** `[⚡ Critical]`
- [ ] **Binomial distribution** `[⚡ Critical]` — *Quant: brainteasers*
- [ ] **Poisson distribution** `[⚡ Critical]` — *Quant: arrival processes*
- [ ] **Lognormal distribution** `[⚡ Critical]` — *Quant: asset prices*
- [ ] **Exponential distribution** `[⚡ Critical]` — *Quant: event timing*
- [ ] **Gamma distribution** `[✅ Required]` — *Bayesian inference*
- [ ] **Hypothesis testing & p-values** `[✅ Required]` — *AI: experimentation*
- [ ] **A/B testing** `[◐ Secondary]` — *AI: product; Quant: signal test*
- [ ] **Maximum Likelihood Estimation (MLE)** `[⚡ Critical]`
- [ ] **Central Limit Theorem (CLT)** `[⚡ Critical]`
- [ ] **Extreme Value Theory (EVT)** `[⚡ Critical]` — *Quant: tail risk, VaR*
- [ ] **Copula functions** `[⚡ Critical]` — *Quant: portfolio risk*

### 4.3 Stochastic Calculus & Econometrics
- [ ] **Markov chains** `[⚡ Critical]` — *AI: RL; Quant: pricing*
- [ ] **Random walks** `[⚡ Critical]` — *Quant: price modelling*
- [ ] **Brownian motion** `[⚡ Critical]` — *Quant: foundational*
- [ ] **Itô's Lemma** `[⚡ Critical]` — *Quant: derivation of BS*
- [ ] **Stochastic Differential Equations (SDEs)** `[⚡ Critical]` — *Quant: option pricing*
- [ ] **Girsanov theorem** `[⚡ Critical]` — *Quant: change of measure*
- [ ] **Time series stationarity** `[⚡ Critical]` — *Both: time series modelling*
- [ ] **Cointegration** `[⚡ Critical]` — *Quant: pairs trading*
- [ ] **ARIMA models** `[⚡ Critical]` — *Both: forecasting*
- [ ] **GARCH models** `[⚡ Critical]` — *Quant: volatility modelling*
- [ ] **Kalman filters** `[⚡ Critical]` — *Quant: signal filtering*
- [ ] **Particle filters** `[✅ Required]` — *Quant: nonlinear estimation*

---

## Phase 2 — Quantitative Finance & Markets

### 5.1 Exchange Mechanics & Dynamics
- [ ] **Market participants** `[⚡ Critical]` — *Quant: interview context*
- [ ] **Matching engines** `[⚡ Critical]` — *Quant: HFT, order execution*
- [ ] **Order types** `[⚡ Critical]` — *Quant: desk knowledge*
- [ ] **Limit Order Book (LOB) dynamics** `[⚡ Critical]` — *Quant: market making*
- [ ] **Bid-ask spread mechanics** `[⚡ Critical]` — *Jane Street core topic*
- [ ] **Order flow toxicity** `[⚡ Critical]` — *Quant: adverse selection*
- [ ] **Market impact modeling** `[⚡ Critical]` — *Quant: execution cost*
- [ ] **Hawkes processes** `[✅ Required]` — *Quant: event clustering*

### 5.2 Algorithmic Execution
- [ ] **VWAP** `[⚡ Critical]` — *Quant: execution benchmark*
- [ ] **TWAP** `[⚡ Critical]` — *Quant: execution benchmark*
- [ ] **Implementation Shortfall minimization** `[⚡ Critical]` — *Quant: optimal execution*
- [ ] **Almgren-Chriss optimal execution model** `[⚡ Critical]` — *Quant: execution theory*
- [ ] **Inventory risk management** `[⚡ Critical]` — *Quant: market making risk*

### 6.1 Fixed Income & Credit
- [ ] **Yield curve bootstrapping** `[⚡ Critical]` — *Quant: rates desks*
- [ ] **Duration, Convexity** `[⚡ Critical]` — *Quant: bond risk*
- [ ] **Vasicek model** `[⚡ Critical]` — *Quant: short-rate*
- [ ] **Hull-White model** `[⚡ Critical]` — *Quant: interest rate products*
- [ ] **Credit Risk — Merton model** `[⚡ Critical]` — *Quant: credit desks*
- [ ] **Credit Default Swaps (CDS)** `[⚡ Critical]` — *Quant: credit derivatives*

### 6.2 Derivatives & Advanced Volatility
- [ ] **Vanilla options pricing** `[⚡ Critical]` — *Quant: foundational*
- [ ] **Exotic options pricing** `[⚡ Critical]` — *Quant: structuring desks*
- [ ] **Black-Scholes-Merton paradigm** `[⚡ Critical]` — *Quant: must derive*
- [ ] **Delta, Gamma, Theta, Vega** `[⚡ Critical]` — *Quant: desk interview staple*
- [ ] **Implied volatility surfaces** `[⚡ Critical]` — *Quant: vol trading*
- [ ] **Implied volatility smiles** `[⚡ Critical]` — *Quant: market insight*
- [ ] **Local Volatility — Dupire model** `[⚡ Critical]` — *Quant: vol modelling*
- [ ] **Stochastic Volatility — Heston model** `[⚡ Critical]` — *Quant: advanced vol*
- [ ] **Stochastic Volatility — SABR model** `[⚡ Critical]` — *Quant: rates/FX*
- [ ] **Fractional calculus** `[✅ Required]` — *Quant: rough vol*
- [ ] **Rough Volatility modeling** `[✅ Required]` — *Quant: cutting-edge*
- [ ] **CVA, DVA, FVA (XVA)** `[⚡ Critical]` — *Quant: bank desks*

### 7.1 Portfolio Theory
- [ ] **Markowitz mean-variance optimization** `[⚡ Critical]` — *Quant: foundational*
- [ ] **Capital Asset Pricing Model (CAPM)** `[⚡ Critical]` — *Quant: equity*
- [ ] **Efficient frontier** `[⚡ Critical]` — *Quant: portfolio opt*
- [ ] **Fama-French factor models** `[⚡ Critical]` — *Quant: equity alpha*
- [ ] **Arbitrage Pricing Theory (APT)** `[⚡ Critical]` — *Quant: multi-factor*
- [ ] **Black-Litterman model** `[⚡ Critical]` — *Quant: active management*
- [ ] **Hierarchical Risk Parity (HRP)** `[✅ Required]` — *AI+Quant: ML-based portfolio*

### 7.2 Alpha Research & Risk Infrastructure
- [ ] **Parametric VaR** `[⚡ Critical]` — *Quant: risk management*
- [ ] **Historical VaR** `[⚡ Critical]` — *Quant: risk management*
- [ ] **Monte Carlo VaR** `[⚡ Critical]` — *Both: simulation*
- [ ] **Expected Shortfall (CVaR)** `[⚡ Critical]` — *Quant: tail risk*
- [ ] **Satellite imagery (alt data)** `[◐ Secondary]` — *AI+Quant: alternative data*
- [ ] **SEC filings NLP** `[◐ Secondary]` — *AI+Quant: NLP on filings*
- [ ] **Web scraping pipelines** `[◐ Secondary]` — *AI+Quant: data collection*
- [ ] **Signal decay analysis** `[⚡ Critical]` — *Quant: alpha research*
- [ ] **Alpha capacity constraints** `[⚡ Critical]` — *Quant: strategy scaling*

---

## Phase 3 — Core Machine Learning

### 8.1 Learning Paradigms & Data Preparation
- [ ] **Supervised learning** `[⚡ Critical]`
- [ ] **Unsupervised learning** `[✅ Required]`
- [ ] **Reinforcement learning (concept)** `[✅ Required]` — *AI: deep; Quant: trading strategies*
- [ ] **Imputation** `[⚡ Critical]` — *Both: missing data*
- [ ] **Outlier detection** `[⚡ Critical]` — *Both: data quality*
- [ ] **Feature scaling** `[✅ Required]`
- [ ] **Categorical encoding** `[✅ Required]`
- [ ] **Fractional differentiation** `[⚡ Critical]` — *Quant: financial stationarity*
- [ ] **Return stationarity conversions** `[⚡ Critical]` — *Quant: financial ML*

### 8.2 Evaluation & Validation
- [ ] **Accuracy, Precision, Recall, F1** `[✅ Required]` — *AI: interview staple*
- [ ] **ROC curve & AUC** `[✅ Required]` — *AI: classification*
- [ ] **Confusion matrix** `[✅ Required]`
- [ ] **K-fold cross-validation** `[✅ Required]`
- [ ] **Purged cross-validation** `[⚡ Critical]` — *Quant: financial ML anti-leakage*
- [ ] **Embargoed cross-validation** `[⚡ Critical]` — *Quant: financial ML anti-leakage*
- [ ] **Grid search** `[✅ Required]`
- [ ] **Random search** `[✅ Required]`
- [ ] **Bayesian optimization** `[✅ Required]`

### 9.1 Supervised Learning
- [ ] **Ridge regression (L2)** `[⚡ Critical]`
- [ ] **Lasso regression (L1)** `[⚡ Critical]` — *Universal — feature selection*
- [ ] **ElasticNet** `[✅ Required]`
- [ ] **Support Vector Machines (SVM)** `[◐ Secondary]` — *AI: interviews; Quant: less used*
- [ ] **K-Nearest Neighbors (KNN)** `[◐ Secondary]` — *AI: interviews*
- [ ] **Random forests** `[⚡ Critical]`
- [ ] **XGBoost** `[⚡ Critical]` — *Universal — industry standard*
- [ ] **LightGBM** `[⚡ Critical]` — *Universal — faster XGBoost*
- [ ] **CatBoost** `[✅ Required]`

### 9.2 Unsupervised Learning & Dimensionality Reduction
- [ ] **K-means clustering** `[✅ Required]`
- [ ] **Hierarchical clustering** `[✅ Required]` — *Quant: HRP hierarchy*
- [ ] **DBSCAN** `[◐ Secondary]` — *AI: anomaly detection*
- [ ] **HDBSCAN** `[◐ Secondary]` — *AI: density clustering*
- [ ] **PCA** `[⚡ Critical]` — *Universal — risk factors, features*
- [ ] **t-SNE** `[◐ Secondary]` — *AI: visualization*
- [ ] **UMAP** `[◐ Secondary]` — *AI: embedding visualization*

---

## Phase 4 — Deep Learning & NLP

### 10.1 Network Mechanics
- [ ] **Feedforward networks** `[✅ Required]` — *Universal DL foundation*
- [ ] **Backpropagation** `[◐ Secondary]` — *AI: must derive; Quant: awareness*
- [ ] **Gradient descent variants** `[◐ Secondary]` — *AI: training; Quant: optimization*
- [ ] **Adam, AdamW optimizers** `[◐ Secondary]` — *AI: standard training*
- [ ] **Activation functions** `[◐ Secondary]` — *AI: architecture design*
- [ ] **Dropout regularization** `[◐ Secondary]` — *AI: overfitting prevention*
- [ ] **BatchNorm, LayerNorm** `[◐ Secondary]` — *AI: training stability*

### 10.2 Advanced Neural Topologies
- [ ] **RNNs (vanilla)** `[✅ Required]` — *Both: sequence modelling*
- [ ] **LSTMs** `[⚡ Critical]` — *Both: time series*
- [ ] **GRUs** `[✅ Required]` — *Both: faster LSTM*
- [ ] **Autoencoders** `[◐ Secondary]` — *AI: anomaly detection*
- [ ] **Temporal Fusion Transformers (TFT)** `[⚡ Critical]` — *Both: financial forecasting*
- [ ] **N-BEATS** `[⚡ Critical]` — *Both: time series*
- [ ] **Graph Neural Networks (GNNs)** `[◐ Secondary]` — *AI+Quant: financial networks*

### 11.1 Text Representation
- [ ] **Bag of Words (BoW), TF-IDF** `[◐ Secondary]` — *AI: classic NLP; Quant: alt data*
- [ ] **Named Entity Recognition (NER)** `[◐ Secondary]` — *AI: information extraction*
- [ ] **Sentiment analysis** `[⚡ Critical]` — *Quant: news/earnings signals*
- [ ] **Word2Vec, GloVe, FastText** `[◐ Secondary]` — *AI: embeddings*
- [ ] **Sentence embeddings** `[◐ Secondary]` — *AI: RAG; Quant: semantic search*

### 11.2 Domain-Specific & Sequence NLP
- [ ] **Financial NLP — Loughran-McDonald** `[⚡ Critical]` — *Quant: earnings call analysis*
- [ ] **FinBERT** `[⚡ Critical]` — *Quant: sentiment scoring*
- [ ] **Transformer — Attention mechanisms** `[✅ Required]`
- [ ] **Transformer — Encoder-decoder architecture** `[✅ Required]`

---

## Phase 5 — The Builder's Toolkit & Infrastructure

### 12.1 Relational & Distributed Storage
- [ ] **SQL joins (all types)** `[⚡ Critical]`
- [ ] **SQL indexing & query optimization** `[⚡ Critical]`
- [ ] **ACID properties** `[✅ Required]` — *AI: system design*
- [ ] **PostgreSQL** `[⚡ Critical]`
- [ ] **MongoDB (NoSQL document)** `[◐ Secondary]` — *AI: unstructured data*
- [ ] **Redis (NoSQL key-value)** `[◐ Secondary]` — *AI: caching; Quant: tick cache*
- [ ] **Parquet, Apache Arrow** `[⚡ Critical]` — *Both: efficient data storage*
- [ ] **Data warehouses (BigQuery, Snowflake)** `[✅ Required]` — *AI: primary; Quant: analytics*

### 13.1 System Architecture
- [ ] **Fault tolerance** `[✅ Required]` — *AI: system design rounds*
- [ ] **Load balancing** `[◐ Secondary]` — *AI: system design rounds*
- [ ] **CAP theorem** `[◐ Secondary]` — *AI: system design rounds*
- [ ] **Consensus protocols (Raft, Paxos)** `[◐ Secondary]` — *AI: distributed systems*
- [ ] **Apache Kafka** `[⚡ Critical]` — *Both: real-time data streaming*
- [ ] **RabbitMQ** `[◐ Secondary]` — *AI: message queues*
- [ ] **ETL / ELT pipelines** `[⚡ Critical]`
- [ ] **Apache Spark** `[✅ Required]` — *Both: large-scale data*

### 13.2 Ultra-Low Latency Engineering
- [ ] **Kernel bypass networking (DPDK)** `[⚡ Critical]` — *Quant: HFT infrastructure*
- [ ] **Solarflare OpenOnload** `[⚡ Critical]` — *Quant: HFT NIC bypass*
- [ ] **FPGA acceleration concepts** `[✅ Required]` — *Quant: co-location*
- [ ] **Hardware acceleration** `[✅ Required]` — *AI: GPU; Quant: FPGA/ASIC*
- [ ] **FIX protocol socket streams** `[⚡ Critical]` — *Quant: exchange connectivity*

### 14.1 CI/CD & Development Workflows
- [ ] **Git workflows** `[⚡ Critical]`
- [ ] **Unit testing** `[⚡ Critical]`
- [ ] **Integration testing** `[✅ Required]`
- [ ] **End-to-end testing** `[◐ Secondary]` — *AI: ML pipelines*
- [ ] **CI pipelines (GitHub Actions)** `[✅ Required]` — *AI: MLOps*
- [ ] **CD pipelines** `[✅ Required]` — *AI: production deployment*
- [ ] **Code linting** `[✅ Required]`
- [ ] **Microservices architectures** `[◐ Secondary]` — *AI: system design*
- [ ] **Event-driven architectures** `[✅ Required]` — *AI: async; Quant: market events*

### 14.2 MLOps & Production Monitoring
- [ ] **MLflow** `[◐ Secondary]` — *AI: experiment tracking*
- [ ] **Weights & Biases** `[◐ Secondary]` — *AI: experiment tracking*
- [ ] **Continuous training pipelines** `[✅ Required]` — *AI: production ML*
- [ ] **Data drift monitoring** `[✅ Required]` — *AI: production health*
- [ ] **Concept drift monitoring** `[✅ Required]` — *AI: production health*
- [ ] **FastAPI** `[◐ Secondary]` — *AI: model serving*
- [ ] **Flask** `[◐ Secondary]` — *AI: rapid prototyping*
- [ ] **gRPC** `[✅ Required]` — *AI: high-performance APIs*
- [ ] **API gateways** `[◐ Secondary]` — *AI: microservices*
- [ ] **OAuth, JWT, RBAC** `[◐ Secondary]` — *AI: security layer*

### 15.1 Cloud & Containerization
- [ ] **Linux server management** `[⚡ Critical]`
- [ ] **Docker engines** `[✅ Required]`
- [ ] **Docker Compose** `[✅ Required]`
- [ ] **Kubernetes pod orchestration** `[◐ Secondary]` — *AI: model serving at scale*
- [ ] **Multi-node scaling** `[◐ Secondary]` — *AI: distributed training*
- [ ] **AWS / GCP / Azure** `[✅ Required]` — *AI: primary; Quant: storage/compute*
- [ ] **ARM-based instances** `[◐ Secondary]` — *AI: cost optimization*
- [ ] **Terraform (IaC)** `[◐ Secondary]` — *AI: MLOps infra*
- [ ] **CUDA GPU provisioning** `[◐ Secondary]` — *AI: model training*

---

## Phase 6 — Generative AI

### 16.1 LLM Architecture & Mechanics
- [ ] **Tokens & context windows** `[◐ Secondary]` — *AI: LLM fundamentals*
- [ ] **Small Language Models (SLMs)** `[◐ Secondary]` — *AI: on-device deployment*

### 16.2 Alignment & Customization
- [ ] **Fine-tuning** `[◐ Secondary]` — *AI: customization; Quant: FinBERT*

### 17.1 RAG — Core Systems & Retrieval
- [ ] **Semantic search** `[◐ Secondary]` — *AI: RAG; Quant: document search*
- [ ] **Hybrid search** `[◐ Secondary]` — *AI: retrieval accuracy*
- [ ] **Vector embeddings** `[◐ Secondary]` — *Universal for LLM apps*
- [ ] **Indexing** `[◐ Secondary]` — *AI: search performance*

### 17.2 Advanced RAG Methodologies
- [ ] **Knowledge graphs** `[◐ Secondary]` — *AI: structured retrieval; Quant: financial graphs*
- [ ] **Document parsing** `[◐ Secondary]` — *Both: alternative data*

### 18.1 Prompt Engineering & Reasoning
- [ ] **Chain-of-Thought (CoT) prompting** `[◐ Secondary]` — *AI: reasoning tasks*

---

## Phase 7 — Agents & Reinforcement Learning

### 19.1 RL Fundamentals & Value-Based Methods
- [ ] **Markov Decision Processes (MDPs)** `[⚡ Critical]` — *AI: RL; Quant: trading strategy*
- [ ] **Bellman equations** `[⚡ Critical]` — *Universal RL foundation*
- [ ] **Q-Learning** `[✅ Required]`
- [ ] **Deep Q-Networks (DQN)** `[✅ Required]`

### 19.2 Advanced RL Frameworks
- [ ] **Policy gradients (REINFORCE)** `[◐ Secondary]` — *AI: primary; Quant: strategy research*
- [ ] **Proximal Policy Optimization (PPO)** `[◐ Secondary]` — *AI: RLHF; Quant: strategy*
- [ ] **Soft Actor-Critic (SAC)** `[◐ Secondary]` — *AI: continuous control*
- [ ] **Multi-Agent RL (MARL)** `[◐ Secondary]` — *AI: multi-agent; Quant: market sim*

### 20.1 Agent Architecture
- [ ] **Human-in-the-loop workflows** `[◐ Secondary]` — *AI: production safety*

### 20.2 Frameworks & Routing Logic
- [ ] **Apache Airflow** `[✅ Required]` — *Both: pipeline orchestration*

---

## Phase 8 — Production Safety, Evaluation & Portfolios

### 22.1 AI Safety & Guardrails
- [ ] **Data exfiltration defenses** `[✅ Required]` — *Both: compliance*
- [ ] **PII masking** `[⚡ Critical]` — *Both: regulatory compliance*

### 22.2 Evaluation Metrics
- [ ] **HumanEval benchmark** `[◐ Secondary]` — *AI: code evaluation*

### 23.1 & 23.2 Capstone Engineering Portfolios
- [ ] **Robust server environments** `[✅ Required]`
- [ ] **Containerized environments (Docker)** `[✅ Required]`
- [ ] **Multi-node environments** `[◐ Secondary]` — *AI: distributed training*
- [ ] **Continuous model training pipelines** `[✅ Required]` — *Both: production ML*
- [ ] **Full-stack portfolio websites** `[✅ Required]`
- [ ] **Backend data pipeline visualization** `[✅ Required]`
- [ ] **Financial sentiment analysis engine** `[✅ Required]` — *AI+Quant: bridge project*
- [ ] **Statistical arbitrage backtesting pipeline** `[⚡ Critical]` — *Quant+AI: hiring signal*
- [ ] **Purged cross-validation implementation** `[⚡ Critical]` — *Quant: anti-leakage*

---

# AI + Quant (Hybrid) Track Checklist
### Track Placement: Squarepoint Capital · Systematica Investments · more

**Legend:**
- `⚡` Critical — highest interview weight
- `✅` Required — core to this track
- `◐` Useful but secondary depth needed

## Phase 1 — The Bedrock

### 1.1 Programming Fundamentals
- [ ] **Variables, Data types, Operators** `[⚡ Critical]`
- [ ] **Control flow, Functions, Recursion** `[⚡ Critical]`
- [ ] **Type hinting** `[✅ Required]` — *Python best practice*
- [ ] **Input / Output, File handling** `[✅ Required]`
- [ ] **Regular expressions** `[✅ Required]` — *AI: NLP pipelines; Quant: log parsing*
- [ ] **Memory — Stack & Heap** `[⚡ Critical]` — *Quant: deeper for C++*
- [ ] **Garbage collection** `[✅ Required]` — *Python internals*
- [ ] **Reference counting** `[✅ Required]` — *C++ RAII overlap*
- [ ] **Global Interpreter Lock (GIL)** `[⚡ Critical]` — *Quant: concurrency bottleneck*

### 1.2 Advanced Programming & Low-Latency Systems
- [ ] **Object-Oriented Programming** `[⚡ Critical]`
- [ ] **Functional Programming** `[✅ Required]`
- [ ] **Iterators, Generators** `[✅ Required]` — *Data pipelines*
- [ ] **Decorators** `[✅ Required]` — *AI: MLOps; Quant: less critical*
- [ ] **Metaprogramming** `[✅ Required]` — *Advanced Python only*
- [ ] **Concurrency & Multithreading** `[⚡ Critical]` — *Quant: real-time systems*
- [ ] **Asynchronous I/O** `[✅ Required]` — *AI: APIs; Quant: feed handling*
- [ ] **C++ Smart Pointers** `[⚡ Critical]` — *Quant only — HFT/low-latency*
- [ ] **C++ Move Semantics** `[⚡ Critical]` — *Quant only*
- [ ] **RAII (Resource Acquisition Is Initialization)** `[⚡ Critical]` — *Quant only*
- [ ] **SIMD Vectorization** `[✅ Required]` — *Quant: HFT performance*
- [ ] **Cache-line alignment** `[✅ Required]` — *Quant: HFT performance*
- [ ] **False sharing prevention** `[✅ Required]` — *Quant: multi-core systems*
- [ ] **Ring buffers** `[✅ Required]` — *Quant: order book queues*
- [ ] **Lock-Free Architectures (LMAX Disruptor)** `[✅ Required]` — *Quant: ultra-low latency*
- [ ] **NUMA awareness** `[✅ Required]` — *Quant: server optimization*

### 2.1 Linear & Hash-Based Data Structures
- [ ] **Arrays, Linked lists** `[⚡ Critical]` — *Universal interview topic*
- [ ] **Stacks, Queues** `[⚡ Critical]`
- [ ] **Hash tables, Hash sets** `[⚡ Critical]`
- [ ] **Collision resolution strategies** `[✅ Required]` — *Systems interviews*
- [ ] **Bloom filters** `[✅ Required]` — *AI: streaming; Quant: dedup*
- [ ] **Count-Min Sketch** `[◐ Secondary]` — *AI: frequency estimation*

### 2.2 Tree & Graph Structures
- [ ] **Binary Search Trees** `[⚡ Critical]` — *AI: heavier LeetCode focus*
- [ ] **AVL trees** `[✅ Required]` — *AI: coding interviews*
- [ ] **Red-Black trees** `[✅ Required]` — *STL internals (Quant: C++)*
- [ ] **B-trees** `[✅ Required]` — *Database internals*
- [ ] **Heaps — Binary & Priority queues** `[⚡ Critical]` — *Universal — order books, Dijkstra*
- [ ] **Tries** `[◐ Secondary]` — *AI: NLP/autocomplete interviews*
- [ ] **Graphs (Directed, Undirected, Weighted)** `[⚡ Critical]`
- [ ] **Adjacency representations** `[⚡ Critical]`

### 3.1 Core Algorithm Design
- [ ] **Big-O Time & Space complexity** `[⚡ Critical]`
- [ ] **Binary search** `[⚡ Critical]`
- [ ] **Merge sort, Quick sort, Heap sort** `[⚡ Critical]` — *AI: more LeetCode weight*
- [ ] **Divide and conquer** `[⚡ Critical]` — *AI: interviews; Quant: algorithms*
- [ ] **Greedy approaches** `[✅ Required]` — *AI: heavy; Quant: lighter*
- [ ] **Backtracking** `[✅ Required]` — *AI: NeetCode patterns*

### 3.2 Graph & Dynamic Algorithms
- [ ] **BFS, DFS** `[⚡ Critical]`
- [ ] **Dijkstra's algorithm** `[⚡ Critical]`
- [ ] **A* algorithm** `[✅ Required]` — *AI: search; Quant: routing*
- [ ] **Topological sort** `[✅ Required]` — *AI: DAGs, pipelines*
- [ ] **Dynamic programming — Memoization** `[⚡ Critical]` — *AI: LeetCode critical*
- [ ] **Dynamic programming — Tabulation** `[⚡ Critical]` — *AI: LeetCode critical*
- [ ] **String matching — KMP** `[◐ Secondary]` — *AI: NLP/coding interviews*
- [ ] **String matching — Rabin-Karp** `[◐ Secondary]` — *AI: rolling hash pattern*

### 4.1 Linear Algebra & Multivariable Calculus
- [ ] **Vectors, Matrices, Tensors** `[⚡ Critical]` — *Universal math foundation*
- [ ] **Determinants** `[⚡ Critical]` — *Quant: hedging, covariance*
- [ ] **Eigenvalues & Eigenvectors** `[⚡ Critical]` — *Universal — PCA, risk*
- [ ] **SVD** `[⚡ Critical]` — *AI: dimensionality; Quant: risk*
- [ ] **Cholesky decomposition** `[⚡ Critical]` — *Quant: covariance matrices*
- [ ] **LU decomposition** `[⚡ Critical]` — *Quant: numerical finance*
- [ ] **QR decomposition** `[✅ Required]`
- [ ] **Derivatives, Gradients** `[⚡ Critical]` — *AI: backprop; Quant: Greeks*
- [ ] **Jacobians, Hessians** `[⚡ Critical]` — *AI: optimization; Quant: risk*
- [ ] **Convex optimization** `[⚡ Critical]` — *Quant: portfolio opt*
- [ ] **Non-convex optimization** `[✅ Required]` — *AI: training NNs*
- [ ] **Lagrange multipliers** `[⚡ Critical]` — *Quant: constrained portfolio opt*
- [ ] **KKT conditions** `[⚡ Critical]` — *Quant: portfolio constraints*

### 4.2 Probability, Statistics & Risk Math
- [ ] **Probability spaces, Random variables** `[⚡ Critical]`
- [ ] **Bayes' theorem** `[⚡ Critical]`
- [ ] **Normal distribution** `[⚡ Critical]`
- [ ] **Binomial distribution** `[⚡ Critical]` — *Quant: brainteasers*
- [ ] **Poisson distribution** `[⚡ Critical]` — *Quant: arrival processes*
- [ ] **Lognormal distribution** `[⚡ Critical]` — *Quant: asset prices*
- [ ] **Exponential distribution** `[⚡ Critical]` — *Quant: event timing*
- [ ] **Gamma distribution** `[✅ Required]` — *Bayesian inference*
- [ ] **Hypothesis testing & p-values** `[⚡ Critical]` — *AI: experimentation*
- [ ] **A/B testing** `[✅ Required]` — *AI: product; Quant: signal test*
- [ ] **Maximum Likelihood Estimation (MLE)** `[⚡ Critical]`
- [ ] **Central Limit Theorem (CLT)** `[⚡ Critical]`
- [ ] **Extreme Value Theory (EVT)** `[✅ Required]` — *Quant: tail risk, VaR*
- [ ] **Copula functions** `[✅ Required]` — *Quant: portfolio risk*

### 4.3 Stochastic Calculus & Econometrics
- [ ] **Markov chains** `[⚡ Critical]` — *AI: RL; Quant: pricing*
- [ ] **Random walks** `[⚡ Critical]` — *Quant: price modelling*
- [ ] **Brownian motion** `[⚡ Critical]` — *Quant: foundational*
- [ ] **Itô's Lemma** `[⚡ Critical]` — *Quant: derivation of BS*
- [ ] **Stochastic Differential Equations (SDEs)** `[⚡ Critical]` — *Quant: option pricing*
- [ ] **Girsanov theorem** `[✅ Required]` — *Quant: change of measure*
- [ ] **Time series stationarity** `[⚡ Critical]` — *Both: time series modelling*
- [ ] **Cointegration** `[⚡ Critical]` — *Quant: pairs trading*
- [ ] **ARIMA models** `[⚡ Critical]` — *Both: forecasting*
- [ ] **GARCH models** `[⚡ Critical]` — *Quant: volatility modelling*
- [ ] **Kalman filters** `[⚡ Critical]` — *Quant: signal filtering*
- [ ] **Particle filters** `[✅ Required]` — *Quant: nonlinear estimation*

---

## Phase 2 — Quantitative Finance & Markets

### 5.1 Exchange Mechanics & Dynamics
- [ ] **Market participants** `[✅ Required]` — *Quant: interview context*
- [ ] **Matching engines** `[✅ Required]` — *Quant: HFT, order execution*
- [ ] **Order types** `[✅ Required]` — *Quant: desk knowledge*
- [ ] **Limit Order Book (LOB) dynamics** `[⚡ Critical]` — *Quant: market making*
- [ ] **Bid-ask spread mechanics** `[⚡ Critical]` — *Jane Street core topic*
- [ ] **Order flow toxicity** `[✅ Required]` — *Quant: adverse selection*
- [ ] **Market impact modeling** `[⚡ Critical]` — *Quant: execution cost*
- [ ] **Hawkes processes** `[✅ Required]` — *Quant: event clustering*

### 5.2 Algorithmic Execution
- [ ] **VWAP** `[✅ Required]` — *Quant: execution benchmark*
- [ ] **TWAP** `[✅ Required]` — *Quant: execution benchmark*
- [ ] **Implementation Shortfall minimization** `[✅ Required]` — *Quant: optimal execution*
- [ ] **Almgren-Chriss optimal execution model** `[⚡ Critical]` — *Quant: execution theory*
- [ ] **Inventory risk management** `[⚡ Critical]` — *Quant: market making risk*

### 6.1 Fixed Income & Credit
- [ ] **Yield curve bootstrapping** `[✅ Required]` — *Quant: rates desks*
- [ ] **Duration, Convexity** `[✅ Required]` — *Quant: bond risk*
- [ ] **Vasicek model** `[✅ Required]` — *Quant: short-rate*
- [ ] **Hull-White model** `[✅ Required]` — *Quant: interest rate products*
- [ ] **Credit Risk — Merton model** `[✅ Required]` — *Quant: credit desks*
- [ ] **Credit Default Swaps (CDS)** `[✅ Required]` — *Quant: credit derivatives*

### 6.2 Derivatives & Advanced Volatility
- [ ] **Vanilla options pricing** `[⚡ Critical]` — *Quant: foundational*
- [ ] **Exotic options pricing** `[✅ Required]` — *Quant: structuring desks*
- [ ] **Black-Scholes-Merton paradigm** `[⚡ Critical]` — *Quant: must derive*
- [ ] **Delta, Gamma, Theta, Vega** `[⚡ Critical]` — *Quant: desk interview staple*
- [ ] **Implied volatility surfaces** `[⚡ Critical]` — *Quant: vol trading*
- [ ] **Implied volatility smiles** `[⚡ Critical]` — *Quant: market insight*
- [ ] **Local Volatility — Dupire model** `[✅ Required]` — *Quant: vol modelling*
- [ ] **Stochastic Volatility — Heston model** `[⚡ Critical]` — *Quant: advanced vol*
- [ ] **Stochastic Volatility — SABR model** `[✅ Required]` — *Quant: rates/FX*
- [ ] **Fractional calculus** `[✅ Required]` — *Quant: rough vol*
- [ ] **Rough Volatility modeling** `[✅ Required]` — *Quant: cutting-edge*
- [ ] **CVA, DVA, FVA (XVA)** `[✅ Required]` — *Quant: bank desks*

### 7.1 Portfolio Theory
- [ ] **Markowitz mean-variance optimization** `[⚡ Critical]` — *Quant: foundational*
- [ ] **Capital Asset Pricing Model (CAPM)** `[⚡ Critical]` — *Quant: equity*
- [ ] **Efficient frontier** `[⚡ Critical]` — *Quant: portfolio opt*
- [ ] **Fama-French factor models** `[⚡ Critical]` — *Quant: equity alpha*
- [ ] **Arbitrage Pricing Theory (APT)** `[✅ Required]` — *Quant: multi-factor*
- [ ] **Black-Litterman model** `[✅ Required]` — *Quant: active management*
- [ ] **Hierarchical Risk Parity (HRP)** `[⚡ Critical]` — *AI+Quant: ML-based portfolio*

### 7.2 Alpha Research & Risk Infrastructure
- [ ] **Parametric VaR** `[✅ Required]` — *Quant: risk management*
- [ ] **Historical VaR** `[✅ Required]` — *Quant: risk management*
- [ ] **Monte Carlo VaR** `[⚡ Critical]` — *Both: simulation*
- [ ] **Expected Shortfall (CVaR)** `[✅ Required]` — *Quant: tail risk*
- [ ] **Satellite imagery (alt data)** `[⚡ Critical]` — *AI+Quant: alternative data*
- [ ] **SEC filings NLP** `[⚡ Critical]` — *AI+Quant: NLP on filings*
- [ ] **Web scraping pipelines** `[⚡ Critical]` — *AI+Quant: data collection*
- [ ] **Signal decay analysis** `[⚡ Critical]` — *Quant: alpha research*
- [ ] **Alpha capacity constraints** `[⚡ Critical]` — *Quant: strategy scaling*

---

## Phase 3 — Core Machine Learning

### 8.1 Learning Paradigms & Data Preparation
- [ ] **Supervised learning** `[⚡ Critical]`
- [ ] **Unsupervised learning** `[⚡ Critical]`
- [ ] **Reinforcement learning (concept)** `[⚡ Critical]` — *AI: deep; Quant: trading strategies*
- [ ] **Active learning** `[◐ Secondary]` — *AI: labelling workflows*
- [ ] **Semi-supervised learning** `[◐ Secondary]` — *AI: limited labels*
- [ ] **Self-supervised learning** `[◐ Secondary]` — *AI: foundation model training*
- [ ] **Imputation** `[⚡ Critical]` — *Both: missing data*
- [ ] **Outlier detection** `[⚡ Critical]` — *Both: data quality*
- [ ] **Feature scaling** `[⚡ Critical]`
- [ ] **Categorical encoding** `[⚡ Critical]`
- [ ] **Fractional differentiation** `[⚡ Critical]` — *Quant: financial stationarity*
- [ ] **Return stationarity conversions** `[⚡ Critical]` — *Quant: financial ML*

### 8.2 Evaluation & Validation
- [ ] **Accuracy, Precision, Recall, F1** `[⚡ Critical]` — *AI: interview staple*
- [ ] **ROC curve & AUC** `[⚡ Critical]` — *AI: classification*
- [ ] **Confusion matrix** `[⚡ Critical]`
- [ ] **K-fold cross-validation** `[⚡ Critical]`
- [ ] **Purged cross-validation** `[⚡ Critical]` — *Quant: financial ML anti-leakage*
- [ ] **Embargoed cross-validation** `[⚡ Critical]` — *Quant: financial ML anti-leakage*
- [ ] **Grid search** `[⚡ Critical]`
- [ ] **Random search** `[⚡ Critical]`
- [ ] **Bayesian optimization** `[⚡ Critical]`

### 9.1 Supervised Learning
- [ ] **Ridge regression (L2)** `[⚡ Critical]`
- [ ] **Lasso regression (L1)** `[⚡ Critical]` — *Universal — feature selection*
- [ ] **ElasticNet** `[✅ Required]`
- [ ] **Support Vector Machines (SVM)** `[✅ Required]` — *AI: interviews; Quant: less used*
- [ ] **K-Nearest Neighbors (KNN)** `[✅ Required]` — *AI: interviews*
- [ ] **Naive Bayes** `[◐ Secondary]` — *AI: NLP classification*
- [ ] **Random forests** `[⚡ Critical]`
- [ ] **XGBoost** `[⚡ Critical]` — *Universal — industry standard*
- [ ] **LightGBM** `[⚡ Critical]` — *Universal — faster XGBoost*
- [ ] **CatBoost** `[✅ Required]`

### 9.2 Unsupervised Learning & Dimensionality Reduction
- [ ] **K-means clustering** `[⚡ Critical]`
- [ ] **Hierarchical clustering** `[✅ Required]` — *Quant: HRP hierarchy*
- [ ] **DBSCAN** `[✅ Required]` — *AI: anomaly detection*
- [ ] **HDBSCAN** `[✅ Required]` — *AI: density clustering*
- [ ] **PCA** `[⚡ Critical]` — *Universal — risk factors, features*
- [ ] **t-SNE** `[✅ Required]` — *AI: visualization*
- [ ] **UMAP** `[✅ Required]` — *AI: embedding visualization*

---

## Phase 4 — Deep Learning & NLP

### 10.1 Network Mechanics
- [ ] **Feedforward networks** `[⚡ Critical]` — *Universal DL foundation*
- [ ] **Backpropagation** `[⚡ Critical]` — *AI: must derive; Quant: awareness*
- [ ] **Gradient descent variants** `[⚡ Critical]` — *AI: training; Quant: optimization*
- [ ] **Adam, AdamW optimizers** `[⚡ Critical]` — *AI: standard training*
- [ ] **Learning rate schedulers** `[✅ Required]` — *AI: training*
- [ ] **Activation functions** `[⚡ Critical]` — *AI: architecture design*
- [ ] **Dropout regularization** `[✅ Required]` — *AI: overfitting prevention*
- [ ] **BatchNorm, LayerNorm** `[✅ Required]` — *AI: training stability*

### 10.2 Advanced Neural Topologies
- [ ] **Convolutional Neural Networks (CNNs)** `[◐ Secondary]` — *AI: vision, pattern recognition*
- [ ] **RNNs (vanilla)** `[⚡ Critical]` — *Both: sequence modelling*
- [ ] **LSTMs** `[⚡ Critical]` — *Both: time series*
- [ ] **GRUs** `[⚡ Critical]` — *Both: faster LSTM*
- [ ] **Autoencoders** `[✅ Required]` — *AI: anomaly detection*
- [ ] **Variational Autoencoders (VAEs)** `[◐ Secondary]` — *AI: generative modelling*
- [ ] **Generative Adversarial Networks (GANs)** `[◐ Secondary]` — *AI: generative; Quant: scenario gen*
- [ ] **Diffusion models** `[◐ Secondary]` — *AI: NVIDIA, Google roles*
- [ ] **Temporal Fusion Transformers (TFT)** `[⚡ Critical]` — *Both: financial forecasting*
- [ ] **N-BEATS** `[⚡ Critical]` — *Both: time series*
- [ ] **Graph Neural Networks (GNNs)** `[⚡ Critical]` — *AI+Quant: financial networks*

### 11.1 Text Representation
- [ ] **Tokenization** `[✅ Required]` — *AI: NLP foundation*
- [ ] **Stemming, Lemmatization** `[◐ Secondary]` — *AI: NLP preprocessing*
- [ ] **Bag of Words (BoW), TF-IDF** `[✅ Required]` — *AI: classic NLP; Quant: alt data*
- [ ] **Named Entity Recognition (NER)** `[✅ Required]` — *AI: information extraction*
- [ ] **Sentiment analysis** `[⚡ Critical]` — *Quant: news/earnings signals*
- [ ] **Word2Vec, GloVe, FastText** `[✅ Required]` — *AI: embeddings*
- [ ] **Sentence embeddings** `[⚡ Critical]` — *AI: RAG; Quant: semantic search*

### 11.2 Domain-Specific & Sequence NLP
- [ ] **Financial NLP — Loughran-McDonald** `[⚡ Critical]` — *Quant: earnings call analysis*
- [ ] **FinBERT** `[⚡ Critical]` — *Quant: sentiment scoring*
- [ ] **Transformer — Attention mechanisms** `[⚡ Critical]`
- [ ] **Transformer — Encoder-decoder architecture** `[⚡ Critical]`

---

## Phase 5 — The Builder's Toolkit & Infrastructure

### 12.1 Relational & Distributed Storage
- [ ] **SQL joins (all types)** `[⚡ Critical]`
- [ ] **SQL indexing & query optimization** `[⚡ Critical]`
- [ ] **ACID properties** `[⚡ Critical]` — *AI: system design*
- [ ] **PostgreSQL** `[⚡ Critical]`
- [ ] **MongoDB (NoSQL document)** `[✅ Required]` — *AI: unstructured data*
- [ ] **Redis (NoSQL key-value)** `[✅ Required]` — *AI: caching; Quant: tick cache*
- [ ] **Parquet, Apache Arrow** `[⚡ Critical]` — *Both: efficient data storage*
- [ ] **Data warehouses (BigQuery, Snowflake)** `[⚡ Critical]` — *AI: primary; Quant: analytics*
- [ ] **Vector databases (FAISS, Pinecone)** `[✅ Required]` — *AI: RAG pipelines*
- [ ] **HNSW algorithm** `[✅ Required]` — *AI: vector search*

### 13.1 System Architecture
- [ ] **Fault tolerance** `[⚡ Critical]` — *AI: system design rounds*
- [ ] **Load balancing** `[⚡ Critical]` — *AI: system design rounds*
- [ ] **CAP theorem** `[⚡ Critical]` — *AI: system design rounds*
- [ ] **Consensus protocols (Raft, Paxos)** `[✅ Required]` — *AI: distributed systems*
- [ ] **Apache Kafka** `[⚡ Critical]` — *Both: real-time data streaming*
- [ ] **RabbitMQ** `[✅ Required]` — *AI: message queues*
- [ ] **ETL / ELT pipelines** `[⚡ Critical]`
- [ ] **Apache Spark** `[⚡ Critical]` — *Both: large-scale data*

### 13.2 Ultra-Low Latency Engineering
- [ ] **Kernel bypass networking (DPDK)** `[✅ Required]` — *Quant: HFT infrastructure*
- [ ] **Solarflare OpenOnload** `[✅ Required]` — *Quant: HFT NIC bypass*
- [ ] **FPGA acceleration concepts** `[✅ Required]` — *Quant: co-location*
- [ ] **Hardware acceleration** `[✅ Required]` — *AI: GPU; Quant: FPGA/ASIC*
- [ ] **FIX protocol socket streams** `[✅ Required]` — *Quant: exchange connectivity*

### 14.1 CI/CD & Development Workflows
- [ ] **Git workflows** `[⚡ Critical]`
- [ ] **Unit testing** `[⚡ Critical]`
- [ ] **Integration testing** `[⚡ Critical]`
- [ ] **End-to-end testing** `[✅ Required]` — *AI: ML pipelines*
- [ ] **CI pipelines (GitHub Actions)** `[⚡ Critical]` — *AI: MLOps*
- [ ] **CD pipelines** `[⚡ Critical]` — *AI: production deployment*
- [ ] **Code linting** `[⚡ Critical]`
- [ ] **Microservices architectures** `[✅ Required]` — *AI: system design*
- [ ] **Event-driven architectures** `[⚡ Critical]` — *AI: async; Quant: market events*

### 14.2 MLOps & Production Monitoring
- [ ] **MLflow** `[⚡ Critical]` — *AI: experiment tracking*
- [ ] **Weights & Biases** `[⚡ Critical]` — *AI: experiment tracking*
- [ ] **Continuous training pipelines** `[⚡ Critical]` — *AI: production ML*
- [ ] **Data drift monitoring** `[⚡ Critical]` — *AI: production health*
- [ ] **Concept drift monitoring** `[⚡ Critical]` — *AI: production health*
- [ ] **FastAPI** `[⚡ Critical]` — *AI: model serving*
- [ ] **Flask** `[✅ Required]` — *AI: rapid prototyping*
- [ ] **gRPC** `[⚡ Critical]` — *AI: high-performance APIs*
- [ ] **API gateways** `[✅ Required]` — *AI: microservices*
- [ ] **OAuth, JWT, RBAC** `[✅ Required]` — *AI: security layer*

### 15.1 Cloud & Containerization
- [ ] **Linux server management** `[⚡ Critical]`
- [ ] **Docker engines** `[⚡ Critical]`
- [ ] **Docker Compose** `[⚡ Critical]`
- [ ] **Kubernetes pod orchestration** `[⚡ Critical]` — *AI: model serving at scale*
- [ ] **Multi-node scaling** `[⚡ Critical]` — *AI: distributed training*
- [ ] **AWS / GCP / Azure** `[⚡ Critical]` — *AI: primary; Quant: storage/compute*
- [ ] **ARM-based instances** `[✅ Required]` — *AI: cost optimization*
- [ ] **Terraform (IaC)** `[⚡ Critical]` — *AI: MLOps infra*
- [ ] **CUDA GPU provisioning** `[⚡ Critical]` — *AI: model training*

---

## Phase 6 — Generative AI

### 16.1 LLM Architecture & Mechanics
- [ ] **Tokens & context windows** `[✅ Required]` — *AI: LLM fundamentals*
- [ ] **Temperature & sampling strategies** `[✅ Required]` — *AI: LLM control*
- [ ] **FlashAttention** `[◐ Secondary]` — *AI: efficiency at scale*
- [ ] **Multi-Query Attention (MQA)** `[◐ Secondary]` — *AI: inference speed*
- [ ] **Grouped-Query Attention (GQA)** `[◐ Secondary]` — *AI: LLM architecture*
- [ ] **Rotary Position Embedding (RoPE)** `[◐ Secondary]` — *AI: LLM architecture*
- [ ] **Mixture of Experts (MoE)** `[◐ Secondary]` — *AI: scaling*
- [ ] **Small Language Models (SLMs)** `[✅ Required]` — *AI: on-device deployment*
- [ ] **Knowledge distillation** `[◐ Secondary]` — *AI: model compression*

### 16.2 Alignment & Customization
- [ ] **Pretraining** `[◐ Secondary]` — *AI: LLM lifecycle*
- [ ] **Fine-tuning** `[✅ Required]` — *AI: customization; Quant: FinBERT*
- [ ] **RLHF** `[◐ Secondary]` — *AI: alignment*
- [ ] **Direct Preference Optimization (DPO)** `[◐ Secondary]` — *AI: alignment*
- [ ] **Instruction tuning** `[◐ Secondary]` — *AI: task-specific models*
- [ ] **LoRA (Parameter-Efficient Fine-Tuning)** `[◐ Secondary]` — *AI: efficient fine-tuning*

### 17.1 RAG — Core Systems & Retrieval
- [ ] **Semantic search** `[⚡ Critical]` — *AI: RAG; Quant: document search*
- [ ] **Hybrid search** `[✅ Required]` — *AI: retrieval accuracy*
- [ ] **Vector embeddings** `[⚡ Critical]` — *Universal for LLM apps*
- [ ] **Chunking strategies** `[✅ Required]` — *AI: document ingestion*
- [ ] **Metadata handling** `[✅ Required]` — *AI: retrieval filtering*
- [ ] **Indexing** `[⚡ Critical]` — *AI: search performance*
- [ ] **Query transformation** `[✅ Required]` — *AI: RAG accuracy*
- [ ] **Query routing** `[✅ Required]` — *AI: multi-source RAG*
- [ ] **Re-ranking** `[✅ Required]` — *AI: retrieval precision*

### 17.2 Advanced RAG Methodologies
- [ ] **Knowledge graphs** `[⚡ Critical]` — *AI: structured retrieval; Quant: financial graphs*
- [ ] **Multi-modal RAG** `[◐ Secondary]` — *AI: vision+text*
- [ ] **Document parsing** `[⚡ Critical]` — *Both: alternative data*
- [ ] **Self-RAG** `[◐ Secondary]` — *AI: advanced retrieval*

### 18.1 Prompt Engineering & Reasoning
- [ ] **Chain-of-Thought (CoT) prompting** `[✅ Required]` — *AI: reasoning tasks*
- [ ] **ReAct prompting** `[✅ Required]` — *AI: agent tools*
- [ ] **Tree of Thoughts (ToT)** `[◐ Secondary]` — *AI: complex reasoning*
- [ ] **Self-reflection prompting** `[◐ Secondary]` — *AI: output quality*
- [ ] **DSPy (Declarative AI)** `[◐ Secondary]` — *AI: programmatic prompting*
- [ ] **Prompt compilation** `[◐ Secondary]` — *AI: optimization*

---

## Phase 7 — Agents & Reinforcement Learning

### 19.1 RL Fundamentals & Value-Based Methods
- [ ] **Markov Decision Processes (MDPs)** `[⚡ Critical]` — *AI: RL; Quant: trading strategy*
- [ ] **Bellman equations** `[⚡ Critical]` — *Universal RL foundation*
- [ ] **Q-Learning** `[⚡ Critical]`
- [ ] **Deep Q-Networks (DQN)** `[⚡ Critical]`

### 19.2 Advanced RL Frameworks
- [ ] **Policy gradients (REINFORCE)** `[⚡ Critical]` — *AI: primary; Quant: strategy research*
- [ ] **Proximal Policy Optimization (PPO)** `[⚡ Critical]` — *AI: RLHF; Quant: strategy*
- [ ] **Soft Actor-Critic (SAC)** `[✅ Required]` — *AI: continuous control*
- [ ] **Multi-Agent RL (MARL)** `[⚡ Critical]` — *AI: multi-agent; Quant: market sim*

### 20.1 Agent Architecture
- [ ] **Agent loops** `[✅ Required]` — *AI: agentic systems*
- [ ] **Tool usage schemas** `[✅ Required]` — *AI: function-calling agents*
- [ ] **Function calling** `[✅ Required]` — *AI: LLM tool integration*
- [ ] **Stateful memory management** `[✅ Required]` — *AI: persistent agents*
- [ ] **Human-in-the-loop workflows** `[✅ Required]` — *AI: production safety*

### 20.2 Frameworks & Routing Logic
- [ ] **OpenRouter integrations** `[◐ Secondary]` — *AI: multi-LLM routing*
- [ ] **n8n workflow automation** `[◐ Secondary]` — *AI: visual pipelines*
- [ ] **Apache Airflow** `[⚡ Critical]` — *Both: pipeline orchestration*
- [ ] **LangGraph** `[✅ Required]` — *AI: stateful agents*
- [ ] **AutoGen** `[◐ Secondary]` — *AI: multi-agent*
- [ ] **CrewAI** `[◐ Secondary]` — *AI: role-based agents*

---

## Phase 8 — Production Safety, Evaluation & Portfolios

### 21.1 LLM Deployment & Inference Optimization
- [ ] **AWQ quantization** `[◐ Secondary]` — *AI: efficient inference*
- [ ] **GPTQ quantization** `[◐ Secondary]` — *AI: efficient inference*
- [ ] **GGUF quantization** `[◐ Secondary]` — *AI: local LLM deployment*
- [ ] **vLLM inference engine** `[◐ Secondary]` — *AI: high-throughput serving*
- [ ] **Ollama** `[◐ Secondary]` — *AI: local development*
- [ ] **TensorRT-LLM** `[◐ Secondary]` — *AI: NVIDIA GPU inference*
- [ ] **KV cache optimization** `[◐ Secondary]` — *AI: latency reduction*
- [ ] **Prompt caching** `[◐ Secondary]` — *AI: API cost reduction*
- [ ] **Speculative decoding** `[◐ Secondary]` — *AI: inference acceleration*

### 22.1 AI Safety & Guardrails
- [ ] **Prompt injection defenses** `[◐ Secondary]` — *AI: production security*
- [ ] **Data exfiltration defenses** `[⚡ Critical]` — *Both: compliance*
- [ ] **Jailbreaking defenses** `[◐ Secondary]` — *AI: product safety*
- [ ] **NeMo Guardrails** `[◐ Secondary]` — *AI: LLM safety layer*
- [ ] **PII masking** `[⚡ Critical]` — *Both: regulatory compliance*
- [ ] **AI watermarking** `[◐ Secondary]` — *AI: content attribution*

### 22.2 Evaluation Metrics
- [ ] **LLM-as-a-Judge** `[◐ Secondary]` — *AI: model evaluation*
- [ ] **Context precision & recall** `[✅ Required]` — *AI: RAG evaluation*
- [ ] **MMLU benchmark** `[◐ Secondary]` — *AI: capability evaluation*
- [ ] **HumanEval benchmark** `[✅ Required]` — *AI: code evaluation*
- [ ] **Needle-in-a-Haystack testing** `[◐ Secondary]` — *AI: long context eval*
- [ ] **LLM tracing** `[◐ Secondary]` — *AI: debugging agents*
- [ ] **LangSmith** `[◐ Secondary]` — *AI: agent observability*
- [ ] **Phoenix (Arize)** `[◐ Secondary]` — *AI: LLM monitoring*

### 23.1 & 23.2 Capstone Engineering Portfolios
- [ ] **Robust server environments** `[✅ Required]`
- [ ] **Containerized environments (Docker)** `[⚡ Critical]`
- [ ] **Multi-node environments** `[✅ Required]` — *AI: distributed training*
- [ ] **Continuous model training pipelines** `[⚡ Critical]` — *Both: production ML*
- [ ] **Full-stack portfolio websites** `[✅ Required]`
- [ ] **3D portfolio websites (Three Fiber, Spline)** `[◐ Secondary]` — *AI: visual differentiation*
- [ ] **Backend data pipeline visualization** `[✅ Required]`
- [ ] **Financial sentiment analysis engine** `[⚡ Critical]` — *AI+Quant: bridge project*
- [ ] **Statistical arbitrage backtesting pipeline** `[⚡ Critical]` — *Quant+AI: hiring signal*
- [ ] **Multi-agent orchestration (project)** `[✅ Required]` — *AI: showcase*
- [ ] **Purged cross-validation implementation** `[⚡ Critical]` — *Quant: anti-leakage*

---
