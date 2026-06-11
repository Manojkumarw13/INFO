# Tools Master List — AI & Data Science Roadmap
### Every Tool Grouped by Category | What Each One Does

---

## 1. Programming Languages

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Python** | Primary language for all ML, data science, and AI work. Scripting, pipelines, model training, APIs | Both | 1 |
| **C++** | High-performance systems, HFT infrastructure, low-latency quant engines, custom data structures | Quant | 1 |
| **SQL** | Querying and manipulating structured data in relational databases | Both | 5 |

---

## 2. Python Scientific Computing Stack

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **NumPy** | N-dimensional arrays, linear algebra, vectorized math operations | Both | 1 |
| **Pandas** | Tabular data manipulation, time series, financial data wrangling | Both | 1 |
| **SciPy** | Scientific computing — optimization, integration, statistics, signal processing | Both | 1 |
| **Matplotlib** | Static data visualization, charts, financial plots | Both | 1 |
| **Plotly** | Interactive visualizations and dashboards | Both | 1 |
| **Numba** | JIT compilation for Python — accelerates numerical code to near-C speed | Both | 1 |
| **Cython** | Converts Python to C extensions for performance-critical code | Quant | 1 |

---

## 3. Machine Learning Libraries

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Scikit-learn** | Classical ML — regression, classification, clustering, preprocessing, pipelines, cross-validation | Both | 3 |
| **XGBoost** | Gradient boosted trees — industry standard for structured/tabular data | Both | 3 |
| **LightGBM** | Faster gradient boosting — handles large datasets with leaf-wise splitting | Both | 3 |
| **CatBoost** | Gradient boosting optimized for categorical features — minimal preprocessing needed | Both | 3 |
| **SHAP** | Model explainability — SHapley Additive exPlanations for feature importance | Both | 3 |

---

## 4. Deep Learning Frameworks

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **PyTorch** | Primary deep learning framework — model building, training loops, autograd, custom architectures | Both | 4 |
| **TensorFlow / Keras** | Alternative DL framework — Keras API for rapid prototyping, TFLite for edge deployment | AI/DS | 4 |
| **JAX** | High-performance ML research — NumPy-compatible with autograd + XLA compilation. Used at Google DeepMind | AI/DS | 4 |

---

## 5. NLP & Transformer Tools

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Hugging Face Transformers** | Loading, fine-tuning, and deploying pre-trained transformer models (BERT, GPT, T5, LLaMA) | Both | 4 |
| **Hugging Face Datasets** | Accessing and processing large NLP/ML datasets with memory-efficient streaming | AI/DS | 4 |
| **Hugging Face PEFT** | Parameter-Efficient Fine-Tuning library — implements LoRA, QLoRA, prefix tuning | AI/DS | 6 |
| **FinBERT** | Pre-trained BERT model for financial sentiment analysis on earnings calls and filings | AI+Quant | 4 |
| **spaCy** | Industrial-strength NLP library — tokenization, NER, dependency parsing pipelines | AI/DS | 4 |
| **NLTK** | NLP preprocessing toolkit — stemming, lemmatization, BoW construction | AI/DS | 4 |

---

## 6. Time Series & Financial ML

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **PyTorch Forecasting** | Deep learning time series library — Temporal Fusion Transformers (TFT) and N-BEATS | Both | 4 |
| **statsmodels** | Classical statistical models — ARIMA, GARCH, VAR, cointegration tests, hypothesis testing | Quant | 1/3 |
| **arch** | ARCH/GARCH volatility modelling in Python | Quant | 1 |
| **QuantLib** | Derivatives pricing, yield curves, fixed income analytics, and Monte Carlo simulation | Quant | 2 |
| **Backtrader** | Backtesting framework for algorithmic trading strategies with event-driven architecture | Quant | 8 |
| **VectorBT** | Vectorized ultra-fast backtesting — runs thousands of strategy simulations in seconds | Quant | 8 |

---

## 7. LLM Frameworks & Orchestration

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **LangChain** | Building LLM applications — chains, retrieval pipelines, tool calling, memory management | AI/DS | 6 |
| **LangGraph** | Stateful multi-agent workflows with cycles and conditional routing — built on LangChain | AI/DS | 7 |
| **LlamaIndex** | RAG-focused LLM framework — document ingestion, chunking, query engines, and retrieval | AI/DS | 6 |
| **DSPy** | Declarative LLM programming — programmatically optimizes prompts and pipelines instead of hand-tuning | AI/DS | 6 |
| **OpenRouter** | Multi-LLM API routing — single API to access GPT-4, Claude, LLaMA, Mistral, and others | AI/DS | 7 |

---

## 8. LLM Inference Engines

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **vLLM** | High-throughput LLM serving with PagedAttention — the production standard for serving open-source LLMs | AI/DS | 8 |
| **Ollama** | Running LLMs locally with one command — for development, testing, and offline inference | AI/DS | 8 |
| **TensorRT-LLM** | NVIDIA's optimized LLM inference library — maximum GPU throughput for production deployment | AI/DS | 8 |
| **llama.cpp** | CPU and GPU inference for quantized LLMs (GGUF format) — runs LLMs on consumer hardware | AI/DS | 8 |

