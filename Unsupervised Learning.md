# Unsupervised Learning

Unsupervised Learning is a type of machine learning in which the model is trained using **unlabeled data**. Unlike supervised learning, there are **no predefined output labels**. The goal is to discover hidden patterns, relationships, or structures within the data.

The model learns by analyzing the similarities and differences among data points without any prior knowledge of the correct answers.

---

# How Unsupervised Learning Works

1. Collect unlabeled data.
2. Select an unsupervised learning algorithm.
3. Train the model to discover hidden patterns.
4. Group similar data points or reduce data dimensions.
5. Analyze the discovered patterns for insights.

```text
Unlabeled Data
      │
      ▼
Train Model
      │
      ▼
Discover Hidden Patterns
      │
      ▼
Clusters / Relationships / Reduced Dimensions
```

---

# Types of Unsupervised Learning

## 1. Clustering

Clustering groups similar data points into clusters based on their characteristics. Data points within the same cluster are more similar to each other than to those in other clusters.

### Applications

* Customer Segmentation
* Market Basket Analysis
* Document Clustering
* Image Segmentation
* Social Network Analysis

### Common Clustering Algorithms

* K-Means Clustering
* Hierarchical Clustering
* DBSCAN (Density-Based Spatial Clustering)
* Mean Shift
* Gaussian Mixture Models (GMM)

---

## 2. Association Rule Learning

Association Rule Learning discovers relationships or associations between variables in a dataset.

It is commonly used to identify items that frequently occur together.

### Applications

* Market Basket Analysis
* Product Recommendation
* Cross-selling
* Inventory Planning

### Example

Customers who buy:

```
Bread → Butter
Milk → Bread
Bread + Butter → Jam
```

The algorithm discovers that customers who buy **Bread** often buy **Butter**.

### Common Algorithms

* Apriori Algorithm
* FP-Growth
* ECLAT

---

## 3. Dimensionality Reduction

Dimensionality Reduction reduces the number of input features while preserving the important information in the dataset.

This technique helps simplify data, reduce computational cost, and improve visualization.

### Applications

* Data Visualization
* Noise Reduction
* Feature Extraction
* Image Compression
* Preprocessing for Machine Learning

### Common Algorithms

* Principal Component Analysis (PCA)
* t-Distributed Stochastic Neighbor Embedding (t-SNE)
* Uniform Manifold Approximation and Projection (UMAP)
* Autoencoders

---

# Unsupervised Learning Models

A model in unsupervised learning identifies hidden structures or relationships within unlabeled data.

### Common Models

| Model                   | Purpose                                   |
| ----------------------- | ----------------------------------------- |
| K-Means                 | Groups similar data into K clusters       |
| Hierarchical Clustering | Builds a hierarchy of clusters            |
| DBSCAN                  | Finds clusters based on data density      |
| PCA                     | Reduces the number of features            |
| Apriori                 | Discovers frequent item associations      |
| Autoencoder             | Learns compressed representations of data |

---

# Unsupervised Learning Algorithms

| Algorithm               | Description                                                           |
| ----------------------- | --------------------------------------------------------------------- |
| K-Means                 | Partitions data into K clusters based on similarity.                  |
| Hierarchical Clustering | Creates a tree-like hierarchy of clusters.                            |
| DBSCAN                  | Detects clusters based on density and identifies noise.               |
| PCA                     | Reduces feature dimensions while retaining important information.     |
| Apriori                 | Finds frequent itemsets and association rules.                        |
| FP-Growth               | Efficiently discovers frequent patterns without candidate generation. |
| Autoencoder             | Uses neural networks to learn compact data representations.           |

---

# Applications of Unsupervised Learning

* Customer Segmentation
* Fraud Detection
* Recommendation Systems
* Market Basket Analysis
* Document Clustering
* Image Compression
* Topic Modeling
* Anomaly Detection
* Social Network Analysis
* Gene Sequence Analysis

---

# Advantages

* Does not require labeled data.
* Can discover hidden patterns and relationships.
* Useful for exploratory data analysis.
* Helps reduce data complexity through dimensionality reduction.

---

# Disadvantages

* Computational Complexity - Due to massive datasets sizes & Difficult to evaluate because there are no true labels.
* Longer Training Times - Algorithms need multiple restarts
* High Risk of Inaccurate Results - no ground trugh to check against.
* Human Intervention Required - experts must interpret clusters
* Lack of Transparency - high-dimentional results can't be explained.
* 
* Results may be harder to interpret.
* Sensitive to algorithm choice and parameter settings.
* Different algorithms may produce different groupings for the same data.

