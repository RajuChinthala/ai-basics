# CNN (Convolutional Neural Network) – Simple Notes

## 1. What is CNN?

**CNN stands for Convolutional Neural Network.**

CNN is a deep learning model mainly used for **images**.

It can learn features such as:

* Edges
* Lines
* Shapes
* Textures
* Object parts
* Complete objects

Example:

```text
Image
  ↓
CNN
  ↓
Feature Extraction
  ↓
Prediction
```

For example:

```text
Cat Image
   ↓
CNN
   ↓
Cat
```

---

# 2. Where is CNN Used?

CNN is mainly used in computer vision.

Common applications:

* Image classification
* Object detection
* Face recognition
* Medical image analysis
* Self-driving cars
* OCR
* Image segmentation

Example:

```text
Image Classification

Image
 ↓
CNN
 ↓
Cat / Dog / Car
```

---

# 3. CNN Architecture

This is the basic CNN architecture:

```text
Input Image
     ↓
Convolution
     ↓
ReLU
     ↓
Pooling
     ↓
Convolution
     ↓
ReLU
     ↓
Pooling
     ↓
Flatten / Global Average Pooling
     ↓
Dense Layer
     ↓
Output Layer
     ↓
Prediction
```

Easy way to remember:

```text
IMAGE
  ↓
CONV
  ↓
RELU
  ↓
POOL
  ↓
CONV
  ↓
RELU
  ↓
POOL
  ↓
FLATTEN
  ↓
DENSE
  ↓
OUTPUT
```

---

# 4. CNN Has Two Main Parts

```text
CNN
│
├── Feature Extraction
│      ├── Convolution
│      ├── ReLU
│      └── Pooling
│
└── Classification
       ├── Flatten
       ├── Dense
       └── Output
```

### Feature Extraction

CNN finds important features from the image.

Example:

```text
Image
 ↓
Edges
 ↓
Shapes
 ↓
Object Parts
 ↓
High-Level Features
```

### Classification

CNN uses those features to predict the object.

```text
Features
   ↓
Dense Layer
   ↓
Cat / Dog / Car
```

---

# 5. Image Representation

A computer sees an image as numbers.

## Grayscale Image

A grayscale image has:

```text
1 Channel
```

Example:

```text
[
 [10, 20, 30],
 [40, 50, 60],
 [70, 80, 90]
]
```

Usually:

```text
0   = Black
255 = White
```

## RGB Image

A color image usually has:

```text
3 Channels
```

They are:

```text
Red
Green
Blue
```

Example image size:

```text
224 × 224 × 3
```

Meaning:

```text
224 = Height
224 = Width
3   = RGB channels
```

---

# 6. Convolution

Convolution is the main operation in CNN.

A small matrix called a **filter** or **kernel** moves over the image.

Example:

```text
Image
  ↓
3 × 3 Filter
  ↓
Convolution
  ↓
Feature Map
```

The filter helps detect patterns such as:

```text
Edges
Lines
Curves
Textures
Shapes
```

---

# 7. Kernel / Filter

A kernel is a small matrix.

Common sizes:

```text
3 × 3
5 × 5
7 × 7
```

Example:

```text
1  0 -1
1  0 -1
1  0 -1
```

The kernel moves over the image and produces a new output called a:

```text
Feature Map
```

---

# 8. Feature Map

The output produced by convolution is called a **feature map**.

Example:

```text
Input Image
    ↓
Filter
    ↓
Convolution
    ↓
Feature Map
```

CNN normally uses many filters.

Example:

```text
32 filters
    ↓
32 feature maps
```

---

# 9. Stride

Stride tells us **how many pixels the filter moves**.

### Stride = 1

The filter moves:

```text
1 pixel at a time
```

### Stride = 2

The filter moves:

```text
2 pixels at a time
```

Example:

```text
Stride 1
→ Larger output

Stride 2
→ Smaller output
```

So:

```text
Larger Stride
      ↓
Smaller Feature Map
```

---

# 10. Padding

Padding means adding extra pixels around the image.

Usually zeros are added.

Original:

```text
1 2 3
4 5 6
7 8 9
```

