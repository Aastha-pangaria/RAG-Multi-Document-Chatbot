# RAG Multi-Document Chatbot

RAG Multi-Document Chatbot is a Streamlit-based application that allows you to **upload and chat with multiple documents** (PDF, DOCX, TXT). It leverages modern embedding models and the Mistral API to provide **context-aware answers** to your questions, using **Retrieval-Augmented Generation (RAG)** techniques for high-quality responses from your own files.

---

## Features

- **Multi-Document Support**: Upload and process multiple PDF, DOCX, and TXT files simultaneously.
- **Contextual Q&A**: Ask questions and receive answers grounded in the content of your uploaded documents.
- **Modern Embeddings**: Uses **SentenceTransformers** for semantic search and chunk retrieval.
- **Persistent Vector Storage**: Utilizes **ChromaDB** for efficient document chunk indexing and retrieval.
- **Mistral API Integration**: Generates high-quality, context-aware responses.
- **User-Friendly Interface**: Built with Streamlit, featuring a clean interface for uploads and chat.
- **Dual-Mode Operation**: Includes a minimalist UI for end-users (`app.py`) and a data-rich dashboard with real-time metrics for developers (`app_eval.py`).

---

## Screenshots

*A clean, user-facing interface for seamless interaction.*
*A detailed developer dashboard with real-time RAG metrics for performance evaluation.*
---

## Installation

1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/your-repo.git](https://github.com/your-username/your-repo.git)
    cd your-repo
    ```

2.  Install the required libraries:
    ```bash
    pip install -r requirements.txt
    ```
    *Or manually install:*
    ```bash
    pip install streamlit pymupdf chromadb pyngrok faiss-cpu sentence-transformers mistralai==0.4.2 python-docx streamlit-copy-to-clipboard
    ```

---

## Setup

You need to set your API keys as environment variables.

### Mistral API Key
1.  Obtain a key from [Mistral AI](https://mistral.ai/).
2.  Set it in your environment:
    ```bash
    # For Linux / macOS
    export MISTRAL_API_KEY="your_api_key_here"

    # For Windows
    set MISTRAL_API_KEY="your_api_key_here"
    ```

### Ngrok Auth Token (Optional)
This is only needed for running in cloud environments like Google Colab.
1.  Obtain a token from your [ngrok dashboard](https://dashboard.ngrok.com/).
2.  Set it in your environment:
    ```bash
    # For Linux / macOS
    export NGROK_AUTH_TOKEN="your_ngrok_token"

    # For Windows
    set NGROK_AUTH_TOKEN="your_ngrok_token"
    ```

---

## Usage

1.  **Run the App**:
    ```bash
    streamlit run app.py
    ```

2.  **Upload Documents**:
    Use the sidebar to upload one or more PDF, DOCX, or TXT files.

3.  **Process Documents**:
    Click the "Process" button to extract text, create chunks, and build the vector index.

4.  **Chat**:
    Once processing is complete, ask questions about your documents using the chat interface.

---

## Developer Evaluation Dashboard

This project includes a separate dashboard (`app_eval.py`) for in-depth performance analysis.

**To run the evaluation dashboard:**
```bash
streamlit run app_eval.py
```

**Features include:**
-   **Live Metrics**: View real-time metrics for each response, including **Latency**, **Groundedness**, **Relevance**, and **Retrieval Similarity**.
-   **Hallucination Detection**: An automated warning system flags responses with low grounding scores.
-   **User Feedback**: Track feedback with interactive 👍/👎 buttons.
-   **Data Export**: Download the full session metrics as a CSV file for further analysis.

---

### Troubleshooting
-   **API Key Issues**: Ensure your `MISTRAL_API_KEY` is valid, active, and correctly set as an environment variable.
-   **File Errors**: The app supports PDF, DOCX, and TXT files. Corrupted or password-protected files may cause errors.
-   **Dependencies**: If you encounter import errors, ensure all packages in `requirements.txt` are installed correctly.

---

### Contributions
Contributions, issues, and feature requests are welcome! Please open a GitHub issue or submit a pull request.
