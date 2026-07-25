# Introduction to Neural Networks

A neural network (also known as an Artificial Neural Network or ANN) is a method in artificial intelligence that teaches computers to process data in a way inspired by the human brain. It is a type of machine learning process, called deep learning, that uses interconnected nodes or neurons in a layered structure.

---

## How It Works

Neural networks are comprised of node layers, containing an **input layer**, one or more **hidden layers**, and an **output layer**. Each node, or artificial neuron, connects to another and has an associated weight and threshold. 

The standard process follows these steps:
1. **Forward Propagation:** Data is fed into the input layer. The inputs are multiplied by their respective **weights**, added to a **bias**, and then passed through an **activation function** to determine the output of that node. This output becomes the input for the next layer.
2. **Calculating Loss:** Once the data reaches the output layer, the network's prediction is compared to the actual correct answer using a **Loss Function** to determine how wrong or right the network was.
3. **Backpropagation:** The error is sent backward through the network. Using an optimization algorithm like **Gradient Descent**, the network adjusts its weights and biases to reduce the error for the next round of data.

---

## Core Concepts of Neural Networks

To understand neural networks deeply, you need to understand their foundational components:

*   **Neurons (Nodes):** The basic computational units that receive inputs, perform calculations, and produce an output.
*   **Weights and Biases:** 
    *   **Weights ($w$):** Determine the importance or strength of the input signal.
    *   **Biases ($b$):** Allow you to shift the activation function curve up or down to better fit the data.
*   **Activation Functions:** Mathematical equations that determine whether a neuron should "fire" (be activated) or not. They introduce non-linearity into the network, allowing it to learn complex patterns. Common examples include:
    *   **ReLU (Rectified Linear Unit):** $f(x) = \max(0, x)$
    *   **Sigmoid:** $f(x) = \frac{1}{1 + e^{-x}}$
*   **Layers:**
    *   **Input Layer:** Receives the raw data.
    *   **Hidden Layers:** Perform intermediate mathematical computations and feature extraction.
    *   **Output Layer:** Produces the final prediction or classification.

---

## Where Neural Networks Are Used

Neural networks are the driving force behind most modern AI breakthroughs. Major applications include:

### 1. Computer Vision
*   **Facial Recognition:** Unlocking smartphones or security surveillance.
*   **Autonomous Vehicles:** Helping self-driving cars detect lanes, pedestrians, and traffic signs.
*   **Medical Imaging:** Identifying tumors or anomalies in X-rays and MRIs.

### 2. Natural Language Processing (NLP)
*   **Large Language Models (LLMs):** Powering tools like ChatGPT, Gemini, and automated translation software.
*   **Sentiment Analysis:** Analyzing customer reviews to see if they are positive, negative, or neutral.

### 3. Recommendation Systems
*   **Streaming & E-commerce:** Powering the algorithms behind Netflix recommendations, YouTube feeds, and Amazon's "frequently bought together" sections.

### 4. Forecasting and Predictive Analytics
*   **Finance:** Algorithmic trading, stock market predictions, and credit card fraud detection.
*   **Weather:** Predicting complex meteorological shifts and natural disasters.
