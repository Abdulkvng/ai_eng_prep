# 02 - RAG (Retrieval Augmented Generation)

## What is RAG

Simple definition:

> RAG is when you give the model external data before it answers.

Instead of relying only on training data, the model reads relevant documents first.

## Why RAG exists

LLMs have problems:

- outdated knowledge
- hallucinations
- no access to private data

RAG fixes this by injecting real data.

## How RAG works

1. User asks a question
2. Convert question to embedding
3. Search vector database
4. Retrieve relevant documents
5. Send documents + question to LLM
6. LLM generates answer using context

## Key components

### Embeddings

Convert text into vectors so you can search by similarity.

### Vector database

Stores embeddings.

Examples: Pinecone, Weaviate, FAISS

### Retriever

Finds relevant documents.

### Generator

The LLM that writes the final answer.

## Common problems

- bad retrieval → wrong docs
- too much context → high cost
- irrelevant context → worse answers

## Improvements

- chunk documents better
- rerank results
- limit context size
- add citations

## Interview answer

If asked to design a knowledge AI system:

Say:

I would use RAG. I would store documents in a vector database, retrieve relevant chunks based on the query, and pass them to the model as context. I would also track retrieval quality and hallucination rate and iterate on chunking and ranking.
