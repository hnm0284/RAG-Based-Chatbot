# 🧠 RAG-Based Chatbot using LangChain, Groq (LLaMA 3), and FAISS

RAG Chatbot Created a chatbot using LangChain, LLaMA 3.1 8B from Groq, and FAISS. Used RAG to find and read documents, then answer questions smartly using a local language model.


This project demonstrates a lightweight Retrieval-Augmented Generation (RAG) chatbot that answers questions from real documents using:
- 📄 PDF documents (`Corona 2025` reports)
- 🔍 LangChain for document loading, splitting, retrieval
- 🤖 LLaMA 3 (via Groq API) as the reasoning LLM
- 🧠 FAISS for vector-based similarity search
- 💡 Sentence-transformers for embedding generation

---

## 🔧 Project Features

- Loads multiple PDFs using `UnstructuredPDFLoader`
- Splits content into smart overlapping chunks for context
- Embeds chunks with `all-MiniLM-L6-v2` from HuggingFace
- Stores vectors in a FAISS index
- Uses a Groq-hosted **LLaMA 3 model** to generate smart, grounded answers

---

## 🧪 Tech Stack

| Component | Tool/Library |
|----------|--------------|
| LLM      | [Groq LLaMA 3](https://groq.com/) (8B or 2B) |
| Vector DB| FAISS |
| Embedding| `sentence-transformers/all-MiniLM-L6-v2` |
| Framework| LangChain |
| Loader   | Unstructured PDF Loader |
| Platform | Kaggle Notebook (or local Jupyter) |



## 🚀 How It Works

1. **PDF Loading**  
   Loads and parses multiple documents using LangChain’s `UnstructuredPDFLoader`.

2. **Text Splitting**  
   Chunks text into overlapping segments using `RecursiveCharacterTextSplitter`.

3. **Embeddings & Indexing**  
   Each chunk is converted to a 384-dim vector using `MiniLM` and stored in a FAISS index.

4. **RAG Chat**  
   A query is embedded → matched against top-k relevant chunks → passed to Groq's LLaMA for answering.

---

## ✅ How to Run

### 🔐 1. Set up your Groq API key
You need a Groq account and an API key. Set it via environment variable:
```
python
import os
os.environ["GROQ_API_KEY"] = "your_groq_api_key_here"
```


