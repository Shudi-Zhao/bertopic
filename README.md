# BERTopic Learning Repository 📚

## 🚀 Overview
This repository serves as a **learning guide** for implementing **BERTopic**, a powerful topic modeling technique that uses transformers and c-TF-IDF for interpretable topic extraction. The goal is to explore **various functionalities of BERTopic**, optimize its parameters, and visualize topic distributions effectively.

All the code in this repository is based on the **official BERTopic documentation**, with modifications for better understanding and practical implementation.

---

## 📌 What This Repository Covers

- **[Quick Start](https://maartengr.github.io/BERTopic/getting_started/quickstart/quickstart.html)**  
  Learn how to extract topics from datasets like **20 newsgroups** using BERTopic.

- **[Fine-tuning Embeddings](https://maartengr.github.io/BERTopic/getting_started/embeddings/embeddings.html)**  
  Explore different **embedding techniques** (`sentence-transformers`, `spaCy`, `Flair`, `TF-IDF`, `OpenAI`, `Gensim`) and how to choose the best approach.

- **[Modularity](https://maartengr.github.io/BERTopic/getting_started/tips_and_tricks/tips_and_tricks.html)**  
  Learn how to **customize components** like embedding models, dimensionality reduction, clustering algorithms, and vectorizers.

- **[Topic Reduction](https://maartengr.github.io/BERTopic/getting_started/topicreduction/topicreduction.html)**  
  Understand how to merge, split, or refine topics **after training** to improve interpretability.

- **[Dimensionality Reduction](https://maartengr.github.io/BERTopic/getting_started/dim_reduction/dim_reduction.html)**  
  Learn how **UMAP, PCA, and SVD** can be used to reduce high-dimensional embeddings, improving clustering efficiency and visualization.

- **[Clustering Techniques](https://maartengr.github.io/BERTopic/getting_started/clustering/clustering.html)**  
  Explore various clustering algorithms like **HDBSCAN**, **k-Means**, and **Agglomerative Clustering** to group similar documents and extract coherent topics.

- **[Vectorizers](https://maartengr.github.io/BERTopic/getting_started/vectorizers/vectorizers.html)**  
  Understand how **CountVectorizer** and **OnlineCountVectorizer** transform text data into numerical representations and how to customize them for enhanced topic modeling.

- **[Visualizing Documents](https://maartengr.github.io/BERTopic/getting_started/visualization/visualize_documents.html)**  
  Use `plotly` and `matplotlib` to explore how documents relate to discovered topics.

- **[Visualizing Topic Similarity](https://maartengr.github.io/BERTopic/getting_started/visualization/visualize_topics.html#visualize-topic-similarity)**  
  Examine **semantic relationships** between topics using **UMAP-based clustering**.
---

## 🛠️ Installation
To set up the environment and run the code:
```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
pip install -r requirements.txt