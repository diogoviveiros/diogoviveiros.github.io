---
title: "Topic Similarity Clustering"
excerpt: "Flask app for clustering topics from CSV files using a transformer architecture combined with hierarchichal clustering methods."
collection: portfolio
---

This project is a Flask-based web app that performs text clustering on CSV data — ideal for quickly identifying themes or duplicate content from unstructured text.

**How It Works**
- Upload a `.csv` file with `Title` and `Description`.
- Cleans and tokenizes text using a transformer-based model.
- Supports fixed clusters or auto-adjusted based on similarity threshold.
- Cosine similarity used for grouping.

**Why It Matters**
- ⚡ Fast: Handles a few hundred rows in minutes.  
- 🧠 Smart: Modern NLP embeddings for accurate clustering.  
- 🧰 Practical: Useful for deduplicating articles, grouping feedback, and more.

**Features**
- Flask-based web UI  
- Real-time clustering feedback  
- Downloadable clustered results  
- Adjustable clustering sensitivity or fixed count

[View Project on Github](https://github.com/diogoviveiros/Topic-Similarity-Clustering)
