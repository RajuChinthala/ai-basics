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


-----
# Skewed Data

Skewed data refers to a dataset in which the values are **not evenly distributed around the mean**. Instead of forming a symmetrical (bell-shaped) distribution, the data has a **longer tail on one side**.

Many machine learning algorithms assume that data follows a normal (Gaussian) distribution. Highly skewed data can affect model performance and statistical analysis.

---

## Types of Skewness

### 1. Positive Skew (Right-Skewed)

In a positively skewed distribution, the **tail extends to the right**. Most values are concentrated on the left, with a few very large values.

Characteristics:
- Mean > Median > Mode
- Contains high-value outliers

**Examples:**
- Income distribution
- House prices
- Online product sales

```
Frequency
 ^
 |        ###
 |      ######
 |    #########
 |  ##########
 |##########
 +------------------------> Value
                     ------>
                    Long Right Tail
```

---

### 2. Negative Skew (Left-Skewed)

In a negatively skewed distribution, the **tail extends to the left**. Most values are concentrated on the right, with a few very small values.

Characteristics:
- Mean < Median < Mode
- Contains low-value outliers

**Examples:**
- Easy exam scores
- Customer satisfaction ratings

```
Frequency
 ^
 |          ##########
 |        ###########
 |      ##########
 |    #######
 |  ###
 +------------------------> Value
 <------
Long Left Tail
```

---

## Why is Skewed Data a Problem?

Skewed data can:

- Reduce the accuracy of some machine learning models.
- Affect statistical measures such as the mean and standard deviation.
- Cause features with extreme values to dominate the learning process.
- Violate assumptions of algorithms that expect normally distributed data.

---

## How to Handle Skewed Data

Several techniques can reduce skewness:

### 1. Log Transformation

Useful for reducing positive skew.

```
New Value = log(x)
```

Example:

| Original | Log Value |
|----------|-----------|
| 10 | 1.00 |
| 100 | 2.00 |
| 1000 | 3.00 |

---

### 2. Square Root Transformation

Useful for moderately skewed data.

```
New Value = √x
```

---

### 3. Box-Cox Transformation

Applies a power transformation to make positive data more normally distributed.

---

### 4. Yeo-Johnson Transformation

Similar to Box-Cox but works with both positive and negative values.

---

### 5. Remove or Treat Outliers

If skewness is caused by a few extreme values, removing or capping outliers may reduce the skew.

---

## Example

Original salaries:

```
30,000
35,000
40,000
42,000
45,000
50,000
500,000
```

The salary **500,000** creates a positive (right) skew because it is much larger than the other values.

---

## Summary

| Type | Tail Direction | Relationship |
|------|----------------|--------------|
| Positive Skew | Right | Mean > Median > Mode |
| Negative Skew | Left | Mean < Median < Mode |

**Key Point:**  
Skewed data is data that is **asymmetrical**, meaning one side of the distribution has a longer tail than the other. Detecting and correcting skewness can improve the performance of machine learning models and statistical analyses.


# Feature Scaling

Feature scaling is the process of transforming numerical features so that they are on a similar scale. It prevents features with larger values from dominating those with smaller values and helps many machine learning algorithms perform better.

The two most common feature scaling techniques are:

- **Min-Max Scaling (Normalization)**
- **Z-Score Normalization (Standardization)**

---

# 1. Min-Max Scaling (Normalization)

Min-Max Scaling rescales feature values to a fixed range, typically **0 to 1**.

## Formula

```text
Scaled Value = (x - xmin) / (xmax - xmin)
```

Where:

- **x** = Original value
- **xmin** = Minimum value in the feature
- **xmax** = Maximum value in the feature

---

## Example

Suppose the **Age** feature contains:

| Age |
|----:|
| 20 |
| 25 |
| 30 |
| 35 |
| 40 |

- Minimum (xmin) = **20**
- Maximum (xmax) = **40**

Normalize the value **30**:

```text
Scaled Value = (30 - 20) / (40 - 20)
             = 10 / 20
             = 0.50
```

### Result