With padding:

```text
0 0 0 0 0
0 1 2 3 0
0 4 5 6 0
0 7 8 9 0
0 0 0 0 0
```

Padding helps:

* Preserve image size
* Process image edges
* Prevent output from shrinking too quickly

---

# 11. Valid and Same Padding

## Valid Padding

No padding.

```text
Padding = 0
```

Output becomes smaller.

## Same Padding

Padding is added so that output size is usually kept the same when stride is 1.

Example:

```text
Input:
32 × 32

Output:
32 × 32
```

---

# 12. Output Size Formula

The convolution output size is:

```text
Output = floor((N + 2P - K) / S) + 1
```

Where:

```text
N = Input size
P = Padding
K = Kernel size
S = Stride
```

Example:

```text
Input   = 32
Kernel  = 3
Padding = 1
Stride  = 1
```

Then:

```text
Output = 32
```

---

# 13. ReLU

ReLU is an activation function.

Full form:

```text
Rectified Linear Unit
```

Formula:

```text
ReLU(x) = max(0, x)
```

Example:

```text
-5 → 0
-2 → 0
 3 → 3
 8 → 8
```

ReLU helps CNN learn complex patterns.

---

# 14. Pooling

Pooling reduces the size of feature maps.

The most common type is:

```text
Max Pooling
```

Example:

```text
1 3
2 8
```

Maximum value:

```text
8
```

Another example:

```text
4 7
9 2
```

Maximum:

```text
9
```

A `2 × 2` max pooling layer can reduce:

```text
28 × 28
   ↓
14 × 14
```

---

# 15. Flatten

Flatten converts feature maps into a single vector.

Example:

```text
16 × 16 × 128
```

becomes:

```text
32768 values
```

Flow:

```text
16 × 16 × 128
      ↓
   Flatten
      ↓
[0.2, 0.8, 0.1, ...]
```

---

# 16. Dense Layer

The Dense layer makes the final decision using extracted features.

```text
Features
   ↓
Dense Layer
   ↓
Class Scores
```

For example:

```text
Cat
Dog
Horse
```

---

# 17. Output Layer

The output layer depends on the problem.

## Binary Classification

Example:

```text
Cat
Dog
```

Use:

```text
Sigmoid
```

Example prediction:

```text
0.90
```

Possible meaning:

```text
0 → Cat
1 → Dog
```

Then:

```text
0.90
→ Dog
```

---

# 18. Multi-Class Classification

Suppose there are three classes:

```text
Cat
Dog
Horse
```

Use:

```text
Softmax
```

Example:

```text
Cat   = 0.10
Dog   = 0.80
Horse = 0.10
```

Prediction:

```text
Dog
```

---

# 19. Complete CNN Architecture Example

Suppose the input image is:

```text
128 × 128 × 3
```

Architecture:

```text
Input Image
128 × 128 × 3
       ↓
Conv2D
32 Filters
3 × 3
       ↓
128 × 128 × 32
       ↓
ReLU
       ↓
Max Pooling
       ↓
64 × 64 × 32
       ↓
Conv2D
64 Filters
       ↓
64 × 64 × 64
       ↓
ReLU
       ↓
Max Pooling
       ↓
32 × 32 × 64
       ↓
Conv2D
128 Filters
       ↓
32 × 32 × 128
       ↓
ReLU
       ↓
Max Pooling
       ↓
16 × 16 × 128
       ↓
Flatten
       ↓
32768 values
       ↓
Dense Layer
       ↓
Output
       ↓
Cat / Dog / Horse
```

---

# 20. Important CNN Pattern

As we go deeper into CNN:

```text
Image Height and Width
↓ decrease

Number of Channels / Filters
↑ increase
```

Example:

```text
224 × 224 × 3
      ↓
112 × 112 × 32
      ↓
56 × 56 × 64
      ↓
28 × 28 × 128
      ↓
14 × 14 × 256
```

Remember:

```text
Spatial Size ↓

Features ↑
```

---

# 21. How CNN Identifies an Image

Suppose we want CNN to identify cats and dogs.

Training data:

