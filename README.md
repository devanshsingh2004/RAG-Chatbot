# RAGChat 🧠

Context-aware AI. Zero hallucinations. Real answers.

RAGChat is a lightweight, full-stack Retrieval-Augmented Generation (RAG) chatbot that combines Large Language Models with a vector-based retrieval pipeline to deliver accurate, grounded, and domain-aware responses from your own documents.

Unlike generic LLM chatbots, RAGChat retrieves relevant context from a vector database before generating answers — ensuring high precision, low hallucination, and real-world reliability.

---
## ✨ Features

Document ingestion — upload PDF, DOCX, HTML files

Semantic search — vector similarity retrieval using ChromaDB

Context-aware chat — history-aware multi-turn conversations

Low-hallucination responses — answers grounded in retrieved data

Session memory — persistent chat history using SQLite

Model switcher — GPT-4o & GPT-4o-mini support

Clean UI — Streamlit chat interface + sidebar controls

Document management — list and delete indexed files

---
##  🏗 Architecture
```java
User (Streamlit UI)
        |
        v
     FastAPI (REST APIs)
        |
        |── LangChain RAG Pipeline
        |       |
        |       ├── ChromaDB (Vector Store)
        |       |
        |       └── OpenAI LLM (Generator)
        |
        └── SQLite (Sessions + Chat History + Document Metadata)
```
---
## 🛠 Tech Stack
| Layer        | Stack                                                                                           |
|--------------|-------------------------------------------------------------------------------------------------|
| Front‑end    | Streamlit                                                                                       |
| Back‑end     | FastAPI · Python                                                                                |
| LLM Orchestration| LangChain                                                                                   |
| Vector DB    | ChromaDB                                                                                        |
| Database     | SQLite                                                                                          |
| LLM          | OpenAI (GPT-4o, GPT-4o-mini)                                                                    |

---
## 🚀 Quick Start

```bash
1. Clone
git clone https://github.com/your-username/RAGChat.git
cd RAGChat

2. Install dependencies
pip install -r requirements.txt

3. Set environment variable
export OPENAI_API_KEY=your_api_key
# Windows: set OPENAI_API_KEY=your_api_key

4. Run backend (FastAPI)
uvicorn main:app --reload

5. Run frontend (Streamlit)
streamlit run streamlit_app.py

```

Backend: http://127.0.0.1:8000
UI: http://localhost:8501

---
## 🧠 How It Works

1) Upload document → chunked + embedded + stored in ChromaDB
3) Ask question → query embedded and matched via semantic search
4) Retrieve context → most relevant chunks selected
5) Generate answer → LLM synthesizes grounded response
6) Store session → chat history saved in SQLite
This dual-stage retriever + generator pipeline ensures answers are fluent and factual.

---
## 📈 Impact

Eliminated hallucinations common in plain LLM setups

Reduced manual research effort through instant semantic retrieval

Improved response accuracy and decision-making speed

Enabled real multi-turn, context-aware conversations

---
## 💡 Why RAGChat?

### Traditional LLMs:

Rely only on pre-trained knowledge

Cannot access private or up-to-date data

Frequently hallucinate

### RAGChat:

Retrieves real context from your documents

Grounds every answer in external knowledge

Delivers enterprise-grade reliability

### This is the same architecture used in:

Internal company knowledge bots

Legal AI systems

Research assistants

Enterprise search platforms

---
## 🔮 Roadmap

Authentication (JWT / OAuth)

Hybrid search (BM25 + vectors)

Re-ranking

Streaming responses

Role-based document access

Dockerization


---
# 👤 Author

Devansh Singh
Backend & AI Systems Engineer
RAG · LLM Infrastructure · Distributed Systems
