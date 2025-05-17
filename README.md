# Industry Classification using RAG (Ramp-Inspired)

This project is a simplified, open-source version of Ramp’s in-house RAG-based industry classification system — rebuilt using public tools like Hugging Face, FAISS, and T5.

## 📖 Inspiration

Ramp's blog ["From RAG to Richness"](https://engineering.ramp.com/post/industry_classification) outlines how they migrated their business classification pipeline to a RAG setup for better precision and control. I tried replicating that concept using open data and open-source tools.

## 🔧 Tools & Stack

- `DistilBERT` (from Hugging Face) for text embeddings
- `FAISS` for fast similarity search on industry descriptions
- `T5` and `flan-T5-base` for selecting the best NAICS match from candidates
- `NAICS` dataset as the knowledge base

## Pipeline Overview

1. Business description → DistilBERT embedding
2. Compare against NAICS embeddings via FAISS (top-k similarity)
3. Feed top-k matches into a T5 model to choose the best fit
4. Output: `[Description]`

