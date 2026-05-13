# Proof Points -- Nikhil Swami

## Price is Right (2026)
**Hero metric:** Fine-tuned Llama 3.2 7B outperformed GPT-4.1 and Claude Opus standalone on price prediction.
**What I built:** End-to-end LLM pipeline — data preprocessing on 1.6M Amazon Electronics products, QLoRA fine-tuning, multi-model RAG ensemble using LangChain, LangGraph and Ollama.
**Key result:** 4.2% MAE, $42 mean error across $0–$1,000 range.
**Key decision:** Chose ensemble approach (fine-tuned + frontier + RAG) over single-model because no single model handled both long-tail and mainstream products equally well.
**Stack:** Python, PyTorch, LangChain, LangGraph, QLoRA, Ollama, HuggingFace

## Text2SQL (2026)
**Hero metric:** 74.5% execution accuracy on Spider benchmark (1,034 queries) using a 7B open-source model.
**What I built:** RAG+Repair Text2SQL pipeline using Qwen2.5-Coder-7B with FAISS retrieval, Steiner tree join path construction, and a 3-level SQL validation/repair loop.
**Key result:** Improved Exact Match by +20 percentage points over zero-shot baseline (17.9% → 38.7%). Evaluated across 2,041 benchmark examples (Spider + CoSQL) with full hardness breakdown.
**Key decision:** Empirically discovered RAG degrades nested query performance by 8.9% while boosting hard queries by +9.6% — led to designing a hybrid routing architecture that selects RAG vs direct inference based on query complexity.
**Stack:** Python, Qwen2.5-Coder-7B, FAISS, RAG Pipelines, Spider benchmark, CoSQL
**GitHub:** https://github.com/nikhilSwami11/text2sql


## Onsite Teams — Flutter Migration (Feb–Aug 2024)
**Hero metric:** 20% user acquisition growth, 500K+ downloads post-migration.
**What I did:** End-to-end migration from native Android to Flutter. Integrated Google Maps SDK, payment systems via Method Channels. Applied Clean Architecture + BLoC + TDD.
**Key result:** 32% reduction in production defects.
**Key decision:** Chose BLoC over Riverpod because the team was large enough that explicit event/state separation reduced merge conflicts.
**Stack:** Flutter, Dart, Go, gRPC, REST, AWS EKS, Kafka, Redis

## Onsite Teams — RAG Helpbot (2024)
**What I built:** Internal RAG-based support bot using Python, LangChain, Mistral 7B (local via Ollama).
**Impact:** Automated repetitive support workflows, reduced engineering overhead.
**Key decision:** Used local model (Mistral 7B via Ollama) over OpenAI API to avoid sending internal data to third-party servers — a security-first call.
**Stack:** Python, LangChain, Ollama, Mistral 7B

## Nowfloats — .NET SaaS Backend (Jan 2023–Feb 2024)
**Hero metric:** 99.5% uptime for 10,000+ business users.
**What I did:** Built and maintained scalable .NET Core / C# backend services on Azure. Optimized SQL Server queries (15% latency reduction). Set up GitHub Actions CI/CD, cutting deployments 14% per sprint.
**Key decision:** Implemented schema indexing strategy rather than query rewriting because the codebase had too many call sites — indexing was the highest-leverage intervention.
**Stack:** C#, .NET Core, SQL Server, Azure, GitHub Actions, Flutter, Firebase

## Fraazo — SDUI Flutter App (Jan–Sept 2022)
**Hero metric:** 1M+ user production Flutter app; crash-free sessions 96% → 99%.
**What I did:** Built Server-Driven UI system in Flutter enabling layout changes without app releases. Fixed framework-level memory leaks. Ran Firebase A/B tests. Implemented Go backend services for rider-facing app.
**Key decision:** SDUI approach chosen because the team needed to run growth experiments faster than App Store review cycles allowed — the architecture directly enabled the business's growth loop.
**Stack:** Flutter, Dart, Go, Firebase, SDUI

## NutriFlow (2026)
**What I built:** End-to-end AI agent for recipe generation and photo-based calorie estimation using GPT-4o Vision and OpenAI Whisper for voice input.
**Key decision:** Benchmarked RAG vs. direct prompt engineering for recipe retrieval — RAG won on personalization but direct prompting was faster for generic queries. Shipped an ensemble approach.
**Stack:** Go, Python, GPT-4o, Whisper, LangChain, ChromaDB, MongoDB

## Affinity — Semantic Social Network (2026)
**Hero metric:** Sub-100ms PostgreSQL query response on a semantically-driven social graph.
**What I built:** Full-stack platform — React/Next.js + TypeScript frontend, Python/FastAPI backend, PostgreSQL. Core feature is a semantic placement algorithm using sentence-transformers and UMAP that maps users into a 2D semantic space based on interests.
**Key decision:** Chose UMAP over t-SNE for dimensionality reduction because UMAP preserves global structure better at scale and is significantly faster at inference — important for a real-time placement feature.
**Stack:** Next.js, TypeScript, React, FastAPI, Python, PostgreSQL, sentence-transformers, UMAP