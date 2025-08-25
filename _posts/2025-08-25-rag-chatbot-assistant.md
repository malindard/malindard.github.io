---
layout: post
title: Ask Your Docs – RAG Chatbot Powered Document Q&A
date: 2025-08-25
excerpt: "A hybrid-retrieval chatbot that answers questions from user-uploaded documents using FAISS, BM25, Groq, and Streamlit."
project: true
tags:
- RAG
- Streamlit
- FAISS
- BM25
- Groq
- Hybrid Retrieval
comments: true
---

# Introduction

The **Ask Your Docs** is a portfolio project I built to explore document-grounded Q&A using **retrieval augmented generation (RAG)**.  
The goal: allow users to upload their own documents (PDF/Markdown/TXT) and query them interactively.  
Every answer comes **only from the documents**, so no hallucination, no guessing and with optional inline citations.

It’s built with **hybrid retrieval** (dense + sparse search) and uses **Groq-hosted LLMs** for low-latency response.  
Deployed with **Streamlit** for UI and **FastAPI** for backend APIs.

[Live Demo →](https://rag-chatbot-assistant.streamlit.app/)

---

# Motivation

I wanted to solve a common pain:  
> "I have a pile of college notes — can I just *ask questions* instead of searching manually?"

Rather than relying on generic chatbots, this app enforces **strict grounding**:  
- If an answer isn’t in the docs, it says so  
- Optional citations make answers auditable  
- Hybrid retrieval improves recall (not just semantic similarity)  

This was also a way to practice **retriever design (BM25 + FAISS)**, **Groq inference**, and **Streamlit UX**.

---

# Architecture

```mermaid
flowchart LR
    A[User Uploads Docs] --> B[Document Processor: chunk & clean]
    B --> C[Vector Store (FAISS)]
    B --> D[BM25 Retriever]
    C --> E[Dense Retrieval]
    D --> F[Sparse Retrieval]
    E --> G[Hybrid Fusion (RRF)]
    F --> G
    G --> H[RAG Engine]
    H --> I[Groq LLM (Answer Gen)]
    I --> J[Streamlit / FastAPI Response]
```

- **Dense**: FAISS + embeddings (`BAAI/bge-small-en-v1.5`)  
- **Sparse**: BM25 keyword retriever  
- **Hybrid**: Reciprocal Rank Fusion (RRF) combines both  

---

# Tools & Models

| Component     | Description |
|---------------|-------------|
| **FastEmbed** | Lightweight embeddings for FAISS |
| **FAISS** | Dense vector search |
| **BM25** | Sparse keyword search |
| **RRF Fusion** | Combines dense & sparse rankings |
| **Groq LLM (Llama-3.1)** | Answer generation |
| **Streamlit** | Chat UI |
| **FastAPI** | Backend REST API |
| **PyPDF2 / Regex** | Document parsing & cleaning |

---

# Workflow

```text
1. User uploads PDFs/Markdown/TXT
2. Documents are chunked and cleaned
3. FAISS creates dense embeddings
4. BM25 indexes sparse keywords
5. Queries run through hybrid retrieval (RRF)
6. Top results passed into Groq LLM
7. Answer generated (with or without citations)
```

---

# Challenges

- ⚖️ **Hybrid Tuning**: balancing dense vs sparse scores to avoid irrelevant hits  
- ⚡ **Latency**: free-tier LLM endpoints (OpenRouter) often slow or rate-limited — Groq solved this with instant inference  
- 📚 **Citations UX**: optional toggle for cleaner answers  
- 🗂️ **Deployment**: managing per-session uploads (reset after refresh vs persistent index)  

---

# Key Learnings

- **Hybrid beats single retriever** → FAISS alone missed keyword-heavy queries, BM25 alone missed semantic matches.  
- **User trust = grounding** → forcing “I don’t know” when context missing avoids hallucination.  
- **UX matters** → Streaming responses and citations toggle make the app feel polished.  
- **Extensibility** → RAG design made it easy to swap LLM backends (OpenRouter → Groq).  

---

# Result

- 🧠 Hybrid RAG pipeline with FAISS + BM25 + RRF  
- ⚡ Integrated **Groq LLM** for fast inference  
- 📑 User document upload (multi-file supported)  
- 💬 Streamlit UI with streaming responses & citation toggle  
- 🧪 REST API with FastAPI for external integration  

---

# Future Plans

- Multi-user session storage (Supabase or Postgres backend)  
- Expand file support (DOCX, XLSX)  
- Domain presets (HR assistant, Legal assistant, Academic papers)  
- Dashboard for query analytics (what docs are being asked most)  

---
[View on GitHub →](https://github.com/malindard/rag-chatbot-assistant)
---

# Related Projects

**👉 Also check out:**  
- [LangChain AI News Generator](https://malindard.github.io//ai-news-generator/) – my other project using **multi-agent chains** for research & writing.  

> "Your documents, your answers — grounded and reliable."
