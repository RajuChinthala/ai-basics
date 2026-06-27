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


-----
# Core Components of Machine Learning

Every Machine Learning system consists of the following core components:

## 1. Dataset

A dataset is a collection of data used to train and evaluate a machine learning model.

### Types of Data
- **Training Data:** Used to train the model.
- **Validation Data:** Used to tune model parameters.
- **Test Data:** Used to evaluate the model's performance.

**Example:**

| House Size (sq ft) | Price ($) |
|--------------------|-----------|
| 1000 | 200,000 |
| 1500 | 300,000 |
| 2000 | 400,000 |

---

## 2. Features (Input Variables)

Features are the input variables that help the model make predictions.

**Examples:**
- House size
- Number of bedrooms
- Location
- Age of house

Notation:
- **X** = Features

Example:
```
X = [House Size, Bedrooms, Age]
```

---

## 3. Labels (Target Variable)

The label is the correct answer the model is trying to predict.

Notation:
- **Y** = Target Variable

Example:
```
X = House Size
Y = House Price
```

---

## 4. Model

A model is the mathematical function or algorithm that learns patterns from data and makes predictions.

Examples:
- Linear Regression
- Decision Tree
- Random Forest
- Neural Network
- Support Vector Machine (SVM)

Example:
```
Input → Model → Prediction
```

---

## 5. Algorithm

An algorithm is the learning procedure that trains the model by finding patterns in the data.

Examples:
- Gradient Descent
- Decision Tree Learning
- Backpropagation
- K-Means Clustering

---

## 6. Loss Function

A loss function measures how far the model's predictions are from the actual values.

Common Loss Functions:
- Mean Squared Error (MSE)
- Mean Absolute Error (MAE)
- Cross-Entropy Loss

Example:
```
Loss = Actual Value - Predicted Value
```

Lower loss indicates better model performance.

---

## 7. Optimizer

An optimizer updates the model's parameters to minimize the loss function.

Popular Optimizers:
- Gradient Descent
- Stochastic Gradient Descent (SGD)
- Adam
- RMSProp

Workflow:
```
Loss → Optimizer → Updated Model
```

---

## 8. Training

Training is the process of teaching the model using the training dataset.

Steps:
1. Feed training data into the model.
2. Make predictions.
3. Calculate loss.
4. Update model parameters.
5. Repeat until performance improves.

---

## 9. Evaluation

Evaluation measures how well the trained model performs on unseen data.

Common Evaluation Metrics:

### Classification
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

### Regression
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² Score

---

## 10. Prediction (Inference)

After training, the model is used to make predictions on new, unseen data.

Example:
```
New Data → Trained Model → Prediction
```

---

# Machine Learning Workflow

```
Collect Data
      │
      ▼
Preprocess Data
      │
      ▼
Feature Engineering
      │
      ▼
Select Model
      │
      ▼
Train Model
      │
      ▼
Evaluate Model
      │
      ▼
Tune Hyperparameters
      │
      ▼
Deploy Model
      │
      ▼
Make Predictions
```

---

# Summary Table

| Component | Purpose |
|-----------|---------|
| Dataset | Provides data for training and testing |
| Features | Input variables used for prediction |
| Labels | Correct output values |
| Model | Learns patterns and makes predictions |
| Algorithm | Trains the model |
| Loss Function | Measures prediction error |
| Optimizer | Minimizes the loss |
| Training | Teaches the model |
| Evaluation | Measures model performance |
| Prediction | Uses the trained model on new data |