---

# Supervised vs. Unsupervised Learning

| Feature       | Supervised Learning        | Unsupervised Learning                             |
| ------------- | -------------------------- | ------------------------------------------------- |
| Training Data | Labeled                    | Unlabeled                                         |
| Goal          | Predict outputs            | Discover hidden patterns                          |
| Output        | Labels or numerical values | Clusters, associations, reduced dimensions        |
| Common Tasks  | Classification, Regression | Clustering, Association, Dimensionality Reduction |
| Example       | Email Spam Detection       | Customer Segmentation                             |

---

# Summary

| Feature           | Description                                                                              |
| ----------------- | ---------------------------------------------------------------------------------------- |
| Learning Type     | Learns from unlabeled data                                                               |
| Input             | Features only (X)                                                                        |
| Output            | Clusters, associations, or reduced dimensions                                            |
| Main Tasks        | Clustering, Association Rule Learning, Dimensionality Reduction                          |
| Common Algorithms | K-Means, Hierarchical Clustering, DBSCAN, PCA, Apriori, FP-Growth, Autoencoders          |
| Applications      | Customer Segmentation, Market Basket Analysis, Recommendation Systems, Anomaly Detection |

------
# Clustering Technique Comparison

| Technique | Hard / Soft | Need K Upfront? | Handles Non-Spherical Clusters? | Scalability | Best For |
|-----------|-------------|-----------------|---------------------------------|------------|----------|
| **K-Means** | Hard | ✅ Yes | ❌ No (Spherical clusters only) | 🟢 High – O(n × k × d × i) | Large, well-separated spherical clusters |
| **Elbow Method** | Tool | ❌ No | N/A | 🔴 Low (Runs K-Means multiple times) | Selecting the optimal value of K |
| **Hierarchical Clustering** | Hard | ❌ No | ✅ Yes | 🔴 Low – O(n² log n) | Small datasets and hierarchical relationships |
| **Dendrogram** | Visualization | ❌ No | ✅ Yes | 🔴 Low | Visualizing cluster hierarchy and choosing clusters |
| **Gaussian Mixture Model (GMM)** | Soft | ✅ Yes | ✅ Yes (Elliptical clusters) | 🟡 Medium | Overlapping or probabilistic clusters |
| **Fuzzy C-Means** | Soft | ✅ Yes | ⚠️ Partially | 🟡 Medium | Data with ambiguous cluster boundaries |
| **DBSCAN** | Hard | ❌ No | ✅ Yes | 🟢 High (Average O(n log n)) | Arbitrary-shaped clusters and outlier detection |
| **Mean Shift** | Soft | ❌ No | ✅ Yes | 🔴 Low | Automatically finding clusters without specifying K |
| **OPTICS** | Hard | ❌ No | ✅ Yes | 🟡 Medium | Clusters with varying densities |
| **Agglomerative Clustering** | Hard | ❌ No | ✅ Yes | 🔴 Low – O(n²) | Small datasets and hierarchical clustering |

---

## Legend

- **Hard Clustering:** Each data point belongs to exactly one cluster.
- **Soft Clustering:** A data point can belong to multiple clusters with different probabilities or membership values.
- **Need K Upfront:** Indicates whether the number of clusters (**K**) must be specified before training.
- **Non-Spherical Clusters:** Indicates whether the algorithm can detect clusters with irregular or arbitrary shapes.
- **Scalability:** Describes how efficiently the algorithm handles large datasets.

---

## Summary

| Algorithm | Strength | Limitation |
|-----------|----------|------------|
| **K-Means** | Fast and simple | Requires K and assumes spherical clusters |
| **Hierarchical Clustering** | Produces cluster hierarchy | Not suitable for large datasets |
| **DBSCAN** | Detects arbitrary-shaped clusters and outliers | Sensitive to parameter selection |
| **GMM** | Handles overlapping clusters | Computationally expensive |
| **Fuzzy C-Means** | Allows partial cluster membership | Requires K and more computation |
| **Mean Shift** | Automatically determines the number of clusters | Slow for large datasets |
| **OPTICS** | Handles varying-density clusters | More complex than DBSCAN |
