RAG Multi-Document Chatbot

RAG Multi-Document Chatbot is a Streamlit-based application that allows you to upload and chat with multiple documents (PDF, DOCX, TXT). It leverages modern embedding models and the Mistral API to provide context-aware answers to your questions, using Retrieval-Augmented Generation (RAG) techniques for high-quality responses from your own files.

Features

Multi-document support: Upload and process multiple PDF, DOCX, and TXT files simultaneously.

Contextual Q&A: Ask questions and receive answers grounded in the content of your uploaded documents.

Modern embeddings: Uses SentenceTransformers for semantic search and chunk retrieval.

Persistent vector storage: Utilizes ChromaDB for efficient document chunk indexing and retrieval.

Mistral API integration: Generates high-quality, context-aware responses.

User-friendly interface: Streamlit web app with sidebar for uploads and API key management.

Secure: Your API key is never stored.

Usage
Set your Mistral API Key

Obtain an API key from Mistral
.

Enter the key in the Streamlit sidebar when prompted.

Run the app
streamlit run app.py

Upload documents

Use the sidebar to upload PDF, DOCX, or TXT files (multiple uploads supported).

Process documents

Click the "Process Documents" button to extract, chunk, and embed your files.

Chat

Ask questions about your documents using the chat interface.
The app retrieves relevant content and generates answers using the Mistral API.

Modes

The chatbot provides two modes for different usage scenarios:

1. Developer Mode

Designed for testing, debugging, and evaluation purposes.

Displays detailed logs, chunk processing insights, and intermediate retrieval information.

Useful for developers fine-tuning RAG pipeline performance.

2. Normal Mode

Simplified interface for everyday document Q&A.

Minimal logs with a clean user experience.

Notes

The app runs locally on port 8501 by default.

For remote access, ngrok integration is included to expose your local Streamlit app via a public URL.

Only the last 50 chat messages are stored per session for privacy and performance.

Troubleshooting

API Key Issues: Ensure your Mistral API key is valid and active.

File Errors: Only PDF, DOCX, and TXT files are supported. Corrupted or empty files will be skipped.

Dependencies: If you encounter missing package errors, re-run the pip install command above.

Contributions

Contributions, issues, and feature requests are welcome!

Fork the repository

Create your branch:

git checkout -b feature/YourFeature


Commit changes:

git commit -m 'Add YourFeature'


Push your branch:

git push origin feature/YourFeature


Open a Pull Request

License

This project is licensed under the MIT License. See the LICENSE
 file for details.

Built With

Made with ❤️ to enhance document Q&A and knowledge retrieval using a RAG-based evaluation framework.
