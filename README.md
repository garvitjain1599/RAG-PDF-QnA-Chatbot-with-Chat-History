# RAG-QnA-Conversation-With-PDF-with-Chat-History
# Conversational RAG with PDF Uploads and Chat History

A Retrieval-Augmented Generation (RAG) application built using **LangChain**, **Groq LLM**, **ChromaDB**, and **Streamlit** that allows users to upload PDF documents and interact with them through a conversational chat interface. The application maintains chat history, enabling context-aware follow-up questions and a more natural conversational experience.

---

## Features

* Upload and process one or more PDF documents.
* Extract and chunk document content for efficient retrieval.
* Generate vector embeddings using Hugging Face Embeddings.
* Store embeddings in ChromaDB vector store.
* Context-aware retrieval using LangChain History-Aware Retriever.
* Conversational memory with session-based chat history.
* Powered by Groq's Llama 3.1 model for fast inference.
* Streamlit-based interactive web interface.

---

## Tech Stack

* Python
* Streamlit
* LangChain
* LangChain Chroma
* ChromaDB
* Hugging Face Embeddings
* Groq API
* PyPDFLoader

---

## Project Workflow

1. User uploads one or more PDF documents.
2. PDF content is extracted using PyPDFLoader.
3. Documents are split into smaller chunks using RecursiveCharacterTextSplitter.
4. Text chunks are converted into embeddings using Hugging Face Embeddings.
5. Embeddings are stored in ChromaDB.
6. User submits a question.
7. LangChain reformulates context-dependent questions into standalone questions using chat history.
8. Relevant document chunks are retrieved from the vector database.
9. Retrieved context and chat history are passed to the LLM.
10. Groq Llama 3.1 generates a concise answer.

---

## Architecture

```text
PDF Upload
    │
    ▼
PyPDFLoader
    │
    ▼
Text Splitter
    │
    ▼
Hugging Face Embeddings
    │
    ▼
Chroma Vector Store
    │
    ▼
History-Aware Retriever
    │
    ▼
Retrieval Chain
    │
    ▼
Groq LLM
    │
    ▼
Response to User
```

---

## Installation

### Clone the Repository

```bash
git clone <repository-url>
cd <repository-name>
```

### Create Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

Windows

```bash
venv\Scripts\activate
```

Linux / Mac

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file in the project root directory.

```env
HF_TOKEN=your_huggingface_token
```

The Groq API key is entered directly through the Streamlit application interface.

---

## Running the Application

```bash
streamlit run app.py
```

Open the local Streamlit URL displayed in the terminal.

---

## Usage

1. Launch the Streamlit application.
2. Enter your Groq API key.
3. Upload one or more PDF files.
4. Provide a session ID for maintaining chat history.
5. Ask questions about the uploaded documents.
6. Continue the conversation with follow-up questions that reference previous interactions.

---

## Example Queries

* What is the main topic of this document?
* Summarize the uploaded PDF.
* What are the key findings mentioned?
* Can you explain this section in simpler terms?
* What did the document mention about machine learning?
* Elaborate on the previous answer.

---

## Key LangChain Components Used

### History-Aware Retriever

Reformulates follow-up questions into standalone questions by leveraging conversation history.

### Retrieval Chain

Retrieves relevant document chunks and passes them to the language model.

### RunnableWithMessageHistory

Maintains session-specific chat history, enabling multi-turn conversations.

### Chroma Vector Store

Stores embeddings and performs similarity-based retrieval.

---

## Future Improvements

* Persistent vector database storage.
* Multiple document collections.
* Source citations in responses.
* Conversation export functionality.
* Support for additional document formats (DOCX, TXT, HTML).
* User authentication and session management.
* Cloud deployment using Streamlit Community Cloud or AWS.

---

## Author

Garvit Jain

GitHub: https://github.com/garvitjain1599
