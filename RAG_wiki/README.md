# Knowledge Retrieval System with Vikhr-Nemo-12B-Instruct-R-21-09-24

## Overview
This project is a knowledge retrieval system based on Retrieval-Augmented Generation (RAG) that operates on text from Wikipedia. It combines vector and lexical search, with question rephrasing and result ranking using the Vikhr-Nemo LLM model.

## Features
- **Data**: The system uses 20 HTML Wikipedia pages with minimal cleaning.
- **Chunking**: Uses **Naive Chunking**, splitting articles into chunks for embedder.
- **Vector Database**: Vector data storage is organized with Chromadb.
- **Embeddings Model**: Embeddings are generated with [sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2](https://huggingface.co/sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2).
- **LLM Model**: Powered by [Vikhr-Nemo-12B-Instruct-R-21-09-24](https://huggingface.co/Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24), specifically the **Q4_K_M-GGUF** version, compatible with `llama_cpp`. This model supports system prompts (recommended in English) and the `documents` role for structured queries.
- **Question and Result Rephrasing**: Questions and search results are rephrased by the LLM for more precise embedding-based search.
- **Keyword Generation**: LLM generates keywords to enhance lexical search.
- **Lexical Search**: **Whoosh** with **BM25F** algorithm is used for keyword-based search.
- **Results Merging**: Combines vector and lexical search results, removing duplicates.
- **Re-ranking**: The built-in Vikhr-Nemo re-ranker sorts final search results.
- **Final Answer**: Returns a structured response based on the combined search output, enriched with insights from all available data.

## To do
Implement advanced chunking techniques such as Semantic Chunking or Late Interaction for improved retrieval quality
Implement Auto-merging retrieval or Sentence-window retrieval
