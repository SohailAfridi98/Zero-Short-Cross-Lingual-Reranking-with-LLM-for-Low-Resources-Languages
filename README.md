# 🌍 CIRAL Swahili Reranking Research

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/release/python-3120/)
[![Framework: PyTorch](https://img.shields.io/badge/Framework-PyTorch-orange.svg)](https://pytorch.org/)

This repository contains the reproduction study and research extensions for the **CIRAL (Cross-lingual Information Retrieval for African Languages)** benchmark, specifically focusing on the **Swahili (sw)** track. Our work evaluates specialized African models (AfriMT5) and state-of-the-art LLMs (Gemini, RankZephyr) across English Reranking and Cross-lingual settings.

## 📌 Project Overview
The goal of this project is to bridge the accessibility gap for low-resource languages by optimizing how search systems retrieve native Swahili passages for English queries. We investigate two primary paradigms:
1. **English Reranking:** Translating Swahili documents into English before ranking.
2. **Cross-lingual Reranking:** Directly matching English queries to native Swahili passages.

## 📊 Key Results (k=20)
| Model | Setting | Strategy | nDCG@20 | MRR@20 |
| :--- | :--- | :--- | :--- | :--- |
| **AfriMT5** | Cross-lingual | **Listwise** | 0.2376 | **0.5767** |
| **AfriMT5** | Cross-lingual | Pointwise | **0.2410** | 0.5516 |
| **RankZephyr** | English Rerank | Listwise | 0.2123 | 0.4064 |
| **Gemini 1.5** | Cross-lingual | Listwise | 0.2123 | 0.4064 |

## 🛠️ Implementation Details
### Hardware
- **Inference:** Google Colab T4 GPU (16GB VRAM)
- **Development:** MacBook Air 2020 (Intel i5, 8GB RAM)

### Frameworks & Tools
- `transformers`: For mT5 and AfriMT5 inference.
- `google-genai`: For Gemini 1.5 Flash integration.
- `pyserini`: For BM25 first-stage retrieval and TREC evaluation.
- `PyTorch`: Backend for model execution.

## 🚀 Getting Started

### 1. Installation
```bash
pip install -r requirements.txt
# Ensure pyserini and trec-eval are installed for evaluation
pip install pyserini
