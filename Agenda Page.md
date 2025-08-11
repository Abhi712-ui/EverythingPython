# Agenda Page

Status: Active

Here is a complete, no-nonsense roadmap to reach AI engineer competency. Follow the phases. Ship the milestones.

# Role target

Design, train, evaluate, and deploy ML/LLM systems that serve users at scale. Own data, models, APIs, infra, and monitoring.

# Phase 0 — Environment and habits

- OS + tooling: Linux or WSL2, Git, SSH, Make, tmux, VS Code, Docker.
- Python 3.11+, conda/uv, virtualenvs, poetry/pip-tools, pre-commit.
- Reading code daily. Writing unit tests. Small commits. Clear READMEs.

Milestones

- Dotfiles repo. One-click project template (lint, test, format, CI).
- Hello-world Docker + FastAPI service deployed to a cheap VM.

# Phase 1 — Programming and math foundations

Programming

- Python: typing, dataclasses, generators, context managers, asyncio basics.
- Data stack: NumPy, pandas, pyarrow, polars.
- C++ (intro): memory model, RAII, STL, pybind11 for perf-critical ops.

Math

- Linear algebra: vectors, matrices, SVD, eigen decomposition.
- Probability: random variables, expectations, Bayes rule.
- Calculus + optimization: gradients, chain rule, SGD variants.
- Stats: bias/variance, confidence intervals, hypothesis tests.

Milestones

- Implement from scratch: k-NN, linear/logistic regression, decision tree, k-means. Verify against scikit-learn.

# Phase 2 — Classical ML and data work

- scikit-learn pipelines, ColumnTransformer, model selection, cross-validation.
- Feature engineering for tabular, leakage avoidance.
- Imbalanced data, calibration, interpretability (permutation importance, SHAP basics).
- Data plumbing: file formats (CSV/Parquet), schemas, validation (Great Expectations or pandera).

Milestones

- End-to-end tabular ML API: train → persist → serve with FastAPI. Dockerized. CI tests. Basic monitoring.

# Phase 3 — Deep learning core

- PyTorch: tensor ops, autograd, nn.Module, DataLoader, training loops.
- Training practice: initialization, normalization, regularization, schedulers, mixed precision, gradient clipping, checkpointing, reproducibility.
- Computer vision: CNNs, augmentations, transfer learning.
- Sequence models: RNNs, attention, Transformers.
- Experiment tracking: MLflow or Weights & Biases.

Milestones

- Recreate ResNet block and Transformer encoder from scratch. Match library outputs on toy inputs.
- Image classifier on a custom dataset. >90% on a defined metric. Logged and reproducible.

# Phase 4 — LLM stack and generative models

- Tokenization, BPE, positional encodings, KV cache, sampling, temperature, top-k/p.
- Fine-tuning methods: full finetune vs LoRA/QLoRA, PEFT. Checkpoint formats, adapters, quantization (8/4-bit), inference throughput.
- Retrieval-augmented generation (RAG): chunking, embeddings, re-ranking, vector indexes (FAISS or a hosted vector DB), freshness and deletions.
- Tool use and agents: calling functions/tools safely, timeouts, retries, sandboxing.
- Evaluation: exact match, BLEU/ROUGE, faithfulness/groundedness, RAG evals, toxicity/safety checks.
- Serving: vLLM or Text Generation Inference, concurrent batching, token throughput, cost control.

Milestones

- Build a RAG microservice: ingest docs → vector store → query → generate → cite. Include automated evals and latency/error dashboards.
- Finetune a small open model with LoRA on a narrow task. Compare to zero-shot baseline.

# Phase 5 — MLOps, data engineering, and production

- Packaging + CI/CD: GitHub Actions, unit/integration tests, model tests.
- Containers and orchestration: Docker, Kubernetes, Helm basics.
- Feature and model management: MLflow registry or equivalent.
- Data platforms: Spark or Ray basics, Airflow/Prefect for pipelines, Kafka for streams.
- Observability: logging, metrics, traces. Drift, data quality, and performance monitors (Evidently or custom).
- Security and privacy: secrets, PII handling, access control, rate limiting, prompt injection defenses.
- Cloud: pick one (AWS/GCP/Azure). Learn IAM, storage, compute, networking, GPUs, autoscaling, cost monitoring.
- Inference optimization: ONNX, TensorRT-LLM, quantization trade-offs.

Milestones

- Blue-green deploy of a model service to Kubernetes with autoscaling. Canary metrics decide promotion.
- Data pipeline that retrains nightly with validation gates and rollback.

# Phase 6 — Specialization tracks (choose 1–2)

- LLM systems: long-context, structured outputs, function calling, multi-tool agents, eval harnesses, safety.
- Vision: detection, segmentation, multimodal encoders, diffusion models.
- Recs/Ranking: embeddings at scale, approximate nearest neighbor, multi-objective metrics.
- Speech: ASR/TTS pipelines, diarization, streaming constraints.
- Optimization/Systems: CUDA basics, custom PyTorch ops, Triton kernels, memory and throughput profiling.

Milestones

- One production-grade project in the chosen track with real users or real load.

# Portfolio projects that signal “hire”

- Tabular ML API with tests, CI, container, monitoring. Public repo and live demo.
- LLM RAG service with automated evaluations and abuse protections. Clear latency and cost metrics.
- Finetuned small model for a niche task with a comparison study and write-up.
- A Kubernetes-deployed model with blue-green rollout and observable SLOs.
- Optional: a small CUDA/Triton kernel that speeds up a real bottleneck, with benchmarks.

# Interview prep

- DSA refresh: arrays, strings, hash maps, trees/graphs, two-pointer, BFS/DFS, heaps. Solve 100–150 targeted problems.
- ML theory: bias/variance, overfitting, regularization, eval metrics, A/B tests, leakage.
- Systems: HTTP, REST, gRPC, concurrency, backpressure, caching, queues, idempotency.
- Debug drills: make a training loop converge from scratch. Diagnose NaNs, exploding grads, data bugs, and nondeterminism.

# Suggested sequence by time

- Months 0–2: Phase 0–1.
- Months 3–4: Phase 2 + first project.
- Months 5–7: Phase 3 + vision or NLP mini-projects.
- Months 8–10: Phase 4 + LLM project.
- Months 11–12: Phase 5 + deploy to K8s.
- Months 13+: Phase 6 specialization and polish. Interview prep in parallel.

# Minimal resource list

- Core reading: Murphy “Probabilistic ML,” Goodfellow “Deep Learning,” Bishop “PRML.”
- Hands-on: fast.ai lessons, PyTorch docs and tutorials.
- MLOps: “Designing Machine Learning Systems” (Lakshmanan et al.) and production blogs from major cloud providers.

# How to work week to week

- 70% building, 20% reading, 10% notes.
- Every week: one reproducible experiment, one measurable improvement, one documented lesson.
- Ship a small artifact weekly: PR, blog note, or demo.

If you want, give your current level and constraints. I will tailor this into a 12-week plan with exact tasks, checkpoints, and rubrics.
