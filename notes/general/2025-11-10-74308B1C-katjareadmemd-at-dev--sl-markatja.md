---
title: Katja/README.md at dev · SL-Mar/Katja
url: https://github.com/SL-Mar/Katja/blob/dev/README.md
tags: [Chat, Platform, SLMs, Legal]
category: 
date: 2025-11-10
id: 74308B1C-E95E-4FC5-8953-AFB446765B5B
created: 2025-11-10T13:16:36Z
modified: 2025-11-10T13:16:36Z
---
# Katja/README.md at dev · SL-Mar/Katja

## Summary

Multi-Mode AI Chat Platform with Specialized LLMs. Contribute to SL-Mar/Katja development by creating an account on GitHub.

**Tags:** `Chat` `Platform` `SLMs` `Legal`

**Source:** [https://github.com/SL-Mar/Katja/blob/dev/README.md](https://github.com/SL-Mar/Katja/blob/dev/README.md)

---

## Content

Repository: SL-Mar/Katja
Description: Multi-Mode AI Chat Platform with Specialized LLMs

Topics: local-first

⭐ Stars: 0
Language: TypeScript

README:

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

# Katja — Multi-Mode AI Chat Platform with Specialized LLMs

**Katja** is a comprehensive AI chat platform featuring **5 specialized modes**: language learning with grammar correction, general chat, legal reasoning (Saul-7B), medical queries (Meditron/BioMistral), and a terminal-style console for monitoring all interactions. Built with local-first privacy using Ollama, with optional cloud fallback (OpenAI GPT-4o-mini). All data stays on your machine by default.

---

## Features

### 🎓 Language Learning Mode
* **Multi-language support** - 7 European languages (Slovene, German, Italian, Croatian, French, English, Portuguese)
* **Real-time grammar correction** - Instant feedback with explanations in target language
* **Spaced repetition** - SM-2 algorithm for reviewing grammar patterns
* **Export corrections** - Save grammar corrections as JSON
* **Auto-clear on language switch** - Fresh conversation when switching languages

### 💬 General Chat Mode
* **14+ LLM models** - Choose from Llama, Qwen, GLM4, Gemma, and more
* **LaTeX rendering** - Math and technical formulas rendered beautifully (inline `$...$` or display `$$...$$`)
* **Model switching** - Live dropdown selector for all available Ollama models
* **Structured responses** - Optimized system prompts for technical and academic queries
* **GPT-4o-mini support** - Selectable OpenAI model with automatic routing

### ⚖️ Legal Chat Mode
* **Saul-7B specialized model** - Fine-tuned for English law, contracts, torts, and legal reasoning
* **LaTeX legal citations** - Properly formatted case citations and legal principles
* **Precedent explanations** - Detailed case law analysis
* **Legal doctrine support** - Equity, trusts, negligence, contract law

### 🏥 Maritime Medical Chat Mode
* **Meditron & BioMistral** - Medical-domain fine-tuned models
* **Maritime medical focus** - Designed for ship's officers managing medical care without doctors
* **Examination guidance** - Systematic patient assessment (vital signs, SAMPLE history, physical exam)
* **Telemedicine preparation** - Organize observations for shore-based physician consultations
* **IMGS protocol support** - International Medical Guide for Ships compliance
* **No diagnosis/treatment** - Emphasizes observation and communication, not prescription

### 💻 Console Mode
* **Terminal-style interface** - Hacker aesthetic with green monospace text
* **Multi-session monitoring** - View conversations from all modules in one place
* **Real-time updates** - Auto-refresh every 3 seconds
* **Session filtering** - Filter by language learning, general, legal, or medical chat
* **Model tracking** - See which model was used for each response
* **Timestamp tracking** - Full conversation history with precise timestamps

### Core Features
* **Local-first inference** - Uses Ollama for privacy-preserving AI (no cloud API required)
* **Cloud fallback** - Automatic OpenAI GPT-4o-mini fallback when selected or local models unavailable
* **Conversation memory** - SQLite database with WAL mode for persistent chat history
* **Session management** - Multiple conversation sessions with isolated history
* **Customizable prompts** - Edit system prompts for each mode via settings page ⭐ NEW
* **CORS security** - Configurable allowed origins for API access

---

## ⚠️ Important Disclaimers

### Legal Chat
The Legal Chat mode is for **educational and research purposes only**. It is not a substitute for professional legal advice. Do not rely on responses for actual legal matters. Always consult a qualified attorney for legal questions.

### Maritime Medical Chat
The Maritime Medical Chat mode is designed for **ship's officers managing medical care on vessels without doctors**. This tool assists with patient examination and observation to prepare for telemedicine consultations with shore-based physicians.

**CRITICAL LIMITATIONS**:
- ⚠️ **NO DIAGNOSIS OR TREATMENT**: Ship's medical officers are NOT authorized to diagnose conditions or initiate treatments (except immediate life-saving measures)
- ⚠️ **PHYSICIAN AUTHORIZATION REQUIRED**: All medical interventions beyond basic first aid must be authorized by a shore-based physician via radio medical advice (TMAS - Telemedical Assistance Service)
- ⚠️ **EXAMINATION ONLY**: This tool focuses on gathering complete, accurate information for remote physicians

This is NOT a substitute for professional medical advice. Always contact a shore-based physician for medical guidance.

---

## Philosophy

Katja is a **local-first, privacy-focused** AI chat platform:

* **Privacy**: All LLM inference happens locally via Ollama by default. No data sent to third parties unless cloud fallback is used.
* **Offline-capable**: Works without internet connection (after initial model download).
* **Transparent**: Open source backend and frontend. No telemetry.
* **Flexible**: Choose between local models (privacy) or cloud models (performance).
* **Minimalist**: Simple FastAPI backend + Next.js frontend.

---

## Quick Start Guide

### 1. 🎓 Language Learning Mode
**URL**: http://localhost:3000 (default landing page)

Grammar corrections in 7 European languages with instant feedback:
- Practice conversational skills in any supported language
- Get real-time grammar corrections with explanations
- Review corrections using spaced repetition algorithm
- Export corrections as JSON for external study tools

### 2. 💬 General Chat Mode
**URL**: http://localhost:3000/chat

General-purpose AI conversations with 14+ models:
- Technical discussions with LaTeX math rendering
- Academic research assistance
- Creative writing and brainstorming
- General knowledge questions

**Example queries**:
- *"What is Bayes' theorem and how is it used in statistics?"*
- *"Explain quantum entanglement in simple terms"*
- *"Write a Python function to calculate Fibonacci numbers"*

### 3. ⚖️ Legal Chat Mode
**URL**: http://localhost:3000/legal-chat

English law queries using Saul-7B specialized legal model:
- Case law analysis and precedent research
- Contract law, torts, equity, trusts
- Legal doctrine explanations
- Properly formatted legal citations

**Example queries**:
- *"What is the leading case in negligence?"*
- *"Explain the doctrine of consideration in contract law"*
- *"Is there an obligation of good faith in insurance law?"*

### 4. 🏥 Maritime Medical Chat Mode
**URL**: http://localhost:3000/medical-chat

Maritime medical guidance for ship's officers using Meditron and BioMistral:
- Systematic patient examination protocols (vital signs, SAMPLE history, physical exam)
- Preparing observations for shore-based physician consultation
- Understanding medical terminology and observations
- IMGS (International Medical Guide for Ships) protocol support

**Example queries**:
- *"How should I perform a complete physical examination on a crew member with chest pain?"*
- *"What vital signs should I collect and how do I document them for the ship's doctor consultation?"*
- *"Guide me through assessing a patient's neurological status"*

**⚠️ CRITICAL**: This mode does NOT provide diagnoses or treatment recommendations. It helps you examine patients and communicate findings to shore-based physicians.

### 5. 💻 Console Mode
**URL**: http://localhost:3000/console

Terminal-style monitoring interface for all LLM interactions:
- View conversation history across all modules
- Filter by session type (language, general, legal, medical)
- Track which models were used for each response
- Auto-refresh every 3 seconds
- Export logs for analysis

---

## Supported Languages

* 🇸🇮 Slovene
* 🇩🇪 German
* 🇮🇹 Italian
* 🇭🇷 Croatian
* 🇫🇷 French
* 🇬🇧 English
* 🇵🇹 Portuguese

Switch languages via flag buttons in the chat interface.

---

## Prerequisites

1. **Ollama** - Install from [ollama.ai](https://ollama.ai) for local inference
2. **Pull models** - Recommended models:
   ```bash
   # General-purpose chat
   ollama pull llama3:8b-instruct-q4_K_M

   # English law (Saul 7B)
   ollama pull adrienbrault/saul-instruct-v1:Q4_K_M

   # Medical (Meditron)
   ollama pull meditron-7b

   # Biomedical (BioMistral)
   ollama pull biomistral-7b
   ```
3. **Node.js** - For frontend (v18+ recommended)
4. **Python 3.10+** - For backend
5. **(Optional) OpenAI API Key** - For cloud fallback when local models unavailable

---

## Getting Started

### Quick Start (Linux)

```bash
git clone https://github.com/SL-MAR/katja.git
cd katja
chmod +x launch-katja.sh
./launch-katja.sh
```

This launches:
* **🎓 Language Learning**: [http://localhost:3000](http://localhost:3000)
* **💬 General Chat**: [http://localhost:3000/chat](http://localhost:3000/chat)
* **⚖️ Legal Chat**: [http://localhost:3000/legal-chat](http://localhost:3000/legal-chat)
* **🏥 Maritime Medical Chat**: [http://localhost:3000/medical-chat](http://localhost:3000/medical-chat)
* **💻 Console**: [http://localhost:3000/console](http://localhost:3000/console)
* **⚙️ Settings**: [http://localhost:3000/settings](http://localhost:3000/settings) ⭐ NEW
* **Backend API**: [http://localhost:8000](http://localhost:8000)
* **API Docs**: [http://localhost:8000/docs](http://localhost:8000/docs)

### Manual Setup

**Backend:**

```bash
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Copy environment template
cp .env.example .env

# Start backend
uvicorn main:app --reload
```

**Frontend:**

```bash
cd frontend
npm install
npm run dev
```

---

## Configuration

### Backend Configuration

The backend uses environment variables. Copy `.env.example` to `.env` and adjust:

```bash
# LLM Provider (local = Ollama, openai = fallback)
LLM_PROVIDER=local

# Ollama settings
OLLAMA_MODEL=llama3:8b-instruct-q4_K_M
OLLAMA_BASE_URL=http://localhost:11434

# Optional: OpenAI fallback (if Ollama unavailable)
# OPENAI_API_KEY=your_api_key_here

# CORS origins (comma-separated)
ALLOWED_ORIGINS=http://localhost:3000,http://localhost:3001,http://localhost:5173
```

**Switching models**: Use the dropdown in each chat mode's UI or edit `OLLAMA_MODEL` in `.env`.

**Fallback behavior**: If Ollama is unavailable and `OPENAI_API_KEY` is set, the backend will automatically fall back to OpenAI's API.

### System Prompt Customization ⭐ NEW

**Settings Page**: [http://localhost:3000/settings](http://localhost:3000/settings)

Each chat mode has a customizable system prompt that defines the AI assistant's behavior:

- **Language Learning**: Conversational teacher with grammar correction
- **Maritime Medical**: Ship's officer examination guidance (no diagnosis/treatment)
- **Legal**: English common law specialist
- **General**: Technical and academic assistant

**Features**:
- ✏️ **Live editor** - Edit prompts in a Monaco-style textarea
- 💾 **Browser storage** - Changes saved to localStorage (persist across sessions)
- 🔄 **Reset to defaults** - Restore original prompts anytime
- 📋 **Preview** - See formatted prompt before saving
- ⚡ **Instant effect** - Changes apply on next message

**Customization tips**:
- Adjust tone (formal/casual)
- Add domain-specific knowledge
- Change output format preferences
- Include LaTeX notation guidance: `$inline$` or `$$display$$`

---

## How It Works

### Architecture

```
┌─────────────┐      ┌──────────────┐      ┌─────────────┐
│  Next.js    │─────▶│  FastAPI     │─────▶│   Ollama    │
│  Frontend   │◀─────│  Backend     │◀─────│   (Local)   │
│ (Port 3001) │      │ (Port 8000)  │      │ (Port 11434)│
└─────────────┘      └──────────────┘      └─────────────┘
                            │
                            ▼
                     ┌──────────────┐
                     │   SQLite     │
                     │   Database   │
                     └──────────────┘
```

### LLM Inference Flow

1. **User types message** → Frontend sends to `/katja/chat`
2. **Backend receives request** → Loads conversation history from SQLite
3. **Prompt construction** → Builds system prompt with grammar patterns + conversation context
4. **Ollama inference** → Sends prompt to local Ollama instance (`http://localhost:11434`)
5. **JSON parsing** → Extracts structured response (reply + grammar correction)
6. **Database storage** → Saves conversation + corrections to SQLite
7. **Response** → Returns to frontend with grammar feedback

**JSON Format** enforced via Ollama's `format: json` parameter:
```json
{
  "reply": "Conversational response in target language",
  "correction": {
    "corrected": "Corrected version of user's text",
    "explanation": "Grammar explanation",
    "pattern": "Grammar pattern ID (if applicable)",
    "severity": "minor|major|critical"
  }
}
```

---

## Technology Stack

**Frontend:**
* Next.js (React framework)
* TypeScript
* Tailwind CSS
* FontAwesome icons
* **react-markdown** + **KaTeX** (LaTeX rendering) ⭐ NEW
* **remark-math** + **rehype-katex** (Math typesetting) ⭐ NEW

**Backend:**
* FastAPI (Python web framework)
* SQLite with WAL mode (Write-Ahead Logging)
* Pydantic v2 (validation)
* SlowAPI (rate limiting)

**LLM:**
* **Ollama** (local inference) - Primary
* **OpenAI GPT-4o-mini** (cloud fallback) - Optional
* Supports 14+ models including:
  - `llama3:8b-instruct-q4_K_M` (general, 4.9GB)
  - `adrienbrault/saul-instruct-v1:Q4_K_M` (legal, 4.1GB) ⭐
  - `meditron-7b` (maritime medical, 4.1GB) ⭐
  - `biomistral-7b` (biomedical, 4.1GB) ⭐
  - `glm4`, `qwen2:7b`, `gemma3:12b` (multi-lingual)
* **Response length**: 4096 tokens (configurable)
* **Temperature**: 0.0 (deterministic for medical/legal accuracy)

---

## Repository Structure

```
katja/
├── backend/
│   ├── core/
│   │   ├── database.py          # SQLite schema & connection
│   │   ├── db_operations.py     # CRUD operations
│   │   ├── llm_router.py        # Ollama + OpenAI integration
│   │   └── spaced_repetition.py # SM-2 algorithm
│   ├── flows/
│   │   └── teacher_flow.py      # Main conversation logic
│   ├── routers/
│   │   ├── teacher.py           # Chat endpoint
│   │   ├── reviews.py           # Spaced repetition API
│   │   ├── analytics.py         # Progress tracking
│   │   └── system.py            # Model switching, logs
│   ├── data/                    # SQLite database (auto-created)
│   ├── .env.example             # Configuration template
│   └── requirements.txt
├── frontend/
│   ├── components/
│   │   ├── Header.tsx           # Navigation, model selector, action buttons
│   │   ├── ChatWindow.tsx       # Grammar learning conversation UI
│   │   ├── GenericChat.tsx      # Generic/legal/medical chat with LaTeX rendering
│   │   ├── GrammarPanel.tsx     # Grammar corrections with localized labels
│   │   └── InputBox.tsx         # User input with multilingual placeholders
│   ├── config/
│   │   └── systemPrompts.ts     # ⭐ Centralized system prompts for all modes
│   ├── pages/
│   │   ├── index.tsx            # 🎓 Language learning page (default)
│   │   ├── chat.tsx             # 💬 General chat page
│   │   ├── legal-chat.tsx       # ⚖️ Legal chat page (Saul-7B)
│   │   ├── medical-chat.tsx     # 🏥 Maritime medical chat page (Meditron/BioMistral)
│   │   ├── console.tsx          # 💻 Console log viewer
│   │   ├── settings.tsx         # ⚙️ System prompt editor ⭐ NEW
│   │   ├── reviews.tsx          # Spaced repetition UI
│   │   └── stats.tsx            # Analytics dashboard
│   ├── utils/
│   │   ├── api.ts               # API client functions
│   │   ├── languages.ts         # Language metadata and labels
│   │   └── promptLoader.ts      # ⭐ Load system prompts (custom or default)
│   └── public/
│       └── screenshots/         # UI screenshots for documentation
├── launch-katja.sh              # Launcher script
├── CHANGELOG.md                 # Version history
└── README.md
```

---

## Screenshots

### 1. Language Learning Mode
Multi-language grammar correction with real-time feedback in 7 European languages.

![Language Learning](./screenshots/katja1_language.png)

### 2. General Chat Mode
General-purpose AI conversations with model selection and structured responses.

![General Chat](./screenshots/katja2_genchat.png)

### 3. Medical Chat Mode
Specialized medical queries using Meditron and BioMistral models.

![Medical Chat](./screenshots/katja3_medchat.png)

### 4. Legal Chat Mode
English law queries using Saul-7B specialized legal model.

![Legal Chat](./screenshots/Katja4_Legalchat.png)

### 5. Console Mode
Terminal-style log viewer for monitoring all LLM interactions across modules.

![Console](./screenshots/katja5_console.png)

---

## API Endpoints

### Language Learning
* `POST /katja/chat` - Send message, receive grammar-corrected response
* `DELETE /katja/clear` - Clear conversation history for language learning

### General/Legal/Medical Chat
* `POST /katja/generic-chat` - Generic chat with any model (supports LaTeX)
* `DELETE /katja/generic-chat/clear` - Clear generic chat history

### Console & Monitoring
* `GET /katja/console/history?type=language` - Get language learning conversation history
* `GET /katja/console/history?type=general` - Get general/legal/medical chat history
* `GET /katja/system/logs` - Stream backend logs (real-time)

### Model Management
* `GET /katja/models` - List all available Ollama models
* `GET /katja/system/models` - List available models with metadata
* `POST /katja/system/models/select` - Switch active model

### Spaced Repetition
* `GET /katja/reviews/due` - Get corrections due for review
* `POST /katja/reviews/{correction_id}/review` - Submit review result

### Analytics
* `GET /katja/analytics/progress` - Learning progress stats

---

## Development

### Running Tests

```bash
cd backend
pytest
```

### Database Schema

SQLite database (`backend/data/katja.db`) auto-initializes with the following tables:

**Language Learning Tables:**
* `user_profile` - User sessions, language preferences, and statistics
* `conversation_history` - Language learning conversations with original and corrected text
* `grammar_corrections` - Corrections with spaced repetition metadata (SM-2 algorithm)
* `grammar_patterns` - Common grammar patterns for 7 languages (seed data)

**Multi-Mode Tables:**
* `generic_conversations` - Shared conversation history for General Chat, Legal Chat, and Medical Chat modes
  - Tracks `session_id`, `role`, `content`, `timestamp`, and `model_used`
  - Enables context memory across conversation turns
  - Queried by Console mode for monitoring

**Features:**
* **WAL mode enabled** - Write-Ahead Logging for better concurrency (multiple reads during writes)
* **Session isolation** - Each browser tab gets unique `session_id` stored in localStorage
* **Persistence** - Conversations survive page refreshes and browser restarts
* **Auto-initialization** - Tables created automatically on first startup

**Database location**: `/backend/data/katja.db` (auto-created, not tracked in git)

---

## Troubleshooting

**Backend won't start:**
* Check Ollama is running: `ollama list`
* Verify Python dependencies: `pip install -r requirements.txt`
* Check `.env` file exists (copy from `.env.example`)

**No grammar corrections:**
* Verify model supports JSON output (use `llama3:8b-instruct-q4_K_M`)
* Check backend logs in UI or `/tmp/katja-backend.log`

**Frontend errors:**
* Ensure backend is running on port 8000
* Check CORS settings in `.env` (add your frontend port)

---

## License

Apache License 2.0

You are free to use, modify, and redistribute this code. See [LICENSE](./LICENSE) for full terms.

---

## Citation

```
S.M.Laignel. (2025). Katja: A Multi-Mode AI Chat Platform with Specialized LLMs for Language Learning, Legal Reasoning, and Medical Queries.
GitHub Repository. https://github.com/SL-MAR/katja
```

