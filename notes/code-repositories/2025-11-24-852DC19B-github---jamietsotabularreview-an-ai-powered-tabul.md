---
title: "GitHub - jamietso/Tabular_Review: An AI-powered tabular review tool for legal professionals. Ingest "
url: https://github.com/jamietso/Tabular_Review
tags: [programming, AI/ML, framework]
category: Code Repository
date: 2025-11-24
id: 852DC19B-6894-4186-906F-11749FC7007A
created: 2025-11-24T08:49:42Z
modified: 2025-11-24T08:49:42Z
---
# GitHub - jamietso/Tabular_Review: An AI-powered tabular review tool for legal professionals. Ingest 

## Summary

An AI-powered tabular review tool for legal professionals. Ingest unstructured documents, define dynamic extraction columns, and query your data with an integrated analyst chat.

**Category:** `Code Repository`  

**Tags:** `programming` `AI/ML` `framework`

**Source:** [https://github.com/jamietso/Tabular_Review](https://github.com/jamietso/Tabular_Review)

---

## Content

Repository: jamietso/Tabular_Review
Description: An AI-powered tabular review tool for legal professionals. Ingest unstructured documents, define dynamic extraction columns, and query your data with an integrated analyst chat.

⭐ Stars: 56
Language: TypeScript

README:


# Tabular Review for Lawyers

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![React](https://img.shields.io/badge/framework-React-61DAFB.svg)
![AI](https://img.shields.io/badge/AI-Google%20Gemini-8E75B2.svg)

An AI-powered document review workspace that transforms unstructured legal contracts into structured, queryable datasets. Designed for legal professionals, auditors, and procurement teams to accelerate due diligence and contract analysis.

## 🚀 Features

- **AI-Powered Extraction**: Automatically extract key clauses, dates, amounts, and entities from PDFs using Google Gemini 2.5 Pro / 3.0.
- **High-Fidelity Conversion**: Uses **Docling** (running locally) to convert PDFs and DOCX files to clean Markdown text, preserving formatting and structure without hallucination.
- **Dynamic Schema**: Define columns with natural language prompts (e.g., "What is the governing law?").
- **Verification & Citations**: Click any extracted cell to view the exact source quote highlighted in the original document.
- **Spreadsheet Interface**: A high-density, Excel-like grid for managing bulk document reviews.
- **Integrated Chat Analyst**: Ask questions across your entire dataset (e.g., "Which contract has the most favorable MFN clause?").

## 🎬 Demo

https://github.com/user-attachments/assets/b63026d8-3df6-48a8-bb4b-eb8f24d3a1ca

## 🛠 Tech Stack

- **Frontend**: React 19, TypeScript, Tailwind CSS
- **AI Integration**: Google GenAI SDK (Gemini 2.5 Flash, 2.5 Pro, 3.0 Pro)

## 📦 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/tabular-review.git
cd tabular-review
```

### 2. Setup Frontend
Install Node dependencies:
```bash
pnpm install
```

Create a `.env.local` file in the root directory for your Google API Key:
```env
VITE_GEMINI_API_KEY=your_google_api_key_here
```

### 3. Setup Backend (Docling)
The backend is required for document conversion.

```bash
cd server
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 4. Run
Start the backend (in one terminal):
```bash
cd server
source venv/bin/activate
python main.py
```

Start the frontend (in another terminal):
```bash
pnpm dev
```

## 🛡 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Disclaimer**: This tool is an AI assistant and should not be used as a substitute for professional legal advice. Always verify AI-generated results against the original documents.

