---
title: "GitHub - zhijiewong/ragviz: Graph RAG visualization platform with interactive knowledge graphs and real-time parameter tuning for local LLMs"
url: https://github.com/zhijiewong/ragviz
tags: [code, github, GraphRAG]
category: Code Repository
date: 2025-11-13
id: 4276EED6-3C68-4730-B6CF-04CA145195AF
created: 2025-11-13T20:57:47Z
modified: 2025-11-13T20:57:47Z
---
# GitHub - zhijiewong/ragviz: Graph RAG visualization platform with interactive knowledge graphs and real-time parameter tuning for local LLMs

## Summary

Graph RAG visualization platform with interactive knowledge graphs and real-time parameter tuning for local LLMs - zhijiewong/ragviz

**Category:** `Code Repository`  

**Tags:** `code` `github` `GraphRAG`

**Source:** [https://github.com/zhijiewong/ragviz](https://github.com/zhijiewong/ragviz)

---

## Content

Repository: zhijiewong/ragviz
Description: Graph RAG visualization platform with interactive knowledge graphs and real-time parameter tuning for local LLMs

Topics: fastapi, graph-neural-networks, graph-rag, knowledge-graph, knowledge-graphs, llm, local-llm, neo4j, nextjs, ollama, rag, retrieval-augmented-generation, vector-search, visualization

⭐ Stars: 0
Language: TypeScript

README:

# Graph RAG Visualization Platform

[![codecov](https://codecov.io/gh/yourusername/ragviz/branch/main/graph/badge.svg)](https://codecov.io/gh/yourusername/ragviz)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Node 18+](https://img.shields.io/badge/node-18+-green.svg)](https://nodejs.org/)

A developer-oriented Graph Retrieval-Augmented Generation (Graph RAG) visualization and parameter tuning platform. This tool combines knowledge graphs with vector retrieval to provide contextual support for local large language models (like Ollama or llama.cpp), enabling interactive document uploads, knowledge graph construction, and real-time parameter adjustments while visualizing their impact on answers and subgraph structures.

![RAGViz Demo](docs/demos/quick-start.gif)

*Upload documents, explore interactive knowledge graphs, and chat with your data using local LLMs*

## Features

### ⚙️ Real-time Parameter Tuning
Adjust retrieval and generation parameters instantly. See how Top K, similarity threshold, and temperature affect your results in real-time.

![Parameter Tuning](docs/demos/parameter-tuning.gif)

### Core Capabilities

- 📊 **Interactive Knowledge Graph Visualization** - Build and explore knowledge graphs with multiple layout algorithms and smooth animations
- 🔍 **Vector-Enhanced Retrieval** - Combine graph structure with semantic search using Neo4j vector indexing
- 🤖 **Local LLM Integration** - Works with Ollama, llama.cpp and other local language models
- 📄 **Multi-format Document Support** - Upload PDF, TXT and other document formats
- 🎯 **Hallucination Reduction** - Leverage structured knowledge graphs to improve answer accuracy
- 🔧 **Developer-Friendly** - Built for research and data science teams with debugging visualization

## Architecture

- **Frontend**: Next.js/React with interactive graph visualization
- **Backend**: FastAPI with RESTful APIs
- **Database**: Neo4j with HNSW vector indexing
- **LLM Integration**: Local model support (Ollama/llama.cpp)

## Quick Start

### Option 1: Cloud-Ready Setup (Recommended for Beginners) ☁️

Use Neo4j Aura's free tier - no local database installation needed!

1. **Create a free Neo4j Aura database** (takes 2 minutes):
   - Go to [https://neo4j.com/cloud/aura-free/](https://neo4j.com/cloud/aura-free/)
   - Sign up for a free account
   - Create a new AuraDB Free instance
   - Save your credentials (URI, username, password)

2. **Clone and configure**:
```bash
# Clone the repository
git clone https://github.com/zhijiewong/ragviz.git
cd ragviz

# Copy and configure environment variables
cp .env.example .env
# Edit .env and add your Neo4j Aura credentials:
# NEO4J_URI=neo4j+s://xxxxx.databases.neo4j.io
# NEO4J_USERNAME=neo4j
# NEO4J_PASSWORD=your_aura_password
```

3. **Install Ollama** (for local LLM):
```bash
# Visit https://ollama.ai/download
# After installation:
ollama pull qwen2.5:7b-instruct
```

4. **Run the application**:
```bash
# Backend
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload

# Frontend (new terminal)
cd frontend
npm install
npm run dev
```

5. **Access**: Open [http://localhost:3000](http://localhost:3000)

### Option 2: Docker Compose (All-in-One Local Setup) 🐳

```bash
# Clone the repository
git clone https://github.com/zhijiewong/ragviz.git
cd ragviz

# Start all services (Neo4j + Backend + Frontend)
docker-compose up -d

# Access the application
# Frontend: http://localhost:3000
# Neo4j Browser: http://localhost:7474
# Backend API: http://localhost:8000/docs
```

## Why Neo4j Aura? ☁️

Neo4j Aura Free tier is perfect for getting started with RAGViz:

- ✅ **Zero Setup** - No database installation required
- ✅ **Always Free** - Generous free tier for development and small projects
- ✅ **Cloud-Hosted** - Accessible from anywhere
- ✅ **Auto-Updates** - Always running the latest Neo4j version
- ✅ **Backups Included** - Automatic daily backups
- ✅ **Production-Ready** - Easy upgrade path when you scale

**Free Tier Limits**: Perfect for RAGViz development
- 200k nodes + 400k relationships
- Ideal for processing hundreds of documents
- More than enough for learning and prototyping

## Project Structure

```
ragviz/
├── frontend/           # Next.js frontend with Tailwind UI & Shadcn UI
│   ├── src/
│   │   ├── components/ # React components
│   │   ├── app/        # Next.js app router
│   │   └── lib/        # Utilities and API clients
├── backend/            # FastAPI backend
│   ├── app/
│   │   ├── api/        # API routes
│   │   ├── core/       # Configuration and settings
│   │   ├── services/   # Business logic
│   │   └── models/     # Data models
├── docker-compose.yml  # Container orchestration
├── START.md           # Quick start guide
├── README.md          # Project documentation
├── IMPLEMENTATION.md  # Technical implementation details
└── LICENSE            # Open source license
```

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
