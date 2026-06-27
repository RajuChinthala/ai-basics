# Types of Machine Learning

Machine learning is commonly divided into four main types based on how the model learns from data.

| Type | Training Data | Goal | Example |
|------|---------------|------|---------|
| Supervised Learning | Labeled data (inputs + correct outputs) | Predict outcomes | Spam email detection, house price prediction |
| Unsupervised Learning | Unlabeled data | Discover patterns or groups | Customer segmentation, anomaly detection |
| Semi-Supervised Learning | Small amount of labeled data + lots of unlabeled data | Improve accuracy with limited labels | Image classification with only some labeled images |
| Reinforcement Learning | Feedback in the form of rewards/penalties | Learn the best actions over time | Game-playing AI, robotics, self-driving systems |

## 1. Supervised Learning

The model learns from examples where the correct answer is already known.

**Input:** Features + Labels

**Output:** Predict labels for new data

**Common Tasks:**
- Classification (Spam vs. Not Spam)
- Regression (House Price Prediction)

**Example:**
```
Email -> Spam
Email -> Not Spam
```

The model learns the relationship and predicts whether a new email is spam.

**Common Algorithms:**
- Linear Regression
- Logistic Regression
- Decision Trees
- Random Forest
- Support Vector Machine (SVM)
- Neural Networks

---

## 2. Unsupervised Learning

The model receives data without labels and tries to find hidden structures.

**Input:** Features only

**Output:** Clusters, patterns, or reduced dimensions

**Example:**

A retailer has customer purchase histories but no customer categories. The model groups customers based on similar buying behavior.

**Common Algorithms:**
- K-Means Clustering
- DBSCAN
- Hierarchical Clustering
- Principal Component Analysis (PCA)
- Autoencoders

---

## 3. Semi-Supervised Learning

This combines supervised and unsupervised learning.

- Small portion of data is labeled.
- Large portion is unlabeled.
- The model uses both to improve prediction accuracy.

**Example:**

Out of 100,000 medical images:
- 2,000 are labeled by doctors.
- 98,000 are unlabeled.

The model uses the labeled data to learn from the much larger unlabeled dataset.

**Applications:**
- Medical Imaging
- Speech Recognition
- Image Classification

---

## 4. Reinforcement Learning

An agent learns by interacting with an environment.

Instead of labels, it receives rewards or penalties based on its actions.

```
State
   ↓
Agent → Action
   ↓
Environment
   ↓
Reward
```

**Example:**

A robot learns to walk:
- Falls → Negative Reward
- Successful Step → Positive Reward
- Eventually learns to walk efficiently.

**Common Algorithms:**
- Q-Learning
- Deep Q Networks (DQN)
- Policy Gradient
- Proximal Policy Optimization (PPO)

---

# Comparison Table

| Feature | Supervised | Unsupervised | Semi-Supervised | Reinforcement |
|---------|------------|--------------|-----------------|---------------|
| Labeled Data Required | Yes | No | Partially | No |
| Learns From | Correct Answers | Hidden Patterns | Labels + Patterns | Rewards |
| Main Goal | Prediction | Pattern Discovery | Better Prediction | Decision Making |
| Example | House Price Prediction | Customer Segmentation | Medical Image Classification | Self-Driving Cars |

## Quick Summary

- **Supervised Learning:** Learns from labeled data to make predictions.
- **Unsupervised Learning:** Finds hidden patterns in unlabeled data.
- **Semi-Supervised Learning:** Uses a small amount of labeled data with a large amount of unlabeled data.
- **Reinforcement Learning:** Learns the best actions through trial and error using rewards and penalties.


# Types of Machine Learning

Machine learning is commonly divided into four main types based on how the model learns from data.

| Type | Training Data | Goal | Example |
|------|---------------|------|---------|
| Supervised Learning | Labeled data (inputs + correct outputs) | Predict outcomes | Spam email detection, house price prediction |
| Unsupervised Learning | Unlabeled data | Discover patterns or groups | Customer segmentation, anomaly detection |
| Semi-Supervised Learning | Small amount of labeled data + lots of unlabeled data | Improve accuracy with limited labels | Image classification with only some labeled images |
| Reinforcement Learning | Feedback in the form of rewards/penalties | Learn the best actions over time | Game-playing AI, robotics, self-driving systems |

## 1. Supervised Learning

The model learns from examples where the correct answer is already known.

**Input:** Features + Labels

**Output:** Predict labels for new data

**Common Tasks:**
- Classification (Spam vs. Not Spam)
- Regression (House Price Prediction)

**Example:**
```
Email -> Spam
Email -> Not Spam
```

The model learns the relationship and predicts whether a new email is spam.

**Common Algorithms:**
- Linear Regression
- Logistic Regression
- Decision Trees
- Random Forest
- Support Vector Machine (SVM)
- Neural Networks

---

## 2. Unsupervised Learning

The model receives data without labels and tries to find hidden structures.

**Input:** Features only

**Output:** Clusters, patterns, or reduced dimensions

**Example:**

A retailer has customer purchase histories but no customer categories. The model groups customers based on similar buying behavior.

**Common Algorithms:**
- K-Means Clustering
- DBSCAN
- Hierarchical Clustering
- Principal Component Analysis (PCA)
- Autoencoders

---

## 3. Semi-Supervised Learning

This combines supervised and unsupervised learning.

- Small portion of data is labeled.
- Large portion is unlabeled.
- The model uses both to improve prediction accuracy.

**Example:**

Out of 100,000 medical images:
- 2,000 are labeled by doctors.
- 98,000 are unlabeled.

The model uses the labeled data to learn from the much larger unlabeled dataset.

**Applications:**
- Medical Imaging
- Speech Recognition
- Image Classification

---

## 4. Reinforcement Learning

An agent learns by interacting with an environment.

Instead of labels, it receives rewards or penalties based on its actions.

```
State
   ↓
Agent → Action
   ↓
Environment
   ↓
Reward
```

**Example:**

A robot learns to walk:
- Falls → Negative Reward
- Successful Step → Positive Reward
- Eventually learns to walk efficiently.

**Common Algorithms:**
- Q-Learning
- Deep Q Networks (DQN)
- Policy Gradient
- Proximal Policy Optimization (PPO)

---

# Comparison Table

| Feature | Supervised | Unsupervised | Semi-Supervised | Reinforcement |
|---------|------------|--------------|-----------------|---------------|
| Labeled Data Required | Yes | No | Partially | No |
| Learns From | Correct Answers | Hidden Patterns | Labels + Patterns | Rewards |
| Main Goal | Prediction | Pattern Discovery | Better Prediction | Decision Making |
| Example | House Price Prediction | Customer Segmentation | Medical Image Classification | Self-Driving Cars |

## Quick Summary

- **Supervised Learning:** Learns from labeled data to make predictions.
- **Unsupervised Learning:** Finds hidden patterns in unlabeled data.
- **Semi-Supervised Learning:** Uses a small amount of labeled data with a large amount of unlabeled data.
- **Reinforcement Learning:** Learns the best actions through trial and error using rewards and penalties.
