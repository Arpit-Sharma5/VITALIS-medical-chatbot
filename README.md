# 🩺 VITALIS — Medical Chatbot

An AI-powered medical chatbot that provides concise, reference-backed answers to health-related questions. Built with **Flask**, **LangChain**, **Google Gemini**, and **Pinecone** vector search — VITALIS retrieves relevant passages from a medical textbook and generates clear, focused responses using Retrieval-Augmented Generation (RAG).

> **⚠️ Disclaimer:** VITALIS is designed for **educational purposes only**. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider.

---

## ✨ Features

- **RAG Pipeline** — Retrieves relevant context from a medical PDF using Pinecone vector search before generating answers via Google Gemini.
- **HuggingFace Embeddings** — Uses `sentence-transformers/all-MiniLM-L6-v2` (384-dim) for efficient semantic search.
- **Polished UI** — A premium dark-themed chat interface with ambient video background, typing animations, and suggestion cards.
- **Dockerized** — Includes a Dockerfile for containerized deployment.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Flask (Python) |
| LLM | Google Gemini (`gemini-2.5-flash`) via LangChain |
| Embeddings | HuggingFace `all-MiniLM-L6-v2` |
| Vector DB | Pinecone (Serverless) |
| Frontend | HTML, CSS, Vanilla JS |
| Orchestration | LangChain (RAG chain) |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- A [Pinecone](https://www.pinecone.io/) account & API key
- A [Google AI Studio](https://aistudio.google.com/) API key (for Gemini)

### Installation

```bash
# Clone the repository
git clone https://github.com/Arpit-Sharma5/VITALIS-medical-chatbot.git
cd VITALIS-medical-chatbot

# Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Configuration

Create a `.env` file in the project root (use `.env.example` as a template):

```
PINECONE_API_KEY=your_pinecone_api_key
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-2.5-flash
```

### Index the Medical Data

Place your medical PDF in the `data/` directory, then run:

```bash
python store_index.py
```

This will extract text, generate embeddings, and upsert them into your Pinecone index.

### Run the App

```bash
python app.py
```
