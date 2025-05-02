# SHL Assessment Recommendation System

A semantic recommendation engine that returns the most relevant SHL assessments based on natural language job queries.

---

## Project Overview

This system uses sentence-level embeddings and semantic search to match job descriptions to suitable SHL assessments. I initially implemented the solution using Google’s Gemini embedding model. However, the results did not meet the accuracy expectations, particularly in retrieving relevant assessments. To improve performance, I transitioned to a sentence-transformer-based approach (BAAI/bge-small-en), which delivered significantly better and more consistent results.”

### Key Features

- Scraped SHL catalog using custom Python notebook
- Explored two embedding models:
  - Google Gemini (`embedding-001`)
  - Sentence Transformers (`BAAI/bge-small-en`)
- Built vector search with FAISS (cosine similarity)
- Benchmarked with Recall@3 and MAP@3
- Deployed:
  - Gradio UI on Hugging Face
  - REST API on Render (FastAPI)

---

## Model Comparison: Gemini vs Sentence Transformers

| Feature                  | Gemini (embedding-001) | Sentence Transformers (bge-small-en) |
|--------------------------|------------------------|--------------------------------------|
| Source                   | Google GenAI API       | Hugging Face (local)                 |
| Accuracy (Recall@3)      | 0.57                   | **0.71**                             |
| Accuracy (MAP@3)         | 1.43                   | **1.57**                             |
| Performance              | Slower + Quota Limited | Fast, No Limits                      |
| Deployment Simplicity    | Needs API Key          | Fully Local                          |
| Final Choice             | ❌                     | ✅ Selected for Submission           |

---

## Repository Contents

| File/Folder                             | Description                                  |
|----------------------------------------|----------------------------------------------|
| `shl_assessments_full_data.csv`        | Scraped dataset of SHL assessments           |
| `SHL_Site_Scrape.ipynb`                | Script to scrape SHL site                    |
| `Sentence_transformers_SHL_assessment_prediction.ipynb` | BGE model embedding + search     |
| `Gemini_SHL_assessment_prediction.ipynb` | Gemini API-based embedding                 |
| `bge_embeddings.npy`                   | Sentence Transformer vector embeddings       |
| `gemini_embeddings.npy`                | Gemini-generated vector embeddings           |
| `SHL_Assessment_transformer_API_Test.ipynb` | Accuracy eval, Recall@3, MAP@3          |
| `Assessment recommendation Report.pdf` | Project summary report                       |
| `model_comparison_report.docx`         | Comparison of Gemini vs Sentence Transformers|
| `README.md`                            | You’re reading it                            |

---

## Evaluation Results

Evaluated using 7 realistic queries aligned with catalog coverage (industrial, banking, support).

| Metric     | Sentence Transformers | Gemini Embeddings |
|------------|------------------------|-------------------|
| Recall@3   | ✅ 0.71                | 0.57              |
| MAP@3      | ✅ 1.57                | 1.43              |

---

## Deployment

### Web UI Demo (Gradio)
👉 [Try the Recommender UI](https://huggingface.co/spaces/boopal03/SHL-Assessment-recommendation-Engine-sentence-transformers)

### Public API (FastAPI on Render)
Base URL: https://shl-assessment-engine-api.onrender.com


