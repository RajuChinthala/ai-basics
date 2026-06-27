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

-------------
# Core Components of Machine Learning

## 1. Representation (What is the model?)

Representation defines **how the machine learning model represents the relationship between inputs and outputs**. In other words, it specifies the hypothesis space—the set of possible models the algorithm can learn.

### Examples
- Linear Regression
- Logistic Regression
- Decision Trees
- Random Forest
- Support Vector Machines (SVM)
- Neural Networks

**Example:**

Predicting house prices:

```
House Size → Linear Regression → Price
```

Here, **Linear Regression** is the representation.

---

## 2. Evaluation (How do we measure performance?)

Evaluation defines **how we determine whether a model is performing well**. It uses a loss function during training and evaluation metrics after training.

### Common Evaluation Metrics

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

**Example:**

Actual Price = $250,000

Predicted Price = $240,000

Error = $10,000

The evaluation metric tells us how good or bad the prediction is.

---

## 3. Optimization (How does the model learn?)

Optimization is the process of **finding the best model parameters by minimizing the loss function**.

The optimizer repeatedly:
1. Makes predictions.
2. Calculates the loss.
3. Updates model parameters.
4. Repeats until the loss is minimized.

### Common Optimization Algorithms
- Gradient Descent
- Stochastic Gradient Descent (SGD)
- Mini-Batch Gradient Descent
- Adam
- RMSProp

**Example:**

```
Training Data
      │
      ▼
   Model
      │
      ▼
 Prediction
      │
      ▼
 Loss Function
      │
      ▼
 Optimizer
      │
      ▼
 Updated Model
```

---

# Summary Table

| Component | Question Answered | Examples |
|-----------|-------------------|----------|
| **Representation** | What kind of model will be used? | Linear Regression, Decision Tree, Neural Network |
| **Evaluation** | How do we measure model performance? | Accuracy, F1 Score, MSE, RMSE |
| **Optimization** | How do we improve the model? | Gradient Descent, Adam, SGD |

## Easy Way to Remember

- **Representation** → **What to learn?** (The model)
- **Evaluation** → **How good is it?** (Metrics/Loss)
- **Optimization** → **How to improve it?** (Learning algorithm)

-------
# Data Pre-processing

Data pre-processing is the process of cleaning, transforming, and preparing raw data before training a machine learning model. High-quality data helps improve model accuracy, reduce errors, and speed up the learning process.

---

## Components of Data Pre-processing

### 1. Data Quality

Data quality refers to the condition of the dataset. A high-quality dataset should be:

- Accurate
- Complete
- Consistent
- Relevant
- Free from duplicate or incorrect records

Poor data quality can lead to inaccurate predictions and poor model performance.

---

### 2. Missing Data

Missing data occurs when one or more values are absent from the dataset. Handling missing values is important because many machine learning algorithms cannot work with incomplete data.

#### Common Techniques

- **Remove Rows:** Delete records containing missing values when only a small number of rows are affected.
- **Remove Columns:** Remove an entire feature if it contains too many missing values or is not important for prediction.
- **Fill Missing Values (Imputation):** Replace missing values using the mean, median, mode, or another suitable value.

**Example:**

| Name | Age | Salary |
|------|-----|--------|
| Alice | 25 | 50000 |
| Bob | - | 60000 |
| Charlie | 30 | 55000 |

The missing age for Bob can be replaced with the average age or the row/column can be removed depending on its importance.

---

### 3. Detecting Outliers

Outliers are data points that differ significantly from the rest of the dataset. They may result from data entry errors, measurement errors, or rare events.

Detecting outliers helps improve model accuracy and prevents unusual values from negatively affecting the learning process.

#### Common Methods

##### Z-Score (Standard Score)

The Z-score measures how many standard deviations a data point is from the mean.

- A value with a **Z-score greater than +3 or less than -3** is commonly considered an outlier.

##### Interquartile Range (IQR)

The IQR method identifies outliers using the spread of the middle 50% of the data.

Steps:
1. Calculate the first quartile (Q1) and third quartile (Q3).
2. Compute the Interquartile Range:
   ```
   IQR = Q3 - Q1
   ```
3. Calculate the bounds:
   ```
   Lower Bound = Q1 - 1.5 × IQR
   Upper Bound = Q3 + 1.5 × IQR
   ```
4. Values outside these bounds are considered outliers.

---

### 4. Encoding

Machine learning models require numerical input. Encoding converts categorical (text) data into numerical values.

#### Common Encoding Techniques

- **Label Encoding:** Assigns a unique integer to each category.
- **One-Hot Encoding:** Creates a separate binary column for each category.

**Example:**

| Color | Label Encoding |
|--------|----------------|
| Red | 0 |
| Blue | 1 |
| Green | 2 |

**One-Hot Encoding**

| Color | Red | Blue | Green |
|--------|-----|------|-------|
| Red | 1 | 0 | 0 |
| Blue | 0 | 1 | 0 |
| Green | 0 | 0 | 1 |

---

### 5. Feature Scaling

Feature scaling transforms numerical features so they have a similar range. This prevents features with larger values from dominating those with smaller values.

Scaling is especially important for algorithms that rely on distance calculations, such as K-Nearest Neighbors (KNN), Support Vector Machines (SVM), and K-Means clustering.

#### Common Scaling Techniques

- **Min-Max Scaling:** Scales values to a fixed range, usually **0 to 1**.
- **Standardization (Z-Score Normalization):** Centers data around a mean of 0 with a standard deviation of 1.

---

### 6. Splitting Data

Before training a model, the dataset is divided into separate subsets to evaluate how well the model generalizes to unseen data.

#### Common Data Splits

- **Training Set (70–80%)** – Used to train the model.
- **Validation Set (10–15%)** – Used to tune model parameters and select the best model.
- **Test Set (10–20%)** – Used to evaluate the final model's performance on unseen data.

**Example:**

Dataset (1000 samples)

- Training Set: 800 samples
- Validation Set: 100 samples
- Test Set: 100 samples

---

## Data Pre-processing Workflow

```
Raw Data
    │
    ▼
Check Data Quality
    │
    ▼
Handle Missing Data
    │
    ▼
Detect & Treat Outliers
    │
    ▼
Encode Categorical Data
    │
    ▼
Scale Numerical Features
    │
    ▼
Split Dataset
    │
    ▼
Ready for Model Training
```

---

## Summary

| Component | Purpose |
|-----------|---------|
| Data Quality | Ensures data is accurate, complete, and consistent |
| Missing Data | Handles incomplete values by removing or imputing them |
| Detecting Outliers | Identifies unusual data points that may affect model performance |
| Encoding | Converts categorical data into numerical format |
| Feature Scaling | Normalizes feature values to a similar range |
| Splitting Data | Divides data into training, validation, and test sets |