| Original Age | Normalized Age |
|-------------:|---------------:|
| 20 | 0.00 |
| 25 | 0.25 |
| 30 | 0.50 |
| 35 | 0.75 |
| 40 | 1.00 |

### Advantages

- Simple and easy to implement.
- Scales all features to the same range.
- Works well with distance-based algorithms.

### Disadvantages

- Sensitive to outliers.
- Extreme values can compress the remaining data.

### Common Algorithms

- K-Nearest Neighbors (KNN)
- K-Means Clustering
- Neural Networks


----
# Data Splitting Techniques

Data splitting is the process of dividing a dataset into separate subsets for training, validating, and testing a machine learning model. Splitting the data helps evaluate how well the model performs on unseen data and reduces the risk of overfitting.

---

# Why Split the Data?

Data splitting helps to:

- Train the model using one portion of the data.
- Tune model parameters without using the test data.
- Evaluate the model on unseen data.
- Measure how well the model generalizes to new data.

---

# Common Data Splitting Techniques

## 1. Train-Test Split

The dataset is divided into two parts:

- **Training Set:** Used to train the model.
- **Test Set:** Used to evaluate the model's performance.

### Common Split Ratios

- 80% Training / 20% Testing
- 70% Training / 30% Testing
- 75% Training / 25% Testing

### Example

Dataset: **1000 records**

| Dataset | Records |
|---------|--------:|
| Training Set | 800 |
| Test Set | 200 |

### Advantages

- Simple and fast.
- Suitable for large datasets.

### Disadvantages

- Model performance depends on one random split.
- May not represent the entire dataset well.

---

## 2. Train-Validation-Test Split

The dataset is divided into three subsets:

- **Training Set:** Used to train the model.
- **Validation Set:** Used to tune hyperparameters and select the best model.
- **Test Set:** Used to evaluate the final model.

### Common Split Ratios

- 70% Training / 15% Validation / 15% Testing
- 80% Training / 10% Validation / 10% Testing

### Example

Dataset: **1000 records**

| Dataset | Records |
|---------|--------:|
| Training Set | 700 |
| Validation Set | 150 |
| Test Set | 150 |

### Advantages

- Provides an unbiased evaluation.
- Prevents using the test set during model tuning.

### Disadvantages

- Requires more data.
- Smaller training dataset compared to Train-Test Split.

---

## 3. K-Fold Cross Validation

K-Fold Cross Validation divides the dataset into **K equal-sized folds**.

The model is trained **K times**, each time using:

- **K − 1 folds** for training.
- **1 fold** for testing.

The final performance is the average of all K runs.

### Example (5-Fold Cross Validation)

```
Fold 1 : Test | Train | Train | Train | Train
Fold 2 : Train | Test | Train | Train | Train
Fold 3 : Train | Train | Test | Train | Train
Fold 4 : Train | Train | Train | Test | Train
Fold 5 : Train | Train | Train | Train | Test
```

### Common Values

- K = 5
- K = 10

### Advantages

- More reliable evaluation.
- Uses the entire dataset for both training and testing.
- Reduces bias caused by a single split.

### Disadvantages

- Computationally expensive.
- Training takes longer.

---

## 4. Stratified Sampling

Stratified Sampling ensures that each dataset split has the **same class distribution** as the original dataset.

This technique is mainly used for **classification problems**, especially when the dataset is imbalanced.

### Example

Original Dataset

| Class | Percentage |
|--------|-----------:|
| Yes | 90% |
| No | 10% |

After splitting, both the training and testing sets maintain the same 90:10 ratio.

### Advantages

- Preserves class distribution.
- Improves evaluation for imbalanced datasets.

### Disadvantages

- Applicable only to classification problems.

---

## 5. Leave-One-Out Cross Validation (LOOCV)

Leave-One-Out Cross Validation is a special case of K-Fold Cross Validation where:

- **K = Number of samples**

Each iteration:

- One sample is used for testing.
- All remaining samples are used for training.

### Example

Dataset with 5 records

