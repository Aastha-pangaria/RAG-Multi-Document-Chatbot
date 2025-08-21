# Multi-Document RAG Chatbot with Streamlit and Mistral AI 🤖

This project implements a sophisticated **Retrieval-Augmented Generation (RAG) chatbot** capable of answering questions based on a collection of user-uploaded documents. It features two distinct Streamlit applications: a clean, user-facing chat interface and a comprehensive developer dashboard for evaluation and performance tuning.

The core of the project lies in its ability to parse multiple document types (PDF, DOCX, TXT), index their content into a vector database, and use this indexed knowledge to provide contextually accurate answers through the Mistral AI language model, effectively minimizing hallucinations.

---

## 🚀 Key Features

* **Multi-Document Support:** Upload and process multiple `.pdf`, `.docx`, and `.txt` files simultaneously.
* **RAG Architecture:** Leverages the RAG pattern to ground LLM responses in the provided documents, ensuring answers are factual and context-based.

**High-Performance Components:**

* **LLM:** `mistral-small-latest` for fast and accurate text generation.
* **Embedding Model:** `all-MiniLM-L6-v2` for efficient and effective sentence embeddings.
* **Vector Store:** ChromaDB for fast, local vector similarity search.

**Dual-Interface System:**

* `app.py`: A simple and intuitive chat interface for end-users.

* `app_eval.py`: An advanced evaluation dashboard for developers to analyze and tune the RAG pipeline.

* **Comprehensive RAG Evaluation:** The developer dashboard provides real-time metrics for each query, including Groundedness, Relevance, Latency, and retrieval precision/recall proxies.

* **Automated Benchmarking:** Run automated evaluations using a CSV file of questions and expected answers to systematically measure performance.

---

## 🧠 Detailed RAG Pipeline & Architecture

The project's architecture is a classic **Retrieval-Augmented Generation (RAG)** pipeline. It functions like an intelligent assembly line for information: it starts with raw documents and ends with a precise, context-aware answer.

### 1. Document Loading & Chunking 📥

**How it Works:**
The user uploads files via the Streamlit interface. These files are then processed by specialized libraries.

* **Text Extraction:** PyMuPDF for PDFs and python-docx for Word documents.
* **Chunking Strategy:** Text is split into smaller, overlapping chunks to preserve context across boundaries.

---

### 2. Embedding & Indexing 🔬

* **Embedding:** Convert each chunk into a vector using the SentenceTransformer model `all-MiniLM-L6-v2`.
* **Indexing:** Store embeddings in ChromaDB for fast Approximate Nearest Neighbor (ANN) search.

---

### 3. Retrieval 🔍

* **Query Embedding:** Convert the user’s question into a vector.
* **Similarity Search:** Find top-k document chunks semantically similar to the question.
* **Context Assembly:** Combine relevant snippets to form the context for the LLM.

---

### 4. Generation ✍️

* **Prompt Engineering:** Wrap the question and retrieved context in instructions:

> "Answer the user's question based ONLY on the provided context. If the answer is not in the context, say you could not find the answer."

* **Grounded Response:** Forces Mistral AI to act as a reading comprehension engine, reducing hallucinations.

---

## 🛠️ Technology Stack

* **Frontend:** Streamlit
* **Document Parsing:** PyMuPDF, python-docx
* **Embedding:** Sentence-Transformers
* **Vector Database:** ChromaDB
* **LLM:** Mistral AI Platform
* **Deployment (Colab Demo):** pyngrok

---

## 📁 Project Structure

```
.
├── app.py                  # Main user-facing Streamlit application
├── app_eval.py             # Developer evaluation dashboard application
```

---

## ⚙️ Setup and Installation

### 1. Prerequisites

* Python 3.8+
* A Mistral AI API Key

### 2. Clone the Repository

```bash
git clone https://github.com/Aastha-pangaria/RAG-Multi-Document-Chatbot.git
cd RAG-Multi-Document-Chatbot
```

### 3. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Set Up API Keys

```bash
export MISTRAL_API_KEY="your_mistral_api_key_here"
```

---

## ▶️ How to Run

You can run either the user-facing app or the developer evaluation app.

### Running the User-Facing Chatbot (`app.py`)

```bash
streamlit run app.py
```

**How to use:**

1. Upload one or more documents (`.pdf`, `.docx`, `.txt`) in the sidebar.
2. Click the **Process Documents** button to index the content.
3. Once processing is complete, ask questions in the chat input box.

### User-Interface Image

<img width="1570" height="919" alt="image" src="https://github.com/user-attachments/assets/be421373-b995-4909-b172-d33ffa78835e" />

### Developer-Interface Image
<img width="1560" height="874" alt="image" src="https://github.com/user-attachments/assets/7167a0e0-4210-414c-acd8-ac87e7e0db58" />


---

### Running the Developer Evaluation Dashboard (`app_eval.py`)

```bash
streamlit run app_eval.py
```

**How to use:**

1. **Configure:** Adjust RAG parameters like `top_k` and `chunk_size` in the sidebar.
2. **Upload & Process:** Upload your documents and process them.
3. **Chat & Analyze:** Ask questions; a detailed metrics panel appears below each answer showing latency, groundedness, relevance, etc.
4. **Benchmark:** Upload a CSV with questions to run automated evaluation and download results.

---

## 📜 License

This project is open-source and available under the **MIT License**.