```text
cat1.jpg → Cat
cat2.jpg → Cat
cat3.jpg → Cat

dog1.jpg → Dog
dog2.jpg → Dog
dog3.jpg → Dog
```

CNN learns from these images.

Conceptually:

```text
Image
 ↓
Edges
 ↓
Shapes
 ↓
Textures
 ↓
Object Parts
 ↓
High-Level Features
 ↓
Prediction
```

Example:

```text
New Cat Image
      ↓
CNN
      ↓
Cat = 95%
Dog = 5%
      ↓
CAT
```

---

# 22. How CNN Learns

CNN learns through training.

```text
Image
  ↓
CNN
  ↓
Prediction
  ↓
Compare with Correct Answer
  ↓
Calculate Loss
  ↓
Backpropagation
  ↓
Update Weights
  ↓
Repeat
```

Example:

```text
Correct = Cat

CNN Predicts = Dog
```

The model calculates an error and changes its weights.

After many examples:

```text
Prediction improves
```

---

# 23. Loss Function

The loss function measures how wrong the prediction is.

For classification, a common loss is:

```text
Cross-Entropy Loss
```

Training tries to:

```text
Reduce Loss
```

---

# 24. Backpropagation

Backpropagation calculates how model parameters should change to reduce the error.

```text
Prediction
   ↓
Loss
   ↓
Backpropagation
   ↓
Calculate Gradients
   ↓
Update Weights
```

---

# 25. Optimizer

Optimizer updates the weights.

Common optimizers:

```text
SGD
Adam
AdamW
```

Example:

```text
Loss
 ↓
Backpropagation
 ↓
Optimizer
 ↓
Updated Weights
```

---

# 26. Learning Rate

Learning rate controls how much weights change.

Example values:

```text
0.01
0.001
0.0001
```

Too large:

```text
Training may become unstable
```

Too small:

```text
Training may be very slow
```

---

# 27. Epoch

One epoch means:

```text
CNN has seen the entire training dataset once
```

Example:

```text
Dataset = 10,000 images
```

After all 10,000 images are used once:

```text
1 Epoch
```

---

# 28. Batch Size

Training data is usually processed in groups.

Example:

```text
Batch Size = 32
```

Flow:

```text
32 Images
   ↓
CNN
   ↓
Update Weights
   ↓
Next 32 Images
```

---

# 29. Data Augmentation

Data augmentation creates modified versions of training images.

Examples:

```text
Flip
Rotate
Crop
Zoom
Brightness Change
```

Example:

```text
Original Cat
    ↓
Flip
Rotate
Zoom
    ↓
More Training Images
```

This can help reduce overfitting.

---

# 30. Overfitting

Overfitting means:

```text
Model performs very well on training data
but poorly on new data.
```

Example:

```text
Training Accuracy   = 99%
Validation Accuracy = 70%
```

Ways to reduce overfitting:

```text
More Data
Data Augmentation
Dropout
Early Stopping
Weight Decay
Transfer Learning
```

---

# 31. Dropout

Dropout randomly disables some neurons during training.

Example:

```text
Normal:

● ● ● ● ●

With Dropout:

● X ● X ●
```

This helps reduce overfitting.

---

# 32. Batch Normalization

Batch normalization helps training become more stable.

A common block is:

```text
Convolution
    ↓
Batch Normalization
    ↓
ReLU
```

---

# 33. Training, Validation, Test Data

A dataset is usually divided into:

```text
Training Data
Validation Data
Test Data
```

Example:

```text
70% → Training
15% → Validation
15% → Testing
```

### Training

Used to learn weights.

### Validation

Used to check performance while building the model.

### Testing

Used for final evaluation on unseen images.

---

# 34. Classification vs Detection vs Segmentation

## Image Classification

Question:

```text
What is in the image?
```

Output:

```text
Dog
```

---

## Object Detection

Questions:

```text
What objects are present?

Where are they?
```

Output:

```text
Dog + Bounding Box
Car + Bounding Box
```

---

## Image Segmentation

Segmentation identifies objects at the pixel level.

```text
Image
  ↓
Each Pixel Classified
```

---

# 35. Popular CNN Architectures

