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
# Types of Points in DBSCAN

DBSCAN (Density-Based Spatial Clustering of Applications with Noise) classifies each data point into one of three categories based on the density of its surrounding neighborhood.

The three types of points are:

- Core Point
- Border Point
- Noise (Outlier) Point

DBSCAN uses two parameters:

- **ε (Epsilon):** The radius used to search for neighboring points.
- **MinPts:** The minimum number of points required within the ε-neighborhood to form a dense region.

---

# 1. Core Point

A **Core Point** is a point that has at least **MinPts** points (including itself) within its ε-neighborhood.

## Characteristics

- Forms the center of a cluster.
- Can directly reach other nearby points.
- Expands the cluster by connecting neighboring points.

### Example

Suppose:

- ε = 2
- MinPts = 5

If Point **A** has **6 points** within its ε-neighborhood, then:

```text
Point A → Core Point
```

---

# 2. Border Point

A **Border Point** has fewer than **MinPts** neighbors within its ε-neighborhood but lies within the ε-neighborhood of a Core Point.

## Characteristics

- Belongs to a cluster.
- Cannot create or expand a cluster.
- Connected to a cluster through a Core Point.

### Example

```text
Core Point
     ●
   / | \
  ●  ●  ○
        ↑
   Border Point
```

The border point belongs to the cluster because it is reachable from the core point.

---

# 3. Noise Point (Outlier)

A **Noise Point** is a point that is **not within the ε-neighborhood of any Core Point** and does not satisfy the conditions to be a Core Point or Border Point.

## Characteristics

- Does not belong to any cluster.
- Considered an outlier or anomaly.
- Ignored during cluster formation.

### Example

```text
Cluster

● ● ● ● ●

          ○

      Noise Point
```

---

# Visual Representation

```text
           ε Neighborhood

          ●   ●
       ●   C   ●
          ●   ●

C = Core Point

--------------------------

        C
      / | \
     ●  ●  B

B = Border Point

--------------------------

Cluster

● ● ● ● ●

          N

N = Noise Point
```

---

# Comparison of DBSCAN Point Types

| Point Type | Minimum Neighbors (MinPts) | Belongs to Cluster | Can Expand Cluster | Description |
|------------|----------------------------|--------------------|--------------------|-------------|
| Core Point | ≥ MinPts | ✅ Yes | ✅ Yes | Dense point that forms the center of a cluster |
| Border Point | < MinPts | ✅ Yes | ❌ No | Connected to a Core Point but cannot expand the cluster |
| Noise Point | < MinPts | ❌ No | ❌ No | Outlier that does not belong to any cluster |

---

# Summary

| Point Type | Role |
|------------|------|
| **Core Point** | Starts and expands clusters. |
| **Border Point** | Belongs to a cluster but cannot create or expand it. |
| **Noise Point** | Considered an outlier and excluded from clusters. |

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

------------
# Distance Metrics

Distance metrics measure the similarity or dissimilarity between two data points. They are widely used in machine learning algorithms such as K-Nearest Neighbors (KNN), K-Means Clustering, Hierarchical Clustering, and DBSCAN.

Choosing the appropriate distance metric can significantly impact the performance of a machine learning model.

---

# Common Distance Metrics

## 1. Euclidean Distance

Euclidean Distance measures the straight-line distance between two points in Euclidean space.

### Formula

```text
d(x, y) = √Σ(xi - yi)²
```

### Characteristics

- Most commonly used distance metric.
- Works well with continuous numerical data.
- Sensitive to feature scaling.

### Applications

- K-Means Clustering
- K-Nearest Neighbors (KNN)
- Hierarchical Clustering

---

## 2. Manhattan Distance

Manhattan Distance measures the distance by moving only horizontally and vertically (city-block distance).

### Formula

```text
d(x, y) = Σ|xi - yi|
```

### Characteristics

- Less sensitive to outliers than Euclidean distance.
- Suitable when movement is restricted to grid-like paths.

### Applications

- KNN
- Clustering
- High-dimensional datasets

---

## 3. Minkowski Distance

Minkowski Distance is a generalized distance metric that includes both Euclidean and Manhattan distances.

### Formula

```text
d(x, y) = (Σ|xi - yi|ᵖ)^(1/p)
```

Where:

- **p = 1** → Manhattan Distance
- **p = 2** → Euclidean Distance

