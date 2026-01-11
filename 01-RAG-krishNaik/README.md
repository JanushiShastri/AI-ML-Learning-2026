# Retrieval-Augmented Generation (RAG) – Krish Naik

## Goal
Learn how RAG systems work and how to build retrieval-based AI pipelines for grounded LLM responses.

---

## What is RAG?

**Retrieval-Augmented Generation (RAG)** is a technique that combines large language models (LLMs) with an external retrieval system.  
Instead of relying only on model training data, the system retrieves relevant documents at query time and uses them as context for generation.  
This improves accuracy, reduces hallucinations, and allows models to use private or up-to-date data.

---

## Data Ingestion Pipeline (Offline)

This pipeline prepares the knowledge base before user queries.

### Steps
1. **Data Collection** – Load data from PDFs, docs, web pages, databases, etc.
2. **Cleaning & Normalization** – Remove noise, duplicates, formatting issues.
3. **Chunking** – Split large documents into smaller overlapping chunks.
4. **Embedding Generation** – Convert each chunk into vectors using an embedding model.
5. **Indexing / Storage** – Store vectors in a vector database (FAISS, Pinecone, Weaviate, etc.).

**Purpose:** Make data searchable by meaning for fast retrieval later.

---

## Data Retrieval Pipeline (Online / Query Time)

This pipeline runs when a user asks a question.

### Steps
1. **Query Embedding** – Convert user query into a vector.
2. **Similarity Search** – Find closest matching vectors from the database.
3. **Context Retrieval** – Select top relevant document chunks.
4. **Prompt Augmentation** – Combine retrieved context with user query.
5. **LLM Generation** – Generate grounded response using the provided context.

**Purpose:** Ensure responses are accurate, contextual, and not hallucinated.

---

## Resources
- Tutorial Playlist: https://www.youtube.com/watch?v=MykcjWPJ6T4&list=PLZoTAELRMXVM8Pf4U67L4UuDRgV4TNX9D

---

## Next Steps
- Implement a simple RAG pipeline using:
  - Embeddings (OpenAI / HuggingFace)
  - Vector DB (FAISS / Chroma)
  - LLM (OpenAI / LLaMA)