```
Iteration 1
Test : Record 1
Train: Records 2,3,4,5

Iteration 2
Test : Record 2
Train: Records 1,3,4,5

...

Iteration 5
Test : Record 5
Train: Records 1,2,3,4
```

### Advantages

- Uses nearly all data for training.
- Very accurate for small datasets.

### Disadvantages

- Extremely slow for large datasets.
- Computationally expensive.

---

# Comparison of Data Splitting Techniques

| Technique | Training Data | Validation Data | Test Data | Best For |
|-----------|---------------|-----------------|-----------|----------|
| Train-Test Split | ✓ | ✗ | ✓ | Large datasets |
| Train-Validation-Test Split | ✓ | ✓ | ✓ | Model tuning |
| K-Fold Cross Validation | ✓ | Multiple folds | ✓ | Small to medium datasets |
| Stratified Sampling | ✓ | Optional | ✓ | Imbalanced classification datasets |
| Leave-One-Out Cross Validation | ✓ | ✗ | One sample at a time | Very small datasets |

---

# Summary

| Technique | Purpose |
|-----------|---------|
| Train-Test Split | Simple evaluation using one split |
| Train-Validation-Test Split | Model training, tuning, and final evaluation |
| K-Fold Cross Validation | Reliable performance estimation using multiple splits |
| Stratified Sampling | Maintains class distribution during splitting |
| Leave-One-Out Cross Validation | Uses almost all data for training and tests one sample at a time |

---

# 2. Z-Score Normalization (Standardization)

Z-Score Normalization transforms data so that it has:

- **Mean = 0**
- **Standard Deviation = 1**

Instead of scaling values to a fixed range, it measures how many standard deviations a value is from the mean.

## Formula

```text
z = (x - μ) / σ
```

Where:

- **z** = Standardized value
- **x** = Original value
- **μ (mu)** = Mean of the feature
- **σ (sigma)** = Standard deviation of the feature

---

## Example

Suppose the **Age** feature contains:

| Age |
|----:|
| 20 |
| 25 |
| 30 |
| 35 |
| 40 |

- Mean (μ) = **30**
- Standard Deviation (σ) ≈ **7.07**

Standardize the value **35**:

```text
z = (35 - 30) / 7.07
  = 5 / 7.07
  ≈ 0.71
```

### Result

| Original Age | Z-Score |
|-------------:|--------:|
| 20 | -1.41 |
| 25 | -0.71 |
| 30 | 0.00 |
| 35 | 0.71 |
| 40 | 1.41 |

### Interpretation

- **z = 0** → Value is equal to the mean.
- **z > 0** → Value is above the mean.
- **z < 0** → Value is below the mean.
- **|z| > 3** → Often considered an outlier.

### Advantages

- Less sensitive to outliers than Min-Max Scaling.
- Centers data around zero.
- Works well when data follows a normal distribution.

### Disadvantages

- Does not limit values to a fixed range.
- Values can be greater than 1 or less than -1.

### Common Algorithms

- Linear Regression
- Logistic Regression
- Support Vector Machines (SVM)
- Principal Component Analysis (PCA)
- K-Means Clustering

---

# Min-Max Scaling vs. Z-Score Normalization

| Feature | Min-Max Scaling | Z-Score Normalization |
|---------|------------------|-----------------------|
| Formula | `(x - xmin) / (xmax - xmin)` | `(x - μ) / σ` |
| Output Range | 0 to 1 | No fixed range |
| Mean After Scaling | Not fixed | 0 |
| Standard Deviation | Not fixed | 1 |
| Sensitive to Outliers | Yes | Less sensitive |
| Best For | KNN, Neural Networks | Regression, SVM, PCA |

---

# Summary

| Technique | Purpose | Output Range | Best Used For |
|-----------|---------|--------------|---------------|
| **Min-Max Scaling** | Rescales data to a fixed range | Usually 0 to 1 | Distance-based algorithms like KNN and Neural Networks |
| **Z-Score Normalization** | Centers data around the mean with a standard deviation of 1 | No fixed range | Algorithms that assume normally distributed data such as SVM, PCA, and Regression |
