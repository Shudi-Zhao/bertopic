# BERTopic Learning Repository 📚

## 🚀 Overview
This repository serves as a **learning guide** for implementing **BERTopic**, a powerful topic modeling technique that uses transformers and c-TF-IDF for interpretable topic extraction. The goal is to explore **various functionalities of BERTopic**, optimize its parameters, and visualize topic distributions effectively.

All the code in this repository is based on the **official BERTopic documentation**, with modifications for better understanding and practical implementation.


## 📌 Steps in BERTopic Modeling

BERTopic follows a structured process to extract meaningful topics from textual data. Below are the key steps:

### **1️⃣ Embedding the Text**
Convert documents into numerical representations using different techniques:
- `sentence-transformers`
- `TF-IDF`
- `spaCy`
- `Flair`
- `OpenAI Embeddings`

---

### **2️⃣ Dimensionality Reduction**
Reduce the high-dimensional embeddings to a lower-dimensional space for better clustering.
Common techniques:
- `UMAP` (Uniform Manifold Approximation and Projection)
- `PCA` (Principal Component Analysis)
- `Truncated SVD`

---

### **3️⃣ Clustering**
Group similar documents together into clusters.
- **Default algorithm**: `HDBSCAN` (Hierarchical Density-Based Clustering)
- **Alternative methods**: `k-Means`, `Agglomerative Clustering`

---

### **4️⃣ Vectorization**
Convert text into a numerical representation for topic extraction.
- **Default method**: `CountVectorizer`
- **Alternative vectorizers**:
  - `TF-IDF`
  - `OnlineCountVectorizer` (for online learning)
  - `Custom Vectorizers` (e.g., BERT embeddings for contextual tokenization)

---

### **5️⃣ Topic Representation**
Extract meaningful words for each topic.
- **Default method**: `c-TF-IDF` (Class-based Term Frequency-Inverse Document Frequency)
- **Other techniques**:
  - `Maximal Marginal Relevance (MMR)`
  - `KeyBERT Inspired`
  - `LLMs` (GPT, Cohere, OpenAI)

---

### **6️⃣ Refinement & Visualization**
Fine-tune topics using:
- `Topic Reduction`
- `Merging or Splitting Topics`
- `Multi-Aspect Representations`

Visualize topics using:
- `UMAP`
- `Topic Similarity Graphs`
- `Word Clouds`

---

### **7️⃣ Dynamic Topic Modeling (Optional)**
Track topic evolution over time using `topics_over_time()`.


**BERTopic is highly modular**, allowing customization at every step for different use cases.  

## 📌 Choosing the Right Embedding Method

BERTopic supports multiple **embedding techniques** for text representation. The choice depends on your dataset and objectives.

| **Method**            | **Best For**                   | **Pros**                                   | **Cons**                          |
|----------------------|------------------------------|--------------------------------------------|----------------------------------|
| **TF-IDF**          | Small datasets, keyword-based topics  | Fast, interpretable, no external models required | Limited semantic understanding |
| **sentence-transformers** | General-purpose topic modeling | Captures semantic meaning, widely used | Requires larger models |
| **spaCy**           | Lightweight applications      | Efficient, supports various linguistic features | Lower accuracy compared to transformers |
| **Flair**           | Context-aware embeddings      | Captures deeper language nuances | Slower training |
| **OpenAI / GPT-based** | Highly human-readable topic summaries | Generates detailed topic descriptions | Requires API, expensive |
| **Gensim Word2Vec**  | Training on domain-specific corpora | Customizable, good for unique vocabularies | Requires training, not great for short texts |

🔹 **Key Takeaways:**
- **For fast and simple results** → Use `TF-IDF`
- **For semantic meaning & general use** → Use `sentence-transformers`
- **For lightweight NLP pipelines** → Use `spaCy`
- **For context-aware embeddings** → Use `Flair`
- **For AI-powered topic descriptions** → Use `OpenAI`
- **For domain-specific training** → Use `Gensim`


## 📌 Choosing the Right Dimensionality Reduction Method

Reducing dimensionality improves **clustering efficiency** and **visualization** in BERTopic.

| **Method**     | **Best For**                 | **Pros**                               | **Cons**                         |
|---------------|-----------------------------|----------------------------------------|---------------------------------|
| **UMAP**      | General-purpose reduction   | Preserves structure, good for clustering | Slower on large datasets       |
| **PCA**       | Large datasets              | Fast, efficient                        | Less effective for clustering  |
| **Truncated SVD** | Sparse TF-IDF matrices     | Works well with sparse high-dimensional data | Less interpretable than UMAP |
| **TSNE**      | Visualization of small datasets | Produces clear separation in plots | Computationally expensive      |

🔹 **Key Takeaways:**
- **For most BERTopic use cases** → Use `UMAP`
- **For large-scale datasets** → Use `PCA`
- **For working with sparse TF-IDF data** → Use `Truncated SVD`
- **For high-quality visualizations** → Use `TSNE`

## 📌 Choosing the Right Clustering Algorithm

BERTopic **clusters documents** based on similarity. The choice of algorithm determines topic quality.

| **Algorithm**  | **Best For**                   | **Pros**                                 | **Cons**                       |
|---------------|--------------------------------|------------------------------------------|-------------------------------|
| **HDBSCAN**   | Default method in BERTopic    | No need to predefine clusters, handles noise | Can generate too many small topics |
| **k-Means**   | Fixed number of topics        | Fast, scalable for large datasets       | Requires predefined `k` value |
| **Agglomerative Clustering** | Hierarchical clustering | Creates a topic hierarchy, useful for structured analysis | Slower than k-Means |
| **Gaussian Mixture Models (GMM)** | Probabilistic clustering | Handles topic overlap well | Computationally expensive |

🔹 **Key Takeaways:**
- **For flexible, automatic topic detection** → Use `HDBSCAN`
- **For large datasets with predefined topics** → Use `k-Means`
- **For structured, hierarchical topics** → Use `Agglomerative Clustering`
- **For soft clustering (documents belonging to multiple topics)** → Use `GMM`

## 📌 Choosing the Right Topic Representation

BERTopic provides multiple ways to generate topic representations. Below is a comparison of different methods:

| **Method**         | **Best For**                | **Pros**                               | **Cons**                      |
|--------------------|----------------------------|----------------------------------------|--------------------------------|
| **c-TF-IDF**      | Default method              | Simple, efficient                     | Can produce repetitive words  |
| **MMR**           | Improving diversity         | Balances relevance & uniqueness       | Needs fine-tuning             |
| **KeyBERT**       | Semantic word extraction    | More natural keywords                 | Requires sentence embeddings  |
| **LLM-based**     | Human-like topic labels     | Best readability                      | API cost                      |
| **POS Filtering** | Removing stopwords         | Focuses on key terms                  | Might lose context            |
| **Custom Models** | Advanced customization      | Fully configurable for better topics  | Requires extra coding effort  |

🔹 **Key Takeaways:**
- **For fast & simple results** → Use `c-TF-IDF`
- **For more diverse keywords** → Use `MMR`
- **For meaningful, semantic keywords** → Use `KeyBERT`
- **For human-readable topic summaries** → Use `LLMs`
- **For removing unnecessary words** → Use `POS Filtering`
- **For advanced customization** → Use a **Custom Model**

🚀 **Choose the best method based on your project needs!**


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

## 🛠️ Installation
To set up the environment and run the code:
```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
pip install -r requirements.txt