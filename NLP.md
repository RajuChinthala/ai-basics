# Natural Language Processing (NLP) — Overview

## 1. What is NLP?

**Natural Language Processing (NLP)** is a branch of **Artificial Intelligence (AI)** that enables computers to understand, interpret, process, and generate human language.

NLP combines concepts from:

* **Computer Science**
* **Artificial Intelligence**
* **Machine Learning (ML)**
* **Deep Learning (DL)**
* **Linguistics**
* **Statistics**

Human language can appear as **text** or **speech**, and NLP techniques help machines extract useful information and meaning from it.

---

## 2. Purpose of NLP

The main purpose of NLP is to make communication between **humans and computers** easier and more natural.

NLP is used to:

* Understand human language
* Extract useful information from text
* Determine the meaning or intent of a sentence
* Analyze opinions and emotions
* Translate between languages
* Generate human-like text
* Summarize large documents
* Answer questions
* Build conversational systems such as chatbots
* Process large amounts of unstructured textual data

### Example

Input:

> "The movie was amazing!"

An NLP system can identify:

* **Topic:** Movie
* **Opinion:** Positive
* **Sentiment:** Positive
* **Important word:** "amazing"

---

## 3. Main Types of NLP

NLP can broadly be divided into two major areas:

### 3.1 Natural Language Understanding (NLU)

**NLU** focuses on helping computers **understand human language**.

Typical tasks include:

* Intent recognition
* Sentiment analysis
* Named Entity Recognition (NER)
* Text classification
* Question understanding
* Information extraction
* Semantic analysis

Example:

> "Book me a flight to New York tomorrow."

NLU may identify:

* **Intent:** Book a flight
* **Destination:** New York
* **Date:** Tomorrow

---

### 3.2 Natural Language Generation (NLG)

**NLG** focuses on helping computers **generate human-readable language**.

Applications include:

* Chatbot responses
* Text summarization
* Report generation
* Question answering
* Content generation
* AI assistants

Example:

Input data:

> Temperature: 35°C

Generated text:

> "Today's temperature is expected to reach 35°C."

---

## 4. Common NLP Tasks

### Tokenization

Breaking text into smaller units called **tokens**.

Example:

```text
"NLP is interesting"
```

becomes:

```text
["NLP", "is", "interesting"]
```

### Stop Word Removal

Removing common words that may carry little useful information for certain tasks.

Examples:

```text
the, is, a, an, and, of
```

For example:

```text
"The cat is on the table"
```

may become:

```text
"cat table"
```

> Note: Stop-word removal is useful in some traditional NLP applications but is not always necessary for modern language models.

### Stemming

Reducing words to a basic **stem**, which may not be a valid dictionary word.

Example:

```text
playing → play
played  → play
studies → studi
```

### Lemmatization

Converting words to their proper dictionary or base form using linguistic information.

Example:

```text
running → run
better  → good
mice    → mouse
```

### Part-of-Speech (POS) Tagging

Identifying the grammatical role of each word.

Example:

```text
John eats apples.
```

* John → Noun
* eats → Verb
* apples → Noun

### Named Entity Recognition (NER)

Identifying important real-world entities in text.

Example:

```text
"Elon Musk founded SpaceX in the United States."
```

Possible entities:

* Elon Musk → Person
* SpaceX → Organization
* United States → Location

### Sentiment Analysis

Determining the emotional tone or opinion expressed in text.

Example:

```text
"I love this product." → Positive
"I hate this product." → Negative
```

Typical classes are:

* Positive
* Negative
* Neutral

### Text Classification

Assigning text to predefined categories.

Example:

```text
"Congratulations! You won $1 million!"
```

Classification:

```text
Spam
```

Applications include:

* Spam detection
* News classification
* Topic classification
* Intent detection

### Machine Translation

Automatically translating text from one language to another.

Example:

```text
English → French
English → Spanish
Hindi → English
```

### Text Summarization

Creating a shorter version of a document while preserving its important information.

Two common approaches are:

1. **Extractive Summarization** — selects important sentences from the original text.
2. **Abstractive Summarization** — generates a new shorter explanation of the original content.

### Question Answering

Finding or generating an answer to a user's question based on available information.

Example:

```text
Context: Paris is the capital of France.
Question: What is the capital of France?
Answer: Paris
```

### Text Generation

Generating new natural-language content based on instructions or previous text.

Applications include:

* AI assistants
* Email generation
* Story generation
* Code explanations
* Report writing

---

## 5. Levels of NLP Analysis

NLP can also be understood through different levels of language analysis.

### Lexical Analysis

Studies individual words and their structure.

### Syntactic Analysis

Studies sentence structure and grammar.

Example:

```text
"The dog eats food."
```

The system determines relationships between the subject, verb, and object.

### Semantic Analysis

Determines the **meaning** of words and sentences.

For example:

```text
bank
```

could mean:

* A financial institution
* The side of a river

The correct meaning depends on context.

### Discourse Analysis

Analyzes relationships between multiple sentences.

Example:

```text
John bought a car.
He loves it.
```

NLP should understand:

```text
"He" → John
"it" → car
```

### Pragmatic Analysis

Determines meaning based on **context and real-world knowledge**.

Example:

```text
"Can you open the window?"
```

Grammatically, it is a question about ability. In context, it is usually understood as a **request to open the window**.

---

## 6. Traditional NLP vs Modern NLP

### Rule-Based NLP

Uses manually created linguistic rules.

```text
IF sentence contains "excellent"
THEN sentiment = positive
```

**Advantages:**

* Easy to understand
* Predictable

**Disadvantages:**

* Difficult to scale
* Cannot handle every language variation

### Statistical NLP

Uses probabilities and statistical techniques learned from text data.

Common techniques include:

* Naive Bayes
* Hidden Markov Models (HMM)
* N-grams
* Conditional Random Fields (CRF)

### Machine Learning-Based NLP

Uses machine learning algorithms trained using textual features.

Common algorithms include:

* Logistic Regression
* Naive Bayes
* Support Vector Machines (SVM)
* Decision Trees

Traditional ML systems often require **feature engineering**.

### Deep Learning-Based NLP

Uses neural networks to automatically learn complex patterns from language.

Common architectures include:

* Recurrent Neural Networks (RNN)
* Long Short-Term Memory (LSTM)
* Gated Recurrent Units (GRU)
* Transformers

### Transformer-Based NLP

Modern NLP is dominated by the **Transformer architecture**.

Popular transformer-based models include:

* BERT
* GPT
* T5
* RoBERTa

Transformers use mechanisms such as **attention** and **self-attention** to understand relationships between words and process context effectively.

---

## 7. Text Representation in NLP

Computers cannot directly understand words, so text must be converted into numerical representations.

### Bag of Words (BoW)

Represents a document using word occurrence or frequency.

### TF-IDF

**Term Frequency-Inverse Document Frequency** assigns greater importance to words that are significant to a particular document but less common across the complete collection.

### Word Embeddings

Represent words as dense numerical vectors.

Popular methods include:

* Word2Vec
* GloVe
* FastText

### Contextual Embeddings

Modern models create representations based on the **context** in which a word appears.

For example:

```text
"I deposited money in the bank."
"I sat on the river bank."
```

A contextual model can represent the two meanings of **bank** differently.

---

## 8. Typical NLP Pipeline

A traditional NLP workflow may look like:

```text
Raw Text
   ↓
Text Cleaning
   ↓
Tokenization
   ↓
Stop Word Removal
   ↓
Stemming / Lemmatization
   ↓
Feature Extraction
   ↓
Model Training
   ↓
Prediction
   ↓
Evaluation
```

For modern transformer/LLM-based NLP, the pipeline may instead look like:

```text
Raw Text
   ↓
Tokenizer
   ↓
Tokens / Token IDs
   ↓
Embeddings
   ↓
Transformer Model
   ↓
Task-Specific or Generated Output
```

Modern models often require much less manual preprocessing.

---

## 9. NLP Model Evaluation

Different NLP tasks require different evaluation metrics.

Common metrics include:

* **Accuracy** — overall percentage of correct predictions
* **Precision** — how many predicted positives are actually positive
* **Recall** — how many actual positives were correctly identified
* **F1-score** — balance between precision and recall
* **BLEU** — traditionally used for machine translation
* **ROUGE** — commonly used for summarization
* **Perplexity** — evaluates how well a language model predicts text

Human evaluation is also important for generated language because automatic metrics do not always capture correctness, usefulness, or naturalness.

---

## 10. Applications of NLP

NLP is used in many real-world systems, including:

* Chatbots
* Virtual assistants
* Search engines
* Email spam detection
* Grammar checking
* Autocomplete
* Sentiment analysis
* Social media analysis
* Customer support
* Machine translation
* Document summarization
* Resume analysis
* Recommendation systems
* Voice assistants
* Question-answering systems
* Generative AI applications

---

## 11. Challenges in NLP

Human language is difficult for computers because it contains ambiguity and depends heavily on context.

Important challenges include:

### Ambiguity

```text
"I saw the man with the telescope."
```

Who has the telescope?

### Sarcasm

```text
"Great! My laptop crashed again."
```

The word "Great" appears positive, but the actual sentiment is negative.

### Context

The meaning of words often changes depending on surrounding words.

### Multiple Languages

Different languages have different:

* Grammar
* Vocabulary
* Sentence structures
* Writing systems

### Slang and Informal Language

```text
LOL
BRB
gonna
wanna
```

These may require contextual understanding.

### Bias

Models can learn undesirable biases from their training data.

### Hallucination

Generative NLP models may produce information that sounds convincing but is incorrect or unsupported.

---

## 12. NLP and Large Language Models (LLMs)

**Large Language Models (LLMs)** are modern AI models trained on very large amounts of textual data.

Examples include the GPT family and other transformer-based language models.

LLMs can perform many NLP tasks through a single general-purpose model, including:

```text
Text → Summarization
Text → Classification
Text → Translation
Text → Question Answering
Prompt → Text Generation
Documents → Information Extraction
```