### Applications

- KNN
- General-purpose distance calculations

---

## 4. Chebyshev Distance

Chebyshev Distance measures the maximum absolute difference between any pair of coordinates.

### Formula

```text
d(x, y) = max(|xi - yi|)
```

### Characteristics

- Focuses on the largest difference.
- Useful when the maximum deviation is important.

### Applications

- Chessboard movement
- Quality control

---

## 5. Cosine Distance

Cosine Distance measures the angle between two vectors rather than the actual distance.

### Formula

```text
Cosine Similarity = (A · B) / (||A|| × ||B||)

Cosine Distance = 1 - Cosine Similarity
```

### Characteristics

- Ignores vector magnitude.
- Measures orientation instead of distance.

### Applications

- Text Mining
- Document Similarity
- Recommendation Systems
- NLP

---

## 6. Hamming Distance

Hamming Distance counts the number of positions where two categorical or binary vectors differ.

### Example

```text
101101
100111
------
Difference = 2
```

### Applications

- Error Detection
- DNA Sequence Analysis
- Binary Classification

---

## 7. Jaccard Distance

Jaccard Distance measures dissimilarity between two sets.

### Formula

```text
Jaccard Similarity = |A ∩ B| / |A ∪ B|

Jaccard Distance = 1 - Jaccard Similarity
```

### Applications

- Recommendation Systems
- Text Analysis
- Market Basket Analysis

---

# Comparison of Distance Metrics

| Distance Metric | Formula | Data Type | Sensitive to Scale | Best For | Common Algorithms |
|-----------------|---------|-----------|--------------------|----------|-------------------|
| Euclidean | √Σ(xi−yi)² | Numerical | ✅ Yes | Straight-line distance | K-Means, KNN |
| Manhattan | Σ|xi−yi| | Numerical | ✅ Yes | Grid-based movement | KNN, Clustering |
| Minkowski | (Σ|xi−yi|ᵖ)¹/ᵖ | Numerical | ✅ Yes | General-purpose distance | KNN |
| Chebyshev | max(|xi−yi|) | Numerical | ✅ Yes | Maximum difference | Quality Control |
| Cosine | 1 − Cosine Similarity | Vectors | ❌ No | Text similarity | NLP, Recommendation Systems |
| Hamming | Count of differing positions | Binary/Categorical | ❌ No | Binary data | Error Detection |
| Jaccard | 1 − (Intersection / Union) | Sets/Binary | ❌ No | Set similarity | Recommendation Systems |

---

# Distance Metrics Used by Machine Learning Algorithms

| Algorithm | Common Distance Metric |
|-----------|------------------------|
| K-Means | Euclidean |
| K-Nearest Neighbors (KNN) | Euclidean, Manhattan, Minkowski |
| Hierarchical Clustering | Euclidean, Manhattan |
| DBSCAN | Euclidean, Manhattan, Minkowski |
| Gaussian Mixture Model (GMM) | Mahalanobis (internally considers covariance) |
| Recommendation Systems | Cosine, Jaccard |
| Text Mining | Cosine |
| Binary Classification | Hamming |

---

# Advantages and Disadvantages

| Distance Metric | Advantages | Disadvantages |
|-----------------|------------|---------------|
| Euclidean | Simple and widely used | Sensitive to scale and outliers |
| Manhattan | Robust to some outliers | Less suitable for diagonal distances |
| Minkowski | Flexible (generalizes Euclidean and Manhattan) | Choice of parameter **p** affects results |
| Chebyshev | Captures maximum deviation | Ignores smaller differences |
| Cosine | Works well for high-dimensional sparse data | Ignores magnitude |
| Hamming | Ideal for binary and categorical data | Not suitable for continuous data |
| Jaccard | Measures similarity between sets | Not suitable for numerical data |

---

# Summary

| Metric | Best Used For |
|--------|---------------|
| Euclidean | Continuous numerical data |
| Manhattan | Grid-based or high-dimensional numerical data |
| Minkowski | General numerical distance |
| Chebyshev | Maximum coordinate difference |
| Cosine | Text similarity and document comparison |
| Hamming | Binary and categorical data |
| Jaccard | Set and binary similarity |

------
<img width="1060" height="430" alt="image" src="https://github.com/user-attachments/assets/2d9c775d-4b50-48b6-bfef-17d1991fae2f" />