Some famous CNN architectures are:

```text
LeNet
AlexNet
VGG
GoogLeNet / Inception
ResNet
DenseNet
MobileNet
EfficientNet
```

---

# 36. LeNet

Simple architecture:

```text
Input
 ↓
Conv
 ↓
Pool
 ↓
Conv
 ↓
Pool
 ↓
Dense
 ↓
Output
```

It is commonly associated with handwritten digit recognition.

---

# 37. VGG

VGG uses many small:

```text
3 × 3
```

convolutions.

Simple flow:

```text
Input
 ↓
Conv
 ↓
Conv
 ↓
Pool
 ↓
Conv
 ↓
Conv
 ↓
Pool
 ↓
Dense
 ↓
Output
```

---

# 38. ResNet

ResNet uses **skip connections**.

Normal:

```text
Input
 ↓
Conv
 ↓
Conv
 ↓
Output
```

ResNet:

```text
Input ──────────────┐
  ↓                 │
Conv                │
  ↓                 │
Conv                │
  ↓                 │
Add ◄───────────────┘
  ↓
Output
```

Main idea:

```text
Output = F(x) + x
```

Skip connections help train deep networks.

---

# 39. MobileNet

MobileNet is designed for:

```text
Mobile Phones
Edge Devices
Embedded Devices
```

It is lightweight and fast.

---

# 40. Transfer Learning

Instead of training a CNN from zero, we can use a pretrained model.

Examples:

```text
ResNet
MobileNet
EfficientNet
```

Flow:

```text
Pretrained CNN
      ↓
Replace Output Layer
      ↓
Train on New Dataset
      ↓
Fine-Tune
```

This is called:

```text
Transfer Learning
```

---

# 41. Simple CNN Code in TensorFlow

```python
import tensorflow as tf
from tensorflow.keras import layers, models

model = models.Sequential([

    layers.Input(shape=(128, 128, 3)),

    layers.Conv2D(
        32,
        (3, 3),
        activation="relu",
        padding="same"
    ),

    layers.MaxPooling2D((2, 2)),

    layers.Conv2D(
        64,
        (3, 3),
        activation="relu",
        padding="same"
    ),

    layers.MaxPooling2D((2, 2)),

    layers.Conv2D(
        128,
        (3, 3),
        activation="relu",
        padding="same"
    ),

    layers.MaxPooling2D((2, 2)),

    layers.Flatten(),

    layers.Dense(
        128,
        activation="relu"
    ),

    layers.Dropout(0.5),

    layers.Dense(
        3,
        activation="softmax"
    )
])

model.summary()
```

For three classes:

```text
Cat
Dog
Horse
```

The last layer is:

```python
layers.Dense(3, activation="softmax")
```

---

# 42. Training the CNN

```python
model.compile(
    optimizer="adam",
    loss="sparse_categorical_crossentropy",
    metrics=["accuracy"]
)

model.fit(
    train_dataset,
    validation_data=validation_dataset,
    epochs=20
)
```

Flow:

```text
Training Images
      ↓
CNN
      ↓
Prediction
      ↓
Loss
      ↓
Backpropagation
      ↓
Update Weights
```

---

# 43. Predicting a New Image

After training:

```python
import tensorflow as tf
import numpy as np

img = tf.keras.utils.load_img(
    "test.jpg",
    target_size=(128, 128)
)

img_array = tf.keras.utils.img_to_array(img)

img_array = tf.expand_dims(
    img_array,
    axis=0
)

prediction = model.predict(img_array)

class_id = np.argmax(prediction)

print(class_id)
```

Suppose:

```text
0 = Cat
1 = Dog
2 = Horse
```

If output is:

```text
[0.10, 0.85, 0.05]
```

Highest value:

```text
0.85
```

Index:

```text
1
```

Prediction:

```text
Dog
```

---

# 44. Complete Image Recognition Flow

```text
Collect Images
      ↓
Label Images
      ↓
Split Dataset
      ↓
Resize Images
      ↓
Normalize Images
      ↓
Data Augmentation
      ↓
Build CNN
      ↓
Train CNN
      ↓
Validate CNN
      ↓
Test CNN
      ↓
Save Model
      ↓
Load New Image
      ↓
Preprocess Image
      ↓
CNN Prediction
      ↓
Class Label
```

