---
title: "GitHub - raphaelmansuy/edgequake: High-performance GraphRAG inspired from LightRag written in Rust"
url: https://github.com/raphaelmansuy/edgequake
tags: [framework, AI/ML, research]
category: Research Paper
date: 2026-02-10
id: E74621DF-9308-4D46-954C-C2801D4DC257
created: 2026-02-10T08:51:27Z
modified: 2026-02-10T08:51:27Z
---
# GitHub - raphaelmansuy/edgequake: High-performance GraphRAG inspired from LightRag written in Rust

## Summary

High-performance GraphRAG inspired from LightRag written in Rust

**Category:** `Research Paper`  

**Tags:** `framework` `AI/ML` `research`

**Source:** [https://github.com/raphaelmansuy/edgequake](https://github.com/raphaelmansuy/edgequake)

---

## Content

Repository: raphaelmansuy/edgequake
Description: High-performance GraphRAG inspired from LightRag written in Rust

⭐ Stars: 15
Language: Rust

README:

# EdgeQuake

> **High-Performance Graph-RAG Framework in Rust**  
> Transform documents into intelligent knowledge graphs for superior retrieval and generation

[![Rust](https://img.shields.io/badge/rust-1.78+-orange.svg?style=flat&logo=rust)](https://www.rust-lang.org)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg?style=flat)](LICENSE)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg?style=flat)](https://github.com/raphaelmansuy/edgequake)
[![Documentation](https://img.shields.io/badge/docs-available-blue.svg?style=flat)](docs/README.md)

---



![Screenshot of EdgeQuake Frontend](docs/assets/01-screenshot.png)

## Why EdgeQuake?

Traditional RAG systems retrieve document chunks using vector similarity alone. This works for simple lookups but fails on multi-hop reasoning ("How does X relate to Y through Z?"), thematic questions ("What are the major themes?"), and relationship queries. The core problem: **vectors capture semantic similarity but lose structural relationships between concepts**.

**EdgeQuake** solves this by implementing the [LightRAG algorithm](https://arxiv.org/abs/2410.05779) in Rust: documents are not just chunked and embedded — they are decomposed into a **knowledge graph** of entities and relationships. At query time, the system traverses both the vector space and the graph structure, combining the speed of vector search with the reasoning power of graph traversal.

### What Sets EdgeQuake Apart

- **Knowledge Graphs**: LLM-powered entity extraction and relationship mapping create a structured understanding of your documents — not just keyword matching
- **6 Query Modes**: From fast naive vector search to graph-traversing hybrid queries, each mode optimizes for different question types
- **Rust Performance**: Async-first Tokio architecture with zero-copy operations — handles thousands of concurrent requests
- **Advanced PDF Processing**: Table detection, multi-column layout, OCR with quality-based mode fallback
- **Production Ready**: OpenAPI 3.0 REST API, SSE streaming, health checks, multi-tenant workspace isolation
- **Modern Frontend**: React 19 with interactive Sigma.js graph visualizations

### Performance Benchmarks

| Metric                 | EdgeQuake        | Traditional RAG | Improvement |
| ---------------------- | ---------------- | --------------- | ----------- |
| Entity Extraction      | ~2-3x more       | Baseline        | 3x          |
| Query Latency (hybrid) | < 200ms          | ~1000ms         | 5x faster   |
| Document Processing    | 25s (10k tokens) | ~60s            | 2.4x faster |
| Concurrent Users       | 1000+            | ~100            | 10x         |
| Memory Usage (per doc) | 2MB              | ~8MB            | 4x better   |

⚠️ **Experimental Feature — PDF Ingestion**: PDF-to-Markdown extraction is currently in **experimental/early prototype** stage. For comprehensive testing and evaluation of EdgeQuake's core functionality (entity extraction, knowledge graphs, query modes, etc.), we recommend using **Markdown documents** in your initial setup. This ensures you can fully explore the stable features while we continue to refine the PDF processing pipeline.

---

## Features

### 🚀 High Performance

- **Async-First**: Tokio-based runtime for maximum concurrency
- **Zero-Copy**: Efficient memory management with Rust ownership
- **Parallel Processing**: Multi-threaded entity extraction and embeddings
- **Fast Storage**: PostgreSQL AGE for graph + pgvector for embeddings

### Knowledge Graph

- **Entity Extraction**: Automatic detection of people, organizations, locations, concepts, events, technologies, and products (7 configurable types)
- **Relationship Mapping**: LLM-powered relationship identification with keyword tagging
- **Gleaning**: Multi-pass extraction catches 15-25% more entities than single-pass
- **Community Detection**: Louvain modularity optimization clusters related entities for thematic queries
- **Graph Visualization**: Interactive Sigma.js-powered frontend with zoom/pan

### 📄 Advanced PDF Processing

- **Text Mode**: Fast extraction for text-based PDFs
- **Vision Mode**: OCR for scanned documents and images
- **Hybrid Mode**: Automatic quality assessment and fallback
- **Table Detection**: Enhanced detection for complex tables
- **Multi-Column Layout**: Accurate reading order detection

### 🔍 6 Query Modes

1. **Naive**: Simple vector similarity — fastest for keyword-like lookups (~100-300ms)
2. **Local**: Entity-centric with local graph neighborhood — best for specific relationships (~200-500ms)
3. **Global**: Community-based semantic search — best for thematic/high-level questions (~300-800ms)
4. **Hybrid** _(default)_: Combines local + global for balanced, comprehensive results (~400-1000ms)
5. **Mix**: Weighted combination of naive + graph results with configurable ratios
6. **Bypass**: Direct LLM query without RAG retrieval — useful for general questions

### 🌐 REST API

- **OpenAPI 3.0**: Full Swagger documentation at `/swagger-ui`
- **Streaming**: Server-Sent Events (SSE) for real-time responses
- **Versioned**: `/api/v1/*` with backward compatibility
- **Health Checks**: Kubernetes-ready `/health`, `/ready`, `/live`

### 🎯 React 19 Frontend

- **Real-Time Streaming**: Token-by-token generation display
- **Graph Visualization**: Interactive network graph with zoom/pan
- **Document Upload**: Drag-and-drop with progress tracking
- **Configuration UI**: Visual PDF processing config builder

---

## Quick Start

### Prerequisites

- **Rust**: 1.78 or later ([Install Rust](https://rustup.rs))
- **Node.js**: 18+ or Bun 1.0+ ([Install Node](https://nodejs.org))
- **Docker**: For PostgreSQL ([Install Docker](https://www.docker.com/get-started))
- **Ollama**: For local LLM (optional, [Install Ollama](https://ollama.ai))

### Installation (5 minutes)

```bash
# 1. Clone the repository
git clone https://github.com/raphaelmansuy/edgequake.git
cd edgequake

# 2. Install dependencies
make install

# 3. Start the full stack (PostgreSQL + Backend + Frontend)
make dev
```

**That's it!** 🎉

- **Backend**: http://localhost:8080
- **Frontend**: http://localhost:3000
- **Swagger UI**: http://localhost:8080/swagger-ui
- **Provider**: Ollama (local, free)

### First Document Upload

```bash
# Upload a text file
curl -X POST http://localhost:8080/api/v1/documents \
  -H "Content-Type: multipart/form-data" \
  -F "file=@your-document.pdf"
```

**Response**:

```json
{
  "id": "doc-123",
  "status": "completed",
  "chunk_count": 15,
  "entity_count": 12,
  "relationship_count": 8,
  "processing_time_ms": 2500
}
```

### First Query

```bash
# Query the knowledge graph
curl -X POST http://localhost:8080/api/v1/query \
  -H "Content-Type: application/json" \
  -d '{
    "query": "What are the main concepts?",
    "mode": "hybrid"
  }'
```

**Response**:

```json
{
  "answer": "The main concepts are: knowledge graphs, entity extraction, and hybrid retrieval...",
  "sources": [
    { "chunk_id": "chunk-1", "similarity": 0.92 },
    { "chunk_id": "chunk-5", "similarity": 0.87 }
  ],
  "entities": ["KNOWLEDGE_GRAPH", "ENTITY_EXTRACTION"],
  "relationships": [
    {
      "source": "KNOWLEDGE_GRAPH",
      "target": "ENTITY_EXTRACTION",
      "type": "ENABLES"
    }
  ]
}
```

---

## Architecture

```
┌────────────────────────────────────────────────────────────────────────────┐
│                              EdgeQuake System                              │
└────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│  Frontend (React 19 + TypeScript)                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Document    │  │    Query     │  │    Graph     │  │   Settings   │     │
│  │   Upload     │  │  Interface   │  │ Visualization│  │   Config     │     │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘     │
│         │                 │                 │                 │             │
│         └─────────────────┴─────────────────┴─────────────────┘             │
│                                    │                                        │
│                                    ▼                                        │
│  ┌────────────────────────────────────────────────────────────────────┐     │
│  │                         REST API (Axum)                            │     │
│  │  /api/v1/documents  •  /api/v1/query  •  /api/v1/graph             │     │
│  │  OpenAPI 3.0 Spec  •  SSE Streaming  •  Health Checks              │     │
│  └────────────────────────────────────────────────────────────────────┘     │
└─────────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│  Backend (Rust - 11 Crates)                                                 │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │  edgequake-core          │  Orchestration & Pipeline                 │   │
│  │  edgequake-llm           │  OpenAI, Ollama, LM Studio, Mock          │   │
│  │  edgequake-storage       │  PostgreSQL AGE, Memory adapters          │   │
│  │  edgequake-api           │  REST API server                          │   │
│  │  edgequake-pipeline      │  Document ingestion pipeline              │   │
│  │  edgequake-query         │  Query engine (6 modes)                   │   │
│  │  edgequake-pdf           │  PDF extraction (text/vision/hybrid)      │   │
│  │  edgequake-auth          │  Authentication & authorization           │   │
│  │  edgequake-audit         │  Compliance & audit logging               │   │
│  │  edgequake-tasks         │  Background job processing                │   │
│  │  edgequake-rate-limiter  │  Rate limiting middleware                 │   │
│  └──────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                    ┌───────────────┴───────────────┐                        │
│                    ▼                               ▼                        │
│  ┌─────────────────────────────┐   ┌──────────────────────────────────┐     │
│  │   LLM Providers             │   │   Storage Backends               │     │
│  │  • OpenAI (gpt-4.1-nano)    │   │  • PostgreSQL 15+ (AGE + vector) │     │
│  │  • Ollama (gemma3:12b)      │   │  • In-Memory (dev/testing)       │     │
│  │  • LM Studio (local models) │   │  • Graph: Property graph model   │     │
│  │  • Mock (testing, free)     │   │  • Vector: pgvector embeddings   │     │
│  │  Auto-detection via env     │   │                                  │     │
│  └─────────────────────────────┘   └──────────────────────────────────┘     │
└─────────────────────────────────────────────────────────────────────────────┘

                    Data Flow: Document → Chunks → Entities → Graph
                    Query Flow: Question → Graph Traversal → LLM → Answer
```

### How the Algorithm Works

EdgeQuake implements the [LightRAG algorithm](https://arxiv.org/abs/2410.05779) in Rust. The core insight: **extract a knowledge graph during indexing, then traverse it during querying**.

**Indexing Pipeline** (per document):
1. **Chunk** — Split document into ~1200-token segments with 100-token overlap
2. **Extract** — LLM parses each chunk into `(entity, type, description)` and `(source, target, keywords, description)` tuples
3. **Glean** — Optional second pass catches missed entities (improves recall by ~18%)
4. **Normalize** — Deduplicate entities via case normalization and description merging (reduces duplicates by ~36-40%)
5. **Embed** — Generate vector embeddings for chunks and entities
6. **Store** — Write to PostgreSQL: chunks to pgvector, entities/relationships to Apache AGE graph

**Query Flow** (6 modes):
- **Naive** — Vector similarity on chunks only (fast, no graph)
- **Local** — Find relevant entities via vector search, then traverse their local graph neighborhood
- **Global** — Use Louvain community detection to find thematic clusters, retrieve community summaries
- **Hybrid** _(default)_ — Combine local entity context + global community context
- **Mix** — Weighted blend of naive vector results and graph-enhanced results
- **Bypass** — Skip retrieval entirely, pass question directly to LLM

See [LightRAG Algorithm Deep Dive](docs/deep-dives/lightrag-algorithm.md) for the complete technical explanation.

---

## Documentation

### 📚 Complete Documentation Index

Explore the full documentation at [docs/README.md](docs/README.md)

### 🚀 Getting Started (15 minutes)

| Guide                                                      | Description                | Time   |
| ---------------------------------------------------------- | -------------------------- | ------ |
| [Installation](docs/getting-started/installation.md)       | Prerequisites and setup    | 5 min  |
| [Quick Start](docs/getting-started/quick-start.md)         | First ingestion and query  | 10 min |
| [First Ingestion](docs/getting-started/first-ingestion.md) | Understanding the pipeline | 15 min |

### 📖 Tutorials (Hands-On)

| Tutorial                                                               | Description                     |
| ---------------------------------------------------------------------- | ------------------------------- |
| [Building Your First RAG App](docs/tutorials/first-rag-app.md)         | End-to-end tutorial             |
| [PDF Ingestion](docs/tutorials/pdf-ingestion.md)                       | PDF upload and configuration    |
| [Multi-Tenant Setup](docs/tutorials/multi-tenant.md)                   | Workspace isolation             |
| [Document Ingestion](docs/tutorials/document-ingestion.md)             | Upload and processing workflows |
| [Migration from LightRAG](docs/tutorials/migration-from-lightrag.md)   | Python to Rust migration guide  |

### 🏗️ Architecture (How It Works)

| Document                                     | Description                           |
| -------------------------------------------- | ------------------------------------- |
| [Overview](docs/architecture/overview.md)    | System design and components          |
| [Data Flow](docs/architecture/data-flow.md)  | How documents flow through the system |
| [Crate Reference](docs/architecture/crates/) | 11 Rust crates explained              |

### 💡 Core Concepts (Theory)

| Concept                                                 | Description                       |
| ------------------------------------------------------- | --------------------------------- |
| [Graph-RAG](docs/concepts/graph-rag.md)                 | Why knowledge graphs enhance RAG  |
| [Entity Extraction](docs/concepts/entity-extraction.md) | LLM-based entity recognition      |
| [Knowledge Graph](docs/concepts/knowledge-graph.md)     | Nodes, edges, and communities     |
| [Hybrid Retrieval](docs/concepts/hybrid-retrieval.md)   | Combining vector and graph search |

### Deep Dives (Advanced)

| Article                                                         | Description                                  |
| --------------------------------------------------------------- | -------------------------------------------- |
| [LightRAG Algorithm](docs/deep-dives/lightrag-algorithm.md)     | Core algorithm: extraction, graph, retrieval |
| [Query Modes](docs/deep-dives/query-modes.md)                   | 6 modes explained with trade-offs            |
| [Entity Normalization](docs/deep-dives/entity-normalization.md) | Deduplication and description merging        |
| [Gleaning](docs/deep-dives/gleaning.md)                         | Multi-pass extraction for completeness       |
| [Community Detection](docs/deep-dives/community-detection.md)   | Louvain clustering for global queries        |
| [Chunking Strategies](docs/deep-dives/chunking-strategies.md)   | Token-based segmentation with overlap        |
| [Embedding Models](docs/deep-dives/embedding-models.md)         | Model selection and dimension trade-offs     |
| [Graph Storage](docs/deep-dives/graph-storage.md)               | Apache AGE property graph backend            |
| [Vector Storage](docs/deep-dives/vector-storage.md)             | pgvector HNSW indexing and search            |
| [PDF Processing](docs/deep-dives/pdf-processing.md)             | Text/Vision/Hybrid extraction pipeline       |
| [Cost Tracking](docs/deep-dives/cost-tracking.md)               | LLM cost monitoring per operation            |
| [Pipeline Progress](docs/deep-dives/pipeline-progress.md)       | Real-time progress tracking                  |

### 📊 Comparisons

| Comparison                                                     | Key Insights                       |
| -------------------------------------------------------------- | ---------------------------------- |
| [vs LightRAG (Python)](docs/comparisons/vs-lightrag-python.md) | Performance and design differences |
| [vs GraphRAG](docs/comparisons/vs-graphrag.md)                 | Microsoft's approach comparison    |
| [vs Traditional RAG](docs/comparisons/vs-traditional-rag.md)   | Why graphs matter                  |

### API Reference

| API                                                    | Description              |
| ------------------------------------------------------ | ------------------------ |
| [REST API](docs/api-reference/rest-api.md)             | HTTP endpoints           |
| [Extended API](docs/api-reference/extended-api.md)     | Advanced API features    |

### Operations (Production)

| Guide                                                           | Description            |
| --------------------------------------------------------------- | ---------------------- |
| [Deployment](docs/operations/deployment.md)                     | Production deployment  |
| [Configuration](docs/operations/configuration.md)               | All config options     |
| [Monitoring](docs/operations/monitoring.md)                     | Observability setup    |
| [Performance Tuning](docs/operations/performance-tuning.md)     | Optimization guide     |

### 🐛 Troubleshooting

| Guide                                                    | Description                  |
| -------------------------------------------------------- | ---------------------------- |
| [Common Issues](docs/troubleshooting/common-issues.md)   | Debugging guide              |
| [PDF Extraction](docs/troubleshooting/pdf-extraction.md) | PDF-specific troubleshooting |

### 🔗 Integrations

| Integration                                           | Description                          |
| ----------------------------------------------------- | ------------------------------------ |
| [OpenWebUI](docs/integrations/open-webui.md)          | Chat interface with Ollama emulation |
| [LangChain](docs/integrations/langchain.md)           | Retriever and agent integration      |
| [Custom Clients](docs/integrations/custom-clients.md) | Python, TypeScript, Rust, Go clients |

### 📓 More Resources

- [FAQ](docs/faq.md) - Frequently asked questions
- [Cookbook](docs/cookbook.md) - Practical recipes
- [Security](docs/security/) - Security best practices

---

## Development

### Building and Testing

```bash
# Build backend
cd edgequake && cargo build --release

# Run tests
cargo test

# Lint and format
cargo clippy
cargo fmt

# Build frontend
cd edgequake_webui
bun run build
```

### Make Commands

EdgeQuake uses a unified Makefile for all development tasks:

```bash
# Full development stack
make dev              # Start all services (PostgreSQL + Backend + Frontend)
make dev-bg           # Start in background (for agents/automation)
make dev-memory       # Start with in-memory storage (testing only)
make stop             # Stop all services
make status           # Check service status

# Backend only
make backend-dev      # Run backend with PostgreSQL
make backend-memory   # Run backend with in-memory storage
make backend-bg       # Run backend in background
make backend-test     # Run backend tests

# Frontend only
make frontend-dev     # Start frontend dev server
make frontend-build   # Build frontend for production

# Database
make db-start         # Start PostgreSQL container
make db-stop          # Stop PostgreSQL container
make db-wait          # Wait for database to be ready

# Quality checks
make test             # Run all tests
make lint             # Lint all code
make format           # Format all code
make clean            # Clean build artifacts
```

### Agent Workflow

EdgeQuake development follows a **Specification-Driven Development** approach using the `edgecode` SOTA coding agent.

- **AGENTS.md**: Comprehensive agent guidelines and workflow
- **specs/**: All development specifications
- **OODA Loop**: Iterative development cycles (Observe, Orient, Decide, Act)

See [AGENTS.md](AGENTS.md) for detailed agent workflow documentation.

---

## Contributing

EdgeQuake is developed using the **edgecode** SOTA coding agent created by **Raphaël MANSUY**. The project follows a **Specification-Driven Development** approach where all changes are specified in the `specs/` directory before implementation.

**Current Status**: `edgecode` is not yet public but will be released soon.

**For now, contributions should go through Raphaël MANSUY directly:**

- **GitHub Issues**: Report bugs and request features
- **GitHub Discussions**: Ask questions and share ideas
- **Direct Contact**: For major contributions, contact [@raphaelmansuy](https://github.com/raphaelmansuy)

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed contribution guidelines.

---

## Community & Support

### Code of Conduct

We are committed to providing a welcoming and inclusive environment. Please read our [Code of Conduct](CODE_OF_CONDUCT.md).

### Support Channels

- **GitHub Issues**: Bug reports and feature requests
- **GitHub Discussions**: Questions and community help
- **LinkedIn**: [@raphaelmansuy](https://www.linkedin.com/in/raphaelmansuy)
- **Twitter/X**: [@raphaelmansuy](https://twitter.com/raphaelmansuy)

### Founder

**Raphaël MANSUY** 🇫🇷 - 🇭🇰🇨🇳 — Permanent Resident of Hong Kong, building the future of intelligent document retrieval systems and context graph systems.

---

## License

Licensed under the Apache License, Version 2.0 (the "License").  
You may obtain a copy of the License at:

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the [LICENSE](LICENSE) file for the specific language governing permissions and limitations.

**Copyright © 2024-2026 Raphaël MANSUY**

---

## Acknowledgments

EdgeQuake is inspired by and builds upon the excellent work of:

- **LightRAG Research Paper** ([arxiv.org/abs/2410.05779](https://arxiv.org/abs/2410.05779)): We are grateful to the authors of the foundational LightRAG algorithm which powers the core knowledge graph extraction and retrieval capabilities in EdgeQuake. Their innovative approach to entity extraction, relationship mapping, and hybrid retrieval has been instrumental in our framework's design.

  **Special thanks to the LightRAG authors:**
  - [Zirui Guo](https://arxiv.org/search/cs?searchtype=author&query=Guo,+Z)
  - [Lianghao Xia](https://arxiv.org/search/cs?searchtype=author&query=Xia,+L)
  - [Yanhua Yu](https://arxiv.org/search/cs?searchtype=author&query=Yu,+Y)
  - [Tu Ao](https://arxiv.org/search/cs?searchtype=author&query=Ao,+T)
  - [Chao Huang](https://arxiv.org/search/cs?searchtype=author&query=Huang,+C)

- **GraphRAG** ([arxiv.org/abs/2404.16130](https://arxiv.org/abs/2404.16130)): Microsoft's "From Local to Global" knowledge graph approach to query-focused summarization.
  - [Shuai Wang](https://www.microsoft.com/en-us/research/people/shuaiw/)
  - [Yingqiang Ge](https://www.microsoft.com/en-us/research/people/yinge/)
  - [Ying Shen](https://www.microsoft.com/en-us/research/people/yingshen/)
  - [Jianfeng Gao](https://www.microsoft.com/en-us/research/people/jfgao/)
  - [Xiaodong Liu](https://www.microsoft.com/en-us/research/people/xiaodl/)
  - [Yelong Shen](https://www.microsoft.com/en-us/research/people/yelongshen/)
  - [Jianfeng Wang](https://www.microsoft.com/en-us/research/people/jianfw/)
  - [Ming Zhou](https://www.microsoft.com/en-us/research/people/zhou/)
- **Rust Community**: For the amazing async ecosystem (Tokio, Axum, SQLx) that enables EdgeQuake's high performance
- **React Community**: For React 19 and the modern frontend stack that powers our interactive UI

---

## Quick Links

| Resource              | URL                                                                              |
| --------------------- | -------------------------------------------------------------------------------- |
| 📚 Full Documentation | [docs/README.md](docs/README.md)                                                 |
| 🚀 Quick Start Guide  | [docs/getting-started/quick-start.md](docs/getting-started/quick-start.md)       |
| 🔧 Agent Workflow     | [AGENTS.md](AGENTS.md)                                                           |
| 🤝 Contributing       | [CONTRIBUTING.md](CONTRIBUTING.md)                                               |
| 📜 Code of Conduct    | [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)                                         |
| 📄 License            | [LICENSE](LICENSE)                                                               |
| 🐛 Report Issues      | [GitHub Issues](https://github.com/raphaelmansuy/edgequake/issues)               |
| 💬 Discussions        | [GitHub Discussions](https://github.com/raphaelmansuy/edgequake/discussions)     |
| 🌐 Repository         | [github.com/raphaelmansuy/edgequake](https://github.com/raphaelmansuy/edgequake) |

---

**Ready to build intelligent document retrieval?** [Get started now!](docs/getting-started/quick-start.md)