---

## 9. Quantization Formats & Tools

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **GPTQ** | Post-training quantization — 4-bit weight quantization for LLMs with minimal accuracy loss | AI/DS | 8 |
| **AWQ** | Activation-aware Weight Quantization — preserves outlier weights for better accuracy than GPTQ | AI/DS | 8 |
| **GGUF** | File format for quantized LLMs used by llama.cpp — supports 2-bit to 8-bit quantization | AI/DS | 8 |

---

## 10. Agentic Frameworks

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **AutoGen** | Microsoft's multi-agent framework — agents converse, delegate tasks, and use tools in group chats | AI/DS | 7 |
| **CrewAI** | Role-based multi-agent orchestration — agents with defined roles collaborate on complex tasks | AI/DS | 7 |
| **n8n** | Visual node-based workflow automation — drag-and-drop agent pipelines with 400+ integrations | AI/DS | 7 |
| **Apache Airflow** | DAG-based pipeline orchestration — schedules and monitors batch ML and data workflows | Both | 7 |

---

## 11. MLOps & Experiment Tracking

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **MLflow** | Experiment tracking, model registry, versioning, and serving — open-source MLOps standard | AI/DS | 5 |
| **Weights & Biases (W&B)** | Rich experiment tracking with charts, hyperparameter sweeps, artifact management, and team collaboration | AI/DS | 5 |
| **Evidently AI** | Data drift detection, model performance monitoring, and data quality reporting in production | AI/DS | 5 |
| **DVC** | Data Version Control — tracks datasets and models alongside code in Git | AI/DS | 5 |

---

## 12. LLM Observability & Evaluation

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **LangSmith** | LLM tracing, debugging, and evaluation — logs every chain/agent step for inspection and testing | AI/DS | 8 |
| **Phoenix (Arize)** | Open-source LLM observability — traces, evals, latency monitoring, and prompt analysis | AI/DS | 8 |
| **RAGAS** | RAG evaluation framework — measures context precision, recall, faithfulness, and answer relevance | AI/DS | 8 |
| **NeMo Guardrails** | NVIDIA's safety layer for LLMs — topic control, PII masking, jailbreak prevention, and output filtering | AI/DS | 8 |

---

## 13. Databases — Relational

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **PostgreSQL** | Primary open-source relational database — used for structured data, time series, and financial records | Both | 5 |
| **SQLite** | Lightweight embedded database — local development and testing | Both | 5 |

---

## 14. Databases — NoSQL

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **MongoDB** | Document store for unstructured/semi-structured data — JSON-like documents, flexible schemas | AI/DS | 5 |
| **Redis** | In-memory key-value store — caching, session management, pub/sub, real-time leaderboards | Both | 5 |

---

## 15. Databases — Vector

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **FAISS** | Facebook AI Similarity Search — blazing-fast local vector similarity search for embeddings | AI/DS | 5/6 |
| **Pinecone** | Managed cloud vector database — production RAG pipelines with metadata filtering | AI/DS | 5/6 |
| **Milvus** | Open-source distributed vector database — scales to billions of vectors with HNSW indexing | AI/DS | 5/6 |
| **Weaviate** | Vector database with built-in ML modules — supports hybrid search and multi-modal retrieval | AI/DS | 5/6 |

---

## 16. Data Formats & Columnar Storage

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Parquet** | Columnar file format — efficient storage and querying of large structured datasets | Both | 5 |
| **Apache Arrow** | In-memory columnar format — zero-copy data sharing between tools (Pandas, Spark, DuckDB) | Both | 5 |
| **HDF5** | Hierarchical data format — storing large numerical arrays (tick data, market data) | Quant | 5 |

---

## 17. Data Warehouses & Analytics

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **BigQuery** | Google's serverless data warehouse — SQL analytics on petabyte-scale datasets | AI/DS | 5 |
| **Snowflake** | Cloud data warehouse — separation of compute and storage, multi-cloud analytics | AI/DS | 5 |
| **Redshift** | Amazon's cloud data warehouse — columnar storage with deep AWS integration | AI/DS | 5 |
| **DuckDB** | Embedded analytical database — runs SQL directly on Parquet/Arrow files, no server needed | Both | 5 |
| **dbt** | Data Build Tool — SQL-based transformation layer for building analytics pipelines in the warehouse | AI/DS | 5 |

---

## 18. Data Streaming & Messaging

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Apache Kafka** | Distributed event streaming — real-time data pipelines, market data feeds, ML feature streaming | Both | 5 |
| **RabbitMQ** | Message queue broker — decouples services with reliable async message delivery | AI/DS | 5 |

---

## 19. Data Processing at Scale

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Apache Spark** | Distributed data processing — batch ETL, large-scale ML (MLlib), SQL on massive datasets | Both | 5 |
| **Apache Airflow** | Workflow orchestration — schedules, monitors, and retries data and ML pipelines as DAGs | Both | 5/7 |
| **Prefect** | Modern Python-native workflow orchestration — simpler than Airflow, better for ML pipelines | AI/DS | 5 |

