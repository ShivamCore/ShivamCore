# Shivam Mishra

Backend and systems engineer. I build agent runtimes, evidence-grounded ML systems, and multi-tenant SaaS backends — with an emphasis on treating model output as untrusted input, failing closed, and making claims I can back with tests.

Most of my strongest work lives in private repositories (links below are marked **private** — happy to walk through them on request). The flagship I can show in full is open source:

## Flagship (public)

### [AgentOS](https://github.com/ShivamCore/AgentOS) · Python · MIT
A local-first agent runner. A local LLM plans a coding task as a dependency graph; AgentOS **validates the plan rather than repairing it**, schedules independent steps concurrently, and executes each through an authorized tool layer and a **fail-closed Docker sandbox** (no Docker → nothing runs). SQLite is the source of truth; crashed runs are marked failed, not silently resumed.
- Why it's interesting: an explicit state machine with illegal-transition guards, plan validation that rejects cycles/dangling-deps/unauthorized tools, and reproducible scheduler + inference benchmarks with raw JSON.
- Evidence: 288 passing tests (9 skipped for Docker/Ollama); ADRs documenting each decision; CI runs lint, type-check, security scan, and the suite.

## Selected private work

Available on request; each README is written to be audited, with honest status and limitations.

- **xTalAI** — Evidence-grounded QA over a crystallography corpus: BM25 / dense / hybrid / cross-encoder retrieval with bootstrap CIs, cited extractive generation, a claim validator (entities, values+units, polarity), and similarity-gated **abstention** so it declines rather than guesses. 537 tests; reproducibility gate in CI.
- **Valenza Lead Recovery platform** — Multi-tenant revenue-recovery SaaS (Next.js + Postgres/Prisma + Redis/BullMQ + WhatsApp Cloud API). Exactly-once scheduled sends claimed atomically, opt-out enforced in a single gateway, deterministic/explainable opportunity scoring, consent-first messaging. ~864 tests; built up over documented milestones from an earlier 199-test version.
- **Medspa growth platform** — Next.js + Supabase SaaS whose security layer is the point: a **hash-chained, tamper-evident audit log**, application-level field encryption with key rotation, TOTP 2FA, rate limiting, and admin actions that require a written justification.
- **SPECTRE** — Geospatial anomaly-detection prototype: six statistical detectors (Z-score, EWMA, Bayesian, convergence, absence, drift), multi-source ingestion, event fusion, and a Cesium + deck.gl globe. ~35k LOC; an early snapshot, documented as such.
- **IoT monitoring dashboard** — ESP8266 + HX711 load-cell telemetry streamed to the browser over Server-Sent Events, with scrypt-hashed auth and no mock data. Type-checks, lints and builds clean.

## How I work

- Plans, LLM output and webhooks are untrusted input — validate, authorize, and fail closed.
- I'd rather ship a smaller thing with tests and a benchmark than a larger thing I can't verify.
- READMEs state what works, what doesn't, and what wasn't checked.

## Stack

- **Languages:** Python, TypeScript, C++
- **Backend:** FastAPI, Celery, Next.js (App Router), SQLAlchemy/Prisma, Postgres/SQLite, Redis/BullMQ
- **ML / AI:** retrieval (BM25, dense, rerank), local LLM inference (Ollama, `node-llama-cpp`), scikit-learn, evaluation with CIs and abstention
- **Practices:** Docker sandboxing, RBAC, encryption & audit logging, CI (lint/type-check/test), ADRs

## Also on my profile

- [Asset-Flow](https://github.com/ShivamCore/Asset-Flow) — team hackathon ERP (FastAPI vertical-slice modules + Next.js); 191 backend tests.
- [Cpp](https://github.com/ShivamCore/Cpp) and [Python](https://github.com/ShivamCore/Python) — foundations: C++ exercises/projects and an applied-ML portfolio of small Flask-served models.

## Connect

[LinkedIn](https://www.linkedin.com/in/shivamm-mishraa/)
