# 🩺 Medical Chatbot

A Retrieval-Augmented Generation (RAG) based Medical Chatbot built using **LangChain**, **OpenAI**, **Pinecone**, **Flask**, and **Hugging Face Embeddings**. The chatbot retrieves relevant information from medical PDF documents and generates context-aware responses using an OpenAI language model.

---

## Features

- 📄 Load medical PDF documents
- ✂️ Split documents into semantic chunks
- 🧠 Generate embeddings using Hugging Face (BAAI/bge-small-en-v1.5)
- 📦 Store embeddings in Pinecone Vector Database
- 🔍 Retrieve relevant document chunks
- 🤖 Generate answers using OpenAI GPT
- 🌐 Simple Flask web interface

---

## Tech Stack

- Python
- Flask
- LangChain
- OpenAI API
- Hugging Face Embeddings
- Pinecone
- FAISS (optional if added later)

---

## Project Structure

```text
Medical-Chatbot/
│
├── data/                  # Medical PDF documents
├── src/
│   ├── helper.py
│   ├── prompt.py
│   └── __init__.py
│
├── static/
├── templates/
├── app.py                 # Flask application
├── store_index.py         # Stores embeddings into Pinecone
├── requirements.txt
├── .env
└── README.md
```

---

## Installation

### Clone the repository

```bash
git clone https://github.com/yukteswar23/Medical-Chatbot.git
cd Medical-Chatbot
```

---

### Create a virtual environment

Using Conda

```bash
conda create -n medicalbot python=3.10 -y
conda activate medicalbot
```

or using venv

Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

Linux/macOS

```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

### Install dependencies

```bash
pip install -r requirements.txt
```

---

### Configure environment variables

Create a `.env` file in the project root.

```env
OPENAI_API_KEY=your_openai_api_key
PINECONE_API_KEY=your_pinecone_api_key
```

---

### Create the vector database

```bash
python store_index.py
```

This will:

- Load medical PDFs
- Split them into chunks
- Generate embeddings
- Upload embeddings to Pinecone

---

### Run the chatbot

```bash
python app.py
```

Open your browser:

```
http://localhost:5001
```

---

## RAG Pipeline

```
Medical PDFs
      │
      ▼
Document Loader
      │
      ▼
Text Splitter
      │
      ▼
Embedding Model
      │
      ▼
Pinecone Vector Store
      │
───────────────────────────────
      │
      ▼
User Query
      │
      ▼
Retriever
      │
      ▼
Relevant Chunks
      │
      ▼
OpenAI GPT
      │
      ▼
Final Response
```

---

## Requirements

- Python 3.10+
- OpenAI API Key
- Pinecone API Key

---

## Current Status

✅ Local RAG chatbot completed.

⚠️ Cloud deployment (AWS) is **not included** in this repository.

---

## Future Improvements

- Conversation memory
- Multiple PDF uploads
- Streamlit interface
- Docker support
- AWS / Azure deployment
- Authentication

---

## Acknowledgements

This project was inspired by tutorials from ** (entbappy)** and adapted using the latest LangChain and OpenAI APIs.