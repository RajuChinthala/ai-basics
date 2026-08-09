# Recurrent Neural Networks (RNN) — Complete Notes

## Table of Contents

1. [What is an RNN?](#1-what-is-an-rnn)
2. [Why Do We Need RNNs?](#2-why-do-we-need-rnns)
3. [Sequential Data](#3-sequential-data)
4. [Feedforward Neural Network vs RNN](#4-feedforward-neural-network-vs-rnn)
5. [RNN Architecture](#5-rnn-architecture)
6. [How an RNN Works](#6-how-an-rnn-works)
7. [RNN Mathematics](#7-rnn-mathematics)
8. [Hidden State](#8-hidden-state)
9. [Parameter Sharing](#9-parameter-sharing)
10. [Types of RNN](#10-types-of-rnn)
11. [Training an RNN](#11-training-an-rnn)
12. [Backpropagation Through Time](#12-backpropagation-through-time)
13. [Vanishing Gradient Problem](#13-vanishing-gradient-problem)
14. [Exploding Gradient Problem](#14-exploding-gradient-problem)
15. [Long-Term Dependencies](#15-long-term-dependencies)
16. [LSTM](#16-lstm)
17. [GRU](#17-gru)
18. [RNN vs LSTM vs GRU](#18-rnn-vs-lstm-vs-gru)
19. [Bidirectional RNN](#19-bidirectional-rnn)
20. [Stacked/Deep RNN](#20-stackeddeep-rnn)
21. [Sequence-to-Sequence Models](#21-sequence-to-sequence-models)
22. [RNN Applications](#22-rnn-applications)
23. [Advantages and Disadvantages](#23-advantages-and-disadvantages)
24. [RNN Implementation in PyTorch](#24-rnn-implementation-in-pytorch)
25. [Important Terminology](#25-important-terminology)
26. [Common Interview Questions](#26-common-interview-questions)
27. [Summary](#27-summary)

---

# 1. What is an RNN?

**RNN** stands for **Recurrent Neural Network**.

An RNN is a type of neural network designed primarily for processing **sequential data**.

Examples of sequential data include:

* Sentences
* Documents
* Audio
* Speech
* Stock prices
* Sensor measurements
* Weather measurements
* Video frames
* DNA sequences
* Time-series data

The important feature of an RNN is that it maintains information about **previous inputs** while processing the current input.

In simple terms:

> **RNN = Neural Network + Memory**

---

# 2. Why Do We Need RNNs?

Consider the sentence:

```text
I am learning neural networks.
```

The meaning of the word:

```text
networks
```

depends partly on the words that came before it.

Similarly, suppose we want to predict the next word:

```text
I am going to the ___
```

Possible predictions could include:

```text
store
school
office
park
```

To make a good prediction, the model needs information from previous words.

A normal feedforward neural network does not naturally maintain such a memory.

An RNN solves this problem by maintaining a **hidden state**.

---

# 3. Sequential Data

Sequential data is data where the **order of observations matters**.

For example:

```text
I love machine learning.
```

is different from:

```text
Learning love machine I.
```

Even though both contain similar words, changing the order changes the meaning.

Another example is stock prices:

```text
Day 1 → $100
Day 2 → $103
Day 3 → $105
Day 4 → $102
```

The previous prices can contain useful information for analyzing the current state.

Therefore, sequence models try to capture relationships between observations across time or position.

---

# 4. Feedforward Neural Network vs RNN

## Feedforward Neural Network

A traditional neural network processes inputs independently.

```text
Input
  ↓
Hidden Layer
  ↓
Output
```

There is no built-in memory of previous inputs.

---

## Recurrent Neural Network

An RNN contains a recurrent connection.

```text
Input₁ → RNN → Hidden₁
                  ↓
Input₂ → RNN → Hidden₂
                  ↓
Input₃ → RNN → Hidden₃
                  ↓
Input₄ → RNN → Hidden₄
```

Each hidden state contains information derived from the current input and the previous hidden state.

Therefore:

```text
Current State = Current Input + Previous State
```

Conceptually, this gives the network memory.

---

# 5. RNN Architecture

An RNN can be represented as:

```text
             ┌───────────────┐
             │               │
             ▼               │
Input ───→ [ RNN Cell ] ───→ Hidden State
                 │
                 ▼
               Output
```

The recurrent connection allows information to move from one time step to another.

We can also **unroll** the network through time.

```text
x₁        x₂        x₃        x₄
↓         ↓         ↓         ↓
RNN ───→ RNN ───→ RNN ───→ RNN
↓         ↓         ↓         ↓
h₁        h₂        h₃        h₄
↓         ↓         ↓         ↓
y₁        y₂        y₃        y₄
```

Where:

* `x_t` = input at time step `t`
* `h_t` = hidden state at time step `t`
* `y_t` = output at time step `t`

---

# 6. How an RNN Works

Suppose the input sentence is:

```text
I love deep learning
```

The RNN processes one token at a time.

### Step 1

Input:

```text
I
```

The network calculates:

```text
h₁
```

---

### Step 2

Input:

```text
love
```

The RNN uses:

```text
love + h₁
```

to calculate:

```text
h₂
```

---

### Step 3

Input:

```text
deep
```

The RNN uses:

```text
deep + h₂
```

to calculate:

```text
h₃
```

---

### Step 4

Input:

```text
learning
```

The RNN uses:

```text
learning + h₃
```

to calculate:

```text
h₄
```

Therefore, information can propagate through the sequence.

---

# 7. RNN Mathematics

The most important RNN equation calculates the hidden state:

```text
h_t = tanh(W_xh x_t + W_hh h_(t-1) + b_h)
```

Where:

| Symbol    | Meaning                            |
| --------- | ---------------------------------- |
| `x_t`     | Input at current time step         |
| `h_t`     | Current hidden state               |
| `h_(t-1)` | Previous hidden state              |
| `W_xh`    | Input-to-hidden weights            |
| `W_hh`    | Hidden-to-hidden recurrent weights |
| `b_h`     | Hidden-state bias                  |
| `tanh`    | Activation function                |

The output can then be calculated as:

```text
y_t = W_hy h_t + b_y
```

For classification, the result may be passed through something like:

```text
softmax(y_t)
```

to produce class probabilities.

---

# 8. Hidden State

The **hidden state** is one of the most important concepts in an RNN.

You can think of it as the network's internal representation of information seen so far.

For example:

```text
The dog was hungry, so it ate the ___
```

By the time the RNN reaches the blank, its hidden state may contain information related to:

```text
dog
hungry
ate
```

That information can help predict:

```text
food
```

The hidden state is updated after every input.

```text
h₀ → h₁ → h₂ → h₃ → ... → h_T
```

Usually `h₀` is initialized with zeros, although other initialization strategies are possible.

---

# 9. Parameter Sharing

An important property of RNNs is **parameter sharing**.

Consider:

```text
x₁ → RNN → h₁
x₂ → RNN → h₂
x₃ → RNN → h₃
```

These are not normally three completely different RNNs.

The **same RNN cell and parameters** are reused across time steps.

For example:

```text
W_xh
W_hh
W_hy
```

are shared across the sequence.

This makes RNNs capable of handling sequences of different lengths and greatly reduces the number of parameters compared with having a separate network for every position.

---

# 10. Types of RNN

RNN architectures can be categorized according to their input and output structures.

## 10.1 One-to-One

```text
Input → Output
```

Example:

```text
Image → Image classification
```

This is essentially a standard neural-network setup rather than a sequence-specific architecture.

---

## 10.2 One-to-Many

```text
       → Output₁
Input  → Output₂
       → Output₃
```

Example:

```text
Image → sequence of words
```

Historically used in image captioning systems.

---

## 10.3 Many-to-One

```text
Input₁ ─┐
Input₂ ─┼→ Output
Input₃ ─┘
```

Example:

```text
"This movie is amazing" → Positive
```

Useful for:

* Sentiment analysis
* Sequence classification
* Spam detection

---

## 10.4 Many-to-Many

```text
Input₁ → Output₁
Input₂ → Output₂
Input₃ → Output₃
```

Examples include:

* Sequence labeling
* Part-of-speech tagging
* Named entity recognition

Another many-to-many configuration can have different input and output lengths:

```text
Input sequence → Output sequence
```

This is used in sequence-to-sequence architectures.

---

# 11. Training an RNN

RNN training follows the same general idea as training other neural networks.

The main steps are:

```text
1. Forward propagation
2. Calculate loss
3. Backpropagation
4. Calculate gradients
5. Update parameters
6. Repeat
```

Because an RNN operates across time steps, its backpropagation procedure is called:

**Backpropagation Through Time (BPTT).**

---

# 12. Backpropagation Through Time

Consider an unrolled RNN:

```text
x₁       x₂       x₃
↓        ↓        ↓
RNN ───→ RNN ───→ RNN
↓        ↓        ↓
y₁       y₂       y₃
```

During forward propagation:

```text
t₁ → t₂ → t₃
```

During backpropagation, gradients propagate backward through the unrolled computation:

```text
t₃ → t₂ → t₁
```

Because the same recurrent parameters are reused at multiple time steps, their gradient receives contributions from multiple positions in the sequence.

This process is called:

```text
Backpropagation Through Time
```

or:

```text
BPTT
```

---

# 13. Vanishing Gradient Problem

One of the biggest problems with basic RNNs is the **vanishing gradient problem**.

During BPTT, gradients are repeatedly multiplied through many time steps.

Conceptually:

```text
gradient × gradient × gradient × ...
```

If these factors repeatedly have magnitudes smaller than `1`, the resulting gradient can become extremely small.

For example:

```text
0.1 × 0.1 × 0.1 × 0.1 × 0.1
= 0.00001
```

The gradient effectively disappears.

As a result, earlier time steps receive very weak learning signals.

This makes it difficult for a vanilla RNN to learn **long-term dependencies**.

---

# 14. Exploding Gradient Problem

The opposite problem can also occur.

If repeated gradient factors have large magnitudes:

```text
2 × 2 × 2 × 2 × 2 × ...
```

the gradient can become extremely large.

This is known as the:

**Exploding Gradient Problem**

It can cause:

* Unstable training
* Huge parameter updates
* `NaN` values
* Failure to converge

A common solution is:

## Gradient Clipping

Instead of allowing gradients to become arbitrarily large, their magnitude is limited.

For example, in PyTorch:

```python
torch.nn.utils.clip_grad_norm_(model.parameters(), max_norm=1.0)
```

---

# 15. Long-Term Dependencies

Suppose we have:

```text
I grew up in France and lived there for twenty years.
I speak fluent ___.
```

To predict:

```text
French
```

the model needs to remember information from much earlier in the sequence.

This is called a:

**Long-Term Dependency**

Vanilla RNNs often struggle with these dependencies.

This motivated architectures such as:

* LSTM
* GRU

---

# 16. LSTM

**LSTM** stands for:

**Long Short-Term Memory**

LSTM is a special type of recurrent neural network designed to handle long-term dependencies better than a basic RNN.

Instead of having only a hidden state, an LSTM maintains:

```text
Hidden State
+
Cell State
```

The cell state provides a controlled path for information to persist across time.

---

## LSTM Gates

An LSTM primarily uses three gates:

1. Forget Gate
2. Input Gate
3. Output Gate

---

## 16.1 Forget Gate

The forget gate determines:

> What information should be forgotten?

Conceptually:

```text
Old memory
    ↓
Forget Gate
    ↓
Keep / Remove information
```

---

## 16.2 Input Gate

The input gate determines:

> What new information should be stored?

```text
New information
      ↓
Input Gate
      ↓
Update memory
```

---

## 16.3 Output Gate

The output gate determines:

> What information should be exposed as the current hidden state/output?

```text
Memory
  ↓
Output Gate
  ↓
Hidden State
```

---

## LSTM Overview

```text
Previous Cell State
        ↓
   Forget Gate
        ↓
     Updated
      Memory
        ↑
    Input Gate
        ↑
Current Input

        ↓

   Output Gate
        ↓
Current Hidden State
```

Because of these gates, LSTMs can preserve useful information and discard irrelevant information more effectively than vanilla RNNs.

---

# 17. GRU

**GRU** stands for:

**Gated Recurrent Unit**

GRU is another gated RNN architecture.

It is similar to LSTM but has a simpler structure.

A GRU mainly uses:

1. Update Gate
2. Reset Gate

---

## Update Gate

Determines how much previous information should be preserved.

---

## Reset Gate

Determines how much previous information should be ignored when incorporating the current input.

---

## GRU vs LSTM

GRU generally has:

* Fewer gates
* Fewer parameters
* No separate cell state in the standard formulation
* Potentially faster training

Both GRU and LSTM are designed to address limitations of vanilla RNNs.

---

# 18. RNN vs LSTM vs GRU

| Feature                       | RNN                 | LSTM         | GRU                    |
| ----------------------------- | ------------------- | ------------ | ---------------------- |
| Architecture                  | Simple              | More complex | Medium complexity      |
| Hidden state                  | Yes                 | Yes          | Yes                    |
| Separate cell state           | No                  | Yes          | No                     |
| Gates                         | No                  | 3 main gates | 2 main gates           |
| Long-term memory              | Weak                | Stronger     | Stronger               |
| Parameters                    | Few                 | Most         | Fewer than LSTM        |
| Training speed                | Often fast per step | Slower       | Often faster than LSTM |
| Vanishing gradient resistance | Poor                | Better       | Better                 |

A useful simplification is:

```text
RNN  → simplest recurrent model
LSTM → RNN with sophisticated memory control
GRU  → simplified gated alternative to LSTM
```

---

# 19. Bidirectional RNN

A normal RNN processes a sequence in one direction:

```text
Left → Right
```

For example:

```text
I → love → machine → learning
```

A **Bidirectional RNN** processes information in both directions:

```text
Forward:
I → love → machine → learning

Backward:
I ← love ← machine ← learning
```

The representations from both directions are combined.

This allows the model to use information from both earlier and later positions.

This can be useful when the entire input sequence is already available.

Examples include:

* Sequence labeling
* Named entity recognition
* Speech-related tasks
* Text classification

It is generally not appropriate when future inputs genuinely aren't available at prediction time.

---

# 20. Stacked/Deep RNN

Multiple RNN layers can be stacked.

```text
Input Sequence
      ↓
   RNN Layer 1
      ↓
   RNN Layer 2
      ↓
   RNN Layer 3
      ↓
     Output
```

This is called a:

* Stacked RNN
* Multi-layer RNN
* Deep RNN

Higher layers can learn increasingly abstract representations of the sequence.

The same idea applies to:

```text
Stacked LSTM
Stacked GRU
```

---

# 21. Sequence-to-Sequence Models

A **Sequence-to-Sequence (Seq2Seq)** model converts one sequence into another sequence.

Historically, a common architecture was:

```text
Encoder → Context → Decoder
```

For example:

```text
English sentence
       ↓
    Encoder
       ↓
Representation
       ↓
    Decoder
       ↓
French sentence
```

RNNs, LSTMs, and GRUs were widely used to build early Seq2Seq systems.

Attention mechanisms later significantly improved these systems.

Modern large-scale sequence modeling is now dominated by **Transformers**.

---

# 22. RNN Applications

RNN-family models have been used in many areas.

## Natural Language Processing

Examples:

```text
Sentiment analysis
Language modeling
Text generation
Sequence classification
Named entity recognition
Machine translation
```

---

## Speech Processing

Examples:

```text
Speech recognition
Audio sequence analysis
Speech generation
```

---

## Time-Series Analysis

Examples:

```text
Weather measurements
Sensor data
Financial time series
Energy consumption
Traffic patterns
```

---

## Video

Video can be considered a sequence:

```text
Frame₁ → Frame₂ → Frame₃ → Frame₄
```

Recurrent architectures have historically been used to model relationships between frames.

---

# 23. Advantages and Disadvantages

## Advantages

### 1. Designed for sequential information

RNNs naturally model ordered inputs.

### 2. Maintains a hidden state

Previous information can influence later predictions.

### 3. Parameter sharing

The same parameters are reused across time steps.

### 4. Variable-length sequences

RNNs can process sequences with different lengths.

### 5. Foundation for understanding sequence models

Learning RNNs makes it easier to understand:

```text
LSTM
GRU
Seq2Seq
Attention
Transformers
```

---

## Disadvantages

### 1. Vanishing gradients

Basic RNNs struggle with long-term dependencies.

### 2. Exploding gradients

Training can become unstable.

### 3. Sequential computation

The hidden state at time `t` depends on the state at time `t-1`.

Therefore, processing cannot be fully parallelized across sequence positions in the same way as Transformers.

### 4. Long sequences are difficult

Remembering information across many steps is challenging for vanilla RNNs.

### 5. Less common in modern large language models

Transformers are generally preferred for modern large-scale NLP systems.

---

# 24. RNN Implementation in PyTorch

## Simple RNN

```python
import torch
import torch.nn as nn


class SimpleRNN(nn.Module):

    def __init__(self, input_size, hidden_size, output_size):
        super().__init__()

        self.rnn = nn.RNN(
            input_size=input_size,
            hidden_size=hidden_size,
            batch_first=True
        )

        self.fc = nn.Linear(hidden_size, output_size)

    def forward(self, x):

        output, hidden = self.rnn(x)

        # Use the RNN output from the final sequence position
        final_output = output[:, -1, :]

        prediction = self.fc(final_output)

        return prediction
```

---

## Understanding the Input Shape

With:

```python
batch_first=True
```

the input normally has shape:

```text
(batch_size, sequence_length, input_size)
```

Example:

```text
(32, 10, 50)
```

means:

```text
32 sequences
10 time steps per sequence
50 features per time step
```

---

## RNN Output

```python
output, hidden = self.rnn(x)
```

`output` contains the output features from the final RNN layer for every time step.

Conceptually:

```text
h₁
h₂
h₃
...
h_T
```

With `batch_first=True`, its shape is typically:

```text
(batch_size, sequence_length, hidden_size)
```

for a basic single-direction RNN.

---

## Final Hidden State

`hidden` contains the final hidden state for each RNN layer and direction.

For a simple one-layer, one-direction RNN:

```text
hidden.shape
=
(1, batch_size, hidden_size)
```

For multiple layers or bidirectional networks, the first dimension becomes larger.

---

# 25. Important Terminology

## Sequence

Ordered collection of data.

```text
x₁, x₂, x₃, ..., x_T
```

---

## Time Step

One position within a sequence.

```text
t = 1, 2, 3, ...
```

---

## Hidden State

Internal representation passed between time steps.

```text
h_t
```

---

## Recurrent Connection

Connection carrying information from the previous hidden state to the next computation.

```text
h_(t-1) → h_t
```

---

## BPTT

**Backpropagation Through Time**

Training procedure used to calculate gradients through the unrolled RNN computation.

---

## Vanishing Gradient

Gradients become extremely small during backpropagation.

---

## Exploding Gradient

Gradients become extremely large.

---

## LSTM

**Long Short-Term Memory**

A gated recurrent architecture designed to better preserve long-term information.

---

## GRU

**Gated Recurrent Unit**

A simpler gated recurrent architecture.

---

## Bidirectional RNN

Processes a sequence in both forward and backward directions.

---

# 26. Common Interview Questions

## Q1. What is an RNN?

An RNN is a neural network architecture designed for sequential data. It maintains a hidden state that allows information from previous sequence positions to influence later computations.

---

## Q2. Why is an RNN called recurrent?

Because information from the previous hidden state is fed into the network again when processing the next time step.

```text
h_(t-1) → RNN → h_t
```

---

## Q3. What is a hidden state?

The hidden state is the internal representation that carries information across sequence positions.

---

## Q4. What is BPTT?

BPTT stands for **Backpropagation Through Time**.

It is the process of backpropagating gradients through the unrolled RNN computation across multiple time steps.

---

## Q5. What is the vanishing gradient problem?

During backpropagation through many steps, gradients can become extremely small.

As a result, the network struggles to learn relationships involving distant sequence positions.

---

## Q6. What is the exploding gradient problem?

Gradients can grow extremely large during BPTT, resulting in unstable training.

Gradient clipping is a common mitigation technique.

---

## Q7. Why is LSTM better than a basic RNN for long sequences?

LSTM uses a cell state and gating mechanisms to control what information is stored, forgotten, and exposed.

This helps gradients and useful information persist over longer sequences.

---

## Q8. What is the difference between LSTM and GRU?

LSTM uses a separate cell state and three main gates:

```text
Forget
Input
Output
```

GRU has a simpler structure with two main gates:

```text
Reset
Update
```

GRUs therefore usually have fewer parameters.

---

## Q9. What is a bidirectional RNN?

A bidirectional RNN processes a sequence in both directions and combines information from the forward and backward passes.

---

## Q10. Can RNNs process variable-length sequences?

Yes.

RNNs naturally operate one step at a time and can process sequences of different lengths, although batching variable-length sequences usually requires padding, packing, masking, or similar techniques.

---

## Q11. Why are Transformers often preferred over RNNs?

A major limitation of RNNs is their sequential computation:

```text
h₁ → h₂ → h₃ → h₄
```

Later states depend directly on earlier states.

Transformers use **self-attention**, allowing relationships between sequence positions to be modeled without the same recurrent chain.

This provides important advantages for parallel training and modeling long-range relationships.

---

# 27. Summary

The most important concepts to remember are:

```text
RNN
│
├── Designed for sequential data
│
├── Processes one sequence position at a time
│
├── Maintains hidden state
│
├── Shares parameters across time
│
├── Trained using BPTT
│
├── Main problems
│   ├── Vanishing gradients
│   └── Exploding gradients
│
├── Improved recurrent architectures
│   ├── LSTM
│   │   ├── Forget gate
│   │   ├── Input gate
│   │   ├── Output gate
│   │   └── Cell state
│   │
│   └── GRU
│       ├── Reset gate
│       └── Update gate
│
├── Extensions
│   ├── Bidirectional RNN
│   ├── Stacked RNN
│   └── Seq2Seq
│
└── Modern alternative
    └── Transformer
```

---

# Quick Revision Cheat Sheet

```text
RNN = Recurrent Neural Network

Purpose:
Process sequential data.

Core idea:
Current input + previous hidden state → new hidden state

Hidden-state equation:

h_t = tanh(W_xh x_t + W_hh h_(t-1) + b_h)

Output:

y_t = W_hy h_t + b_y

Training:
Backpropagation Through Time (BPTT)

Main problems:
1. Vanishing gradients
2. Exploding gradients
3. Difficulty learning long-term dependencies
4. Sequential computation

Solutions / Improvements:
LSTM
GRU
Gradient clipping

LSTM:
Forget gate
Input gate
Output gate
Cell state

GRU:
Reset gate
Update gate

Bidirectional RNN:
Forward sequence + backward sequence

RNN → LSTM/GRU → Attention → Transformer
```

# Recommended Learning Order

Study the concepts in this order:

```text
1. Neural network basics
        ↓
2. Sequential data
        ↓
3. Vanilla RNN architecture
        ↓
4. Hidden state
        ↓
5. RNN equations
        ↓
6. Forward propagation
        ↓
7. Backpropagation Through Time
        ↓
8. Vanishing gradients
        ↓
9. Exploding gradients
        ↓
10. LSTM
        ↓
11. GRU
        ↓
12. Bidirectional RNN
        ↓
13. Sequence-to-Sequence
        ↓
14. Attention
        ↓
15. Transformers
```

A strong understanding of **hidden states, BPTT, vanishing gradients, LSTM, and GRU** gives you the foundation needed to move from classical recurrent networks to modern sequence models.