---

## 20. Containerization & Orchestration

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Docker** | Containerizes applications — packages code, dependencies, and environment into portable images | Both | 5 |
| **Docker Compose** | Defines and runs multi-container applications locally — spins up entire stacks with one command | Both | 5 |
| **Kubernetes (K8s)** | Orchestrates containers at scale — auto-scaling, rolling deployments, service discovery, self-healing | AI/DS | 5 |

---

## 21. Cloud Platforms

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **AWS** | Amazon Web Services — EC2 compute, S3 storage, SageMaker ML, Lambda serverless | Both | 5 |
| **GCP** | Google Cloud Platform — Vertex AI, BigQuery, Cloud Run, TPU access for large-scale training | AI/DS | 5 |
| **Azure** | Microsoft Azure — Azure ML, Azure OpenAI Service, Data Factory, Functions | AI/DS | 5 |
| **Oracle Cloud** | ARM-based instances — cost-effective GPU compute for training and inference | AI/DS | 5 |

---

## 22. Infrastructure as Code & DevOps

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **Terraform** | Provisions cloud infrastructure with code — reproducible, version-controlled cloud environments | Both | 5 |
| **Git** | Version control — tracks code changes, enables collaboration and CI/CD workflows | Both | 5 |
| **GitHub Actions** | CI/CD automation — runs tests, builds Docker images, and deploys models on every commit | Both | 5 |

---

## 23. API Frameworks & Serving

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **FastAPI** | Production Python REST APIs — asynchronous, auto-generates OpenAPI docs, used for ML model serving | AI/DS | 5/8 |
| **Flask** | Lightweight Python web framework — rapid prototyping and simple API endpoints | AI/DS | 5 |
| **gRPC** | High-performance remote procedure calls — efficient binary serialization for microservice communication | AI/DS | 5 |

---

## 24. Authentication & Security

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **OAuth 2.0** | Industry-standard authorization protocol — enables third-party login and delegated access | AI/DS | 5 |
| **JWT (JSON Web Tokens)** | Stateless authentication tokens — carries user claims for API authorization | AI/DS | 5 |
| **RBAC** | Role-Based Access Control — restricts system access based on user roles and permissions | AI/DS | 5 |

---

## 25. GPU & Hardware Acceleration

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **CUDA** | NVIDIA's GPU programming platform — enables parallel computation for deep learning training | AI/DS | 5 |
| **DPDK** | Data Plane Development Kit — kernel bypass networking for ultra-low latency packet processing | Quant | 5 |
| **Solarflare OpenOnload** | Kernel bypass networking for HFT — sub-microsecond network latency on Linux | Quant | 5 |
| **FlashAttention** | Memory-efficient attention kernel — 2–4x faster transformer training with less GPU memory | AI/DS | 6 |

---

## 26. Portfolio & Web Technologies

| Tool | Used For | Track | Phase |
|---|---|---|---|
| **React** | JavaScript UI library — building interactive frontend components for portfolio websites | Both | 8 |
| **Three.js** | 3D graphics in the browser — WebGL-based rendering for animated portfolio scenes | Both | 8 |
| **React Three Fiber** | React renderer for Three.js — builds 3D scenes declaratively using React components | Both | 8 |
| **Spline** | No-code 3D design tool — creates interactive 3D scenes exported directly to the web | Both | 8 |

---

## Summary — Tool Count by Category

| Category | # Tools | Primary Track |
|---|---|---|
| Programming Languages | 3 | Both |
| Python Scientific Stack | 7 | Both |
| Machine Learning Libraries | 5 | Both |
| Deep Learning Frameworks | 3 | AI/DS |
| NLP & Transformer Tools | 6 | Both |
| Time Series & Financial ML | 6 | Quant |
| LLM Frameworks | 5 | AI/DS |
| LLM Inference Engines | 4 | AI/DS |
| Quantization Formats | 3 | AI/DS |
| Agentic Frameworks | 4 | AI/DS |
| MLOps & Experiment Tracking | 4 | AI/DS |
| LLM Observability & Evaluation | 4 | AI/DS |
| Databases — Relational | 2 | Both |
| Databases — NoSQL | 2 | AI/DS |
| Databases — Vector | 4 | AI/DS |
| Data Formats & Columnar Storage | 3 | Both |
| Data Warehouses & Analytics | 5 | AI/DS |
| Data Streaming & Messaging | 2 | Both |
| Data Processing at Scale | 3 | Both |
| Containerization & Orchestration | 3 | Both |
| Cloud Platforms | 4 | AI/DS |
| Infrastructure as Code & DevOps | 3 | Both |
| API Frameworks & Serving | 3 | AI/DS |
| Authentication & Security | 3 | AI/DS |
| GPU & Hardware Acceleration | 4 | Both |
| Portfolio & Web Technologies | 4 | Both |
| **Total** | **109** | |