---

# 45. Important CNN Concepts

| Concept           | Meaning                                        |
| ----------------- | ---------------------------------------------- |
| CNN               | Neural network for spatial data such as images |
| Convolution       | Extract features                               |
| Kernel            | Small filter                                   |
| Feature Map       | Output of convolution                          |
| Stride            | How far filter moves                           |
| Padding           | Extra pixels around image                      |
| ReLU              | Activation function                            |
| Pooling           | Reduces feature-map size                       |
| Flatten           | Converts feature maps to vector                |
| Dense             | Makes final decision                           |
| Softmax           | Multi-class probabilities                      |
| Sigmoid           | Binary/multi-label probability                 |
| Loss              | Measures error                                 |
| Optimizer         | Updates model weights                          |
| Epoch             | One full dataset pass                          |
| Batch Size        | Images processed together                      |
| Dropout           | Reduces overfitting                            |
| Augmentation      | Creates image variations                       |
| Transfer Learning | Reuse pretrained models                        |

---

# 46. CNN Architecture Summary

```text
              INPUT IMAGE
                   │
                   ▼
            ┌─────────────┐
            │ Convolution │
            │ Find Feature│
            └─────────────┘
                   │
                   ▼
            ┌─────────────┐
            │    ReLU     │
            └─────────────┘
                   │
                   ▼
            ┌─────────────┐
            │   Pooling   │
            │ Reduce Size │
            └─────────────┘
                   │
                   ▼
             Repeat Blocks
                   │
                   ▼
            ┌─────────────┐
            │ Flatten/GAP │
            └─────────────┘
                   │
                   ▼
            ┌─────────────┐
            │ Dense Layer │
            └─────────────┘
                   │
                   ▼
            ┌─────────────┐
            │   Output    │
            └─────────────┘
                   │
                   ▼
               PREDICTION
```

---

# 47. Easy Memory Trick

Remember:

```text
CNN = SEE → EXTRACT → REDUCE → DECIDE
```

### SEE

```text
Input Image
```

### EXTRACT

```text
Convolution
```

### REDUCE

```text
Pooling
```

### DECIDE

```text
Dense Layer
```

Final:

```text
IMAGE
 ↓
CONVOLUTION
 ↓
RELU
 ↓
POOLING
 ↓
FEATURES
 ↓
DENSE
 ↓
PREDICTION
```

---

# 48. Most Important Points for Interview

Remember these first:

```text
CNN = Convolutional Neural Network

Kernel = Feature Detector

Stride = Filter Movement

Padding = Border Pixels

Feature Map = Convolution Output

ReLU = Non-Linearity

Pooling = Reduce Size

Flatten = Convert to Vector

Dense = Classification

Softmax = Multi-Class Output

Sigmoid = Binary Output
```

Most important architecture:

```text
Input
 ↓
Conv
 ↓
ReLU
 ↓
Pool
 ↓
Conv
 ↓
ReLU
 ↓
Pool
 ↓
Flatten
 ↓
Dense
 ↓
Output
```

Most important CNN pattern:

```text
Width / Height ↓

Channels / Features ↑
```

Example:

```text
224 × 224 × 3
      ↓
112 × 112 × 32
      ↓
56 × 56 × 64
      ↓
28 × 28 × 128
```

---

# 49. One-Line Definition

> A CNN is a deep learning model that uses convolution filters to automatically learn image features and classify or recognize objects.

---

# 50. Final Quick Revision

```text
Input Image
     ↓
Convolution
     ↓
Feature Map
     ↓
ReLU
     ↓
Pooling
     ↓
More Conv Layers
     ↓
Flatten / Global Average Pooling
     ↓
Dense Layer
     ↓
Softmax / Sigmoid
     ↓
Prediction
```

For image recognition:

```text
Training Images + Labels
          ↓
         CNN
          ↓
     Learn Features
          ↓
     Trained Model
          ↓
      New Image
          ↓
      Prediction
```