Traditional NLP often creates a separate specialized model for each task, whereas LLMs can perform many tasks through prompting, fine-tuning, or other adaptation techniques.

---

## 13. NLP, NLU, and NLG

A simple relationship is:

```text
                NLP
                 |
        -------------------
        |                 |
       NLU               NLG
        |                 |
 Understand Language   Generate Language
```

**NLP** is the broader field.

**NLU** focuses mainly on understanding language.

**NLG** focuses mainly on generating language.

---

## 14. Simple NLP Architecture

```text
              Human Language
                    |
                    v
            +----------------+
            | Preprocessing  |
            +----------------+
                    |
                    v
            +----------------+
            | Tokenization   |
            +----------------+
                    |
                    v
            +----------------+
            | Representation |
            | / Embeddings   |
            +----------------+
                    |
                    v
            +----------------+
            |   NLP Model    |
            +----------------+
                    |
                    v
        +-------------------------+
        | Classification /        |
        | Extraction / Generation |
        +-------------------------+
                    |
                    v
                 Output
```

---

## 15. Summary

**Natural Language Processing (NLP)** enables computers to work with human language.

The two broad components are:

* **NLU** — understanding language
* **NLG** — generating language

Important NLP tasks include:

* Tokenization
* Stemming and lemmatization
* POS tagging
* Named Entity Recognition
* Sentiment analysis
* Text classification
* Information extraction
* Machine translation
* Summarization
* Question answering
* Text generation

NLP has evolved through:

```text
Rule-Based Systems
        ↓
Statistical NLP
        ↓
Machine Learning
        ↓
Deep Learning
        ↓
Transformers
        ↓
Large Language Models
```

Modern NLP systems increasingly use **transformers and LLMs** because they can understand contextual relationships and perform many language tasks within a single model.


----
# Types of Ambiguity in NLP

## What is Ambiguity?

**Ambiguity** in Natural Language Processing (NLP) occurs when a word, phrase, or sentence can have **more than one possible meaning or interpretation**.

Ambiguity is one of the major challenges in NLP because computers must determine the correct meaning using context.

---

## 1. Lexical Ambiguity

**Lexical ambiguity** occurs when a **single word has multiple meanings**.

### Example

> "He went to the bank."

The word **bank** can mean:

- A financial institution
- The side of a river

The NLP system must use the surrounding context to determine the intended meaning.

---

## 2. Syntactic Ambiguity

**Syntactic ambiguity** occurs when a sentence can have **more than one grammatical structure**.

It is also known as **structural ambiguity**.

### Example

> "I saw the man with the telescope."

Possible meanings:

1. I used a telescope to see the man.
2. I saw a man who had a telescope.

---

## 3. Semantic Ambiguity

**Semantic ambiguity** occurs when a sentence has more than one possible **meaning or interpretation**, even when its grammatical structure is understood.

### Example

> "Every student read a book."

Possible meanings:

1. All students read the same book.
2. Each student read a different book.

---

## 4. Pragmatic Ambiguity

**Pragmatic ambiguity** occurs when the intended meaning depends on **context, situation, or speaker intention**.

### Example

> "Can you open the door?"

Possible interpretations:

- Literal meaning: Asking whether the person is capable of opening the door.
- Intended meaning: Requesting the person to open the door.

NLP systems require contextual and real-world knowledge to understand such sentences.

---

## 5. Referential Ambiguity

**Referential ambiguity** occurs when it is unclear **which person, object, or entity a word refers to**.

### Example

> "John told Mike that he won."

The word **he** could refer to:

- John
- Mike

Resolving this type of ambiguity is important in **coreference resolution**.

---

## 6. Morphological Ambiguity

**Morphological ambiguity** occurs when a word or expression can have **multiple grammatical or morphological interpretations**.

### Example

> "Visiting relatives can be boring."

Possible meanings:

1. The activity of visiting relatives can be boring.
2. Relatives who are visiting can be boring.

---

## 7. Scope Ambiguity

**Scope ambiguity** occurs when the scope of **negation, quantifiers, or other operators** can be interpreted differently.

### Example

> "All students didn't pass."

Possible meanings:

1. No students passed.
2. Not all students passed.

---

## Summary

| Type | Description | Example |
|---|---|---|
| **Lexical** | A word has multiple meanings | "bank" |
| **Syntactic** | A sentence has multiple grammatical structures | "I saw the man with the telescope." |
| **Semantic** | A sentence has multiple possible meanings | "Every student read a book." |
| **Pragmatic** | Meaning depends on context or intention | "Can you open the door?" |
| **Referential** | Unclear what or whom a word refers to | "John told Mike that he won." |
| **Morphological** | A word/expression has multiple grammatical interpretations | "Visiting relatives can be boring." |
| **Scope** | Scope of negation or quantifiers is unclear | "All students didn't pass." |

---

## Easy Way to Remember

- **Lexical** → Word
- **Syntactic** → Structure
- **Semantic** → Meaning
- **Pragmatic** → Context
- **Referential** → Who/What
- **Morphological** → Word Form
- **Scope** → Range of Meaning
