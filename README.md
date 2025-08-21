# Multi-DOC Reading Chatbot using RAG and Streamlit

This repository contains a **Streamlit-based chatbot** that can read and answer questions from multiple documents (PDF, DOCX, TXT) using **Retrieval-Augmented Generation (RAG)** and **Mistral API**. Ideal for document-based Q&A and evaluation.

---

## 🚀 Features

- Upload **multiple documents** (PDF, DOCX, TXT) simultaneously
- Automatically **extract text and chunk documents**
- Compute **embeddings** with SentenceTransformers for semantic search
- Store and query chunks using **ChromaDB**
- Generate **contextual answers** via **Mistral API**
- Developer mode for **detailed evaluation metrics**
- Normal user mode for **clean chat interface**
- Optional **benchmark CSV evaluation**

---

## 📦 Installation

Install required Python packages:

```bash
pip install streamlit pymupdf chromadb pyngrok faiss-cpu sentence-transformers mistralai==0.4.2 python-docx streamlit-copy-to-clipboard
