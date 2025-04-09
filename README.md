# SHL-Assessment-Recommendation-System

A semantic search–based recommendation engine that returns the most relevant SHL assessments for a given natural language job query. Supports both a web-based demo and an API endpoint for integration.

---

## Overview

This project uses NLP models to understand job descriptions and recommend suitable SHL assessments by semantically matching queries to assessment metadata.

- Data scraped from SHL's public catalog
- Uses both Gemini and Sentence Transformers for embedding
- FAISS for fast vector search
- Gradio (UI) and FastAPI (backend) for deployment
- Evaluated using Recall@3 and MAP@3

---

##  Repository Contents

| File/Folder                             | Description                                  |
|----------------------------------------|----------------------------------------------|
| `shl_assessments_full_data.csv`        | Scraped dataset of SHL assessments           |
| `SHL_Site_Scrape.ipynb`                | Script to scrape SHL site                    |
| `Sentence_transformers_SHL_assessment_prediction.ipynb` | Model building using BGE local model |
| `Gemini_SHL_assessment_prediction.ipynb` | Model building using Gemini API             |
| `bge_embeddings.npy`                   | Precomputed embeddings (BGE model)           |
| `gemini_embeddings.npy`                | Precomputed embeddings (Gemini API)          |
| `SHL_Assessment_transformer_API_Test.ipynb` | Test API endpoints for both versions    |
| `Assessment recommendation Report.pdf` | Final report summary                         |
| `README.md`                            | You're reading it                            |

---

## 🧾 Evaluation Results

| Metric     | Sentence Transformers | Gemini Embeddings |
|------------|------------------------|-------------------|
| Recall@3   | 0.71                   | 0.57              |
| MAP@3      | 1.57                   | 1.43              |

Benchmarks focused on realistic roles (e.g., warehouse worker, branch manager, customer service).

---

## 🚀 Live Demo & API

### 🌐 Web Demo (Gradio UI)
👉 [Try It on Hugging Face](https://huggingface.co/spaces/boopal03/SHL-Assessment-recommendation-Engine-sentence-transformers)

### 🔌 API Endpoint (Render)
POST your query to: boopalamani2003@gmail.com

