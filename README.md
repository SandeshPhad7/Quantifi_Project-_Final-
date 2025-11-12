# Quantifi_Project-_Final-: Production-Grade NLP Customer Review Analysis Pipeline

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)
[![Python](https://img.shields.io/badge/python-3.8%2B-blue)]()
[![Project Status: Complete](https://img.shields.io/badge/status-complete-brightgreen.svg)]()

---

## 📖 Overview

**Quantifi_Project-_Final-** is an enterprise-ready, end-to-end pipeline for in-depth analysis of customer reviews using *only classical, interpretable NLP methods* (no transformers/LLMs). This repo takes in e-commerce product reviews (Air Coolers case study: 500 real reviews) and delivers sentiment, topic, cluster, and actionable insights, along with interactive visualizations.

- **Business Use:** Understand what customers say, how they feel, which themes matter most, and what to improve—all with outputs you can trust and explain.

---

## 📂 Project Structure

```
Quantifi_Project-_Final-/
├── Dataset-SA.csv                  # Customer review dataset (Air Coolers)
├── requirements.txt                # Python dependencies
├── run_all.py                      # Runs the full pipeline
├── phase1_preprocessing.py         # Data cleaning & preparation
├── phase2_analysis.py              # Syntactic, semantic, and vector NLP
├── phase3_advanced.py              # Review summarization, clustering, QA, business insights
├── dashboard.py                    # Dashboards & visualizations (png)
├── HOW_TO_RUN.md                   # Quick start guide & troubleshooting
├── README.md                       # This file (Overview & Documentation)
└── (Outputs auto-generated:)
    ├── processed_reviews.csv/pkl
    ├── phase1_statistics.json
    ├── pos_analysis.json
    ├── ner_analysis.json
    ├── sentiment_analysis.json
    ├── topic_modeling.json
    ├── word2vec_model.bin
    ├── review_clusters.json
    ├── question_answering.json
    ├── actionable_insights.json
    └── dashboard_*.png (6+ viz)
```

---

## 🛠 Methods & Analysis – What Happens in Each Phase

### Phase 1: Data Acquisition & Preprocessing

- **Input:** 500 customer reviews (`Dataset-SA.csv`)
- **Processing:**
  - Language identification (handles 13 languages; flags non-English)
  - Cleaning: removes HTML, URLs, emojis, special chars
  - Case normalization, encoding fixes
  - Tokenization (words & sentences)
  - Stopword removal
  - Lemmatization (WordNet), Stemming fallback
- **Outputs:** 
  - `processed_reviews.csv/.pkl`
  - `phase1_statistics.json` (summary stats)

### Phase 2: Syntactic & Semantic NLP Analysis

- **POS Tagging:** Identify parts-of-speech; find most common adjectives & verbs
- **Named Entity Recognition (NER):** Rule-based NLTK entity extraction
- **Text Vectorization:** 
  - Bag-of-Words (CountVectorizer, 1k features)
  - TF-IDF (top keywords, 1k features)
- **Word Embeddings:** Custom Word2Vec (CBOW, Gensim)
- **Semantic Similarity:** Review-to-review similarity (Cosine, TF-IDF)
- **Sentiment Analysis:** Lexicon-based polarity scoring for every review
- **Topic Modeling:** LSA (SVD, n=5 topics), interpretable themes & topic assignment per review
- **Output Artifacts:**
  - `pos_analysis.json`
  - `ner_analysis.json`
  - `tfidf_top_terms.json`
  - `word2vec_model.bin`
  - `sentiment_analysis.json`
  - `topic_modeling.json`
  - `word_similarity.json`
  - `phase2_analyzed_reviews.pkl/csv`

### Phase 3: Advanced Analysis, Insights, and Q&A

- **Review Summarization & Clustering:** KMeans segments reviews into 5 clusters & extracts representatives (with centroid distance)
- **Common Feedback Extraction:** Finds and summarizes major recurring review groups (vector similarity > threshold)
- **Automated Question Answering:** Answers business/customer questions using only real review data ("Is the cooling good?", "Value for money?", etc.)
- **Insight Generation:** Generates strengths, pain points, and actionable recommendations for buyers and product teams
- **Key Outputs:** `review_clusters.json`, `cluster_analysis.json`, `question_answering.json`, `actionable_insights.json`, `phase3_final_results.pkl/csv`

### Visualization Dashboard (dashboards.py)

Outputs 6+ high-quality PNG charts:
- **Overview:** Sentiment, star distribution, clusters, adjectives, metrics
- **Wordclouds:** (Positive/Negative/Neutral)
- **Topic Analysis:** Distribution, keywords, sentiment/ratings by topic
- **Insights Report:** Strengths, weaknesses, recommendations
- **Q&A Result Visuals:** Explains answers from review data
- **Statistical Analysis:** Rating, sentiment correlation, review length, feature heatmaps

---

## 📊 Project Dataset

- **Product:** Air Coolers (including Candes and Maharaja Whiteline)
- **Review Count:** 500 unique reviews, all labeled
- **Sentiment:** 84.2% positive, 12.2% negative, 3.6% neutral
- **Language:** Multilingual (auto-detected & handled)
- **Avg. Rating:** 4.13/5.0

---

## 🔥 Key Results

- **Sentiment Analysis:** 84% positive, lexicon-based accuracy ~56%
- **Top Topics:** General quality, cooling efficacy, price/value, features, customer experience
- **Cluster Discoveries:** 5 customer types including value-seekers and superfans
- **Answering Key Questions:** E.g., "Is the cooling good?" — 80%+ positive on cooling mentions.
- **Business Insights:** Provides explicit, actionable recommendations (for both buyers & manufacturers)

---

## 📈 Example Dashboard Outputs

- `dashboard_overview.png` – Main KPIs, top adjectives, sentiment
- `dashboard_wordclouds.png` – Visualizes term usage by sentiment
- `dashboard_topics.png` – Key topics, distribution, ratings
- `dashboard_insights.png` – Strengths, weaknesses, recommendations
- `dashboard_qa.png` – Q&A in business language
- `dashboard_statistics.png` – Deep dives & correlations

---

## 📦 Technologies Used

- **Languages:** Python 3.8+
- **NLP & Data:** pandas, numpy, nltk, scikit-learn, gensim, langdetect
- **Visualization:** matplotlib, seaborn, wordcloud
- **Clustering & Modeling:** KMeans, TruncatedSVD (for LSA), cosine similarity
- **All classical/statistical methods – no black-box transformers**

---

## ⚡ Getting Started

1. **Clone / Download**
2. **Install requirements:**  
   ```
   pip install -r requirements.txt
   ```
3. **Quickstart (All-in-one):**
   ```
   python run_all.py
   ```
4. **Or run each phase separately for more control (see HOW_TO_RUN.md)**

---

## ⏱️ Runtime

- **Average full run:** ~3–4 minutes
- **Phase breakdown:**  
    - Preprocessing: ~30s  
    - NLP Analysis: 1–2 min  
    - Clustering & Insights: ~30s  
    - Dashboards: ~30s

---

## 👨‍🔬 Reproducibility & Code Quality

- Modular, clear-phase scripts
- In-code docstrings & comments
- Intermediate JSON/CSV for every analysis step
- Fixed random seeds
- Progress logging, robust error handling

---

## 📝 License

```
MIT License

Copyright (c) 2025 SandeshPhad7

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

---

## 🤝 Contributions

PRs and issues are welcome! Please open an issue if you find a bug, have a suggestion, or want to contribute. If you use this repo for research or in a business context, attribution is appreciated.

---

## 👤 Author

- [SandeshPhad7](https://github.com/SandeshPhad7)

---

## 📬 Support & Questions

See `HOW_TO_RUN.md` for troubleshooting. For help, open a GitHub issue.

---

**100% classical/statistical NLP. Explainable. Reliable. No transformers—fully interpretable analytics for product review mining and insight.**
