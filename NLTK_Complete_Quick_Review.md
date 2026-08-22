# NLTK Complete Quick Review

> A practical, copy-paste tutorial for learning and reviewing the Natural Language Toolkit (NLTK). Examples target Python 3 and current NLTK 3.x. This is a broad working guide, not an exhaustive reference to every NLTK class.

## Table of contents

1. [What NLTK is](#1-what-nltk-is)
2. [Installation and setup](#2-installation-and-setup)
3. [The basic NLP workflow](#3-the-basic-nlp-workflow)
4. [Tokenization](#4-tokenization)
5. [Text normalization and regular expressions](#5-text-normalization-and-regular-expressions)
6. [Stop words, stemming, and lemmatization](#6-stop-words-stemming-and-lemmatization)
7. [Part-of-speech tagging](#7-part-of-speech-tagging)
8. [Named-entity recognition](#8-named-entity-recognition)
9. [Corpora and lexical resources](#9-corpora-and-lexical-resources)
10. [Frequency distributions, n-grams, and collocations](#10-frequency-distributions-n-grams-and-collocations)
11. [WordNet](#11-wordnet)
12. [Text classification](#12-text-classification)
13. [Sentiment analysis with VADER](#13-sentiment-analysis-with-vader)
14. [Chunking and parsing](#14-chunking-and-parsing)
15. [A reusable preprocessing pipeline](#15-a-reusable-preprocessing-pipeline)
16. [Evaluation](#16-evaluation)
17. [Common errors and fixes](#17-common-errors-and-fixes)
18. [Quick-reference cheat sheet](#18-quick-reference-cheat-sheet)
19. [Practice exercises](#19-practice-exercises)
20. [Official references](#20-official-references)

---

## 1. What NLTK is

**NLTK** means **Natural Language Toolkit**. It is a Python library for Natural Language Processing (NLP): using software to analyze and transform human language.

NLTK is especially useful for:

- learning NLP concepts;
- tokenizing and cleaning text;
- stemming and lemmatization;
- part-of-speech tagging;
- named-entity recognition;
- accessing corpora such as Brown and Gutenberg;
- using WordNet;
- building traditional machine-learning text classifiers;
- experimenting with grammars and parsers.

NLTK is excellent for education and classical NLP. For large production pipelines or modern transformer models, tools such as spaCy and Hugging Face are often used alongside or instead of NLTK.

### Important vocabulary

| Term | Meaning | Example |
|---|---|---|
| Corpus | A collection of language data | movie reviews |
| Document | One text item in a corpus | one review |
| Sentence | A sequence of words expressing a thought | `NLP is useful.` |
| Token | A unit produced by tokenization | `NLP`, `is`, `useful`, `.` |
| Type | A unique token value | `useful` |
| Lexicon | Words plus information about them | WordNet |
| Lemma | Dictionary/base form | `run` for `running` |
| POS tag | Grammatical category | noun, verb, adjective |
| N-gram | A sequence of *n* tokens | `natural language` is a bigram |

---

## 2. Installation and setup

### 2.1 Try Jupyter / JupyterLite

At <https://jupyter.org/try-jupyter/lab/>, run this in a notebook cell:

```python
%pip install -U nltk
```

Then choose **Kernel → Restart Kernel** before importing NLTK. The uppercase `-U` means upgrade; lowercase `-u` is not the same option.

The Try Jupyter site can use different browser-based kernels. If `import piplite` fails, do not use it; use the `%pip` magic shown above.

### 2.2 Local Jupyter, terminal, or virtual environment

From a terminal:

```bash
python -m pip install --upgrade nltk
```

Inside a notebook:

```python
%pip install -U nltk
```

Restart the kernel after upgrading a package that has already been imported.

### 2.3 Verify the installation

```python
import nltk

print(nltk.__version__)
print(nltk.__file__)
```

### 2.4 Download commonly used NLTK data

NLTK code and NLTK data are separate. Many functions need a tokenizer model, tagger, corpus, or lexicon.

```python
import nltk

resources = [
    "punkt_tab",
    "stopwords",
    "wordnet",
    "omw-1.4",
    "averaged_perceptron_tagger_eng",
    "maxent_ne_chunker_tab",
    "words",
    "vader_lexicon",
]

for resource in resources:
    nltk.download(resource)
```

Optional learning corpora:

```python
for resource in [
    "brown",
    "gutenberg",
    "movie_reviews",
    "universal_tagset",
]:
    nltk.download(resource)
```

To open NLTK's interactive downloader in a supported desktop environment:

```python
nltk.download()
```

Browser notebooks may not support the graphical downloader. Use `nltk.download("resource_name")` instead.

### 2.5 What each common resource supports

| Resource | Used for |
|---|---|
| `punkt_tab` | sentence and word tokenization |
| `stopwords` | common stop-word lists |
| `wordnet` | English WordNet and lemmatization |
| `omw-1.4` | multilingual WordNet data |
| `averaged_perceptron_tagger_eng` | English POS tagging |
| `maxent_ne_chunker_tab` | English named-entity chunking |
| `words` | word list used by named-entity chunking |
| `vader_lexicon` | VADER sentiment scores |
| `brown` | tagged Brown corpus |
| `gutenberg` | public-domain literary texts |
| `movie_reviews` | positive/negative review corpus |
| `universal_tagset` | simplified universal POS tags |

---

## 3. The basic NLP workflow

A traditional NLP workflow is:

1. acquire text;
2. split it into sentences or words;
3. normalize it;
4. optionally remove punctuation or stop words;
5. stem or lemmatize when appropriate;
6. extract features;
7. analyze, visualize, or train a model;
8. evaluate the result.

The correct steps depend on the task. For example, punctuation and capitalization can carry sentiment, so removing them before sentiment analysis can hurt results.

```python
text = "NLTK makes language processing approachable. It is useful for learning NLP!"

from nltk.tokenize import sent_tokenize, word_tokenize

sentences = sent_tokenize(text)
tokens = word_tokenize(text)

print(sentences)
print(tokens)
```

---

## 4. Tokenization

Tokenization divides text into smaller units.

### 4.1 Sentence tokenization

```python
from nltk.tokenize import sent_tokenize

text = "Dr. Rao teaches NLP. Students enjoy it! Do you?"
sentences = sent_tokenize(text)

for sentence in sentences:
    print(sentence)
```

### 4.2 Word tokenization

```python
from nltk.tokenize import word_tokenize

text = "NLTK's tokenizer handles punctuation, too."
tokens = word_tokenize(text)
print(tokens)
```

### 4.3 Tokenize sentence by sentence

This preserves sentence boundaries:

```python
from nltk.tokenize import sent_tokenize, word_tokenize

text = "NLP studies language. NLTK helps us experiment."
tokenized_sentences = [word_tokenize(s) for s in sent_tokenize(text)]
print(tokenized_sentences)
```

### 4.4 `wordpunct_tokenize`

This tokenizer uses a regular-expression approach and normally does not require the Punkt model:

```python
from nltk.tokenize import wordpunct_tokenize

print(wordpunct_tokenize("I can't believe it's 3.5 miles!"))
```

### 4.5 Tweet tokenization

```python
from nltk.tokenize import TweetTokenizer

tokenizer = TweetTokenizer(
    preserve_case=False,
    reduce_len=True,
    strip_handles=False,
)

tweet = "@NLTK Wowwww! NLP is fun :) #python"
print(tokenizer.tokenize(tweet))
```

### 4.6 Tokenization rule of thumb

- Use `sent_tokenize` for general sentence splitting.
- Use `word_tokenize` for standard word/punctuation splitting.
- Use `TweetTokenizer` for social-media-style text.
- Use `RegexpTokenizer` when your application needs explicit rules.

---

## 5. Text normalization and regular expressions

Normalization makes text more consistent. Do only what benefits the task.

### 5.1 Lowercasing

```python
tokens = ["NLTK", "is", "Useful"]
lower_tokens = [token.lower() for token in tokens]
print(lower_tokens)
```

Lowercasing merges `Apple` and `apple`, but it can remove information needed for named entities.

### 5.2 Keep alphabetic tokens

```python
from nltk.tokenize import word_tokenize

text = "NLTK 3.x is useful—and free!"
tokens = word_tokenize(text)
words = [token.lower() for token in tokens if token.isalpha()]
print(words)
```

`isalpha()` removes punctuation and numbers. That is not always desirable.

### 5.3 Regular-expression tokenization

```python
from nltk.tokenize import RegexpTokenizer

tokenizer = RegexpTokenizer(r"[A-Za-z]+(?:'[A-Za-z]+)?")
print(tokenizer.tokenize("Raju's NLP lesson isn't difficult."))
```

### 5.4 Find patterns with Python's `re`

```python
import re

text = "Contact ana@example.com or bob@example.org."
emails = re.findall(r"[\w.+-]+@[\w.-]+\.[A-Za-z]{2,}", text)
print(emails)
```

### 5.5 Normalize whitespace

```python
import re

text = "NLP\tuses   text.\nNLTK helps."
clean_text = re.sub(r"\s+", " ", text).strip()
print(clean_text)
```

---

## 6. Stop words, stemming, and lemmatization

### 6.1 Stop words

Stop words are frequent function words such as `the`, `is`, and `at`. Removing them may help keyword or frequency analysis, but can damage meaning in some tasks. For example, removing `not` changes sentiment.

```python
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

stop_words = set(stopwords.words("english"))
text = "This is a simple example showing the removal of common words."

tokens = word_tokenize(text.lower())
filtered = [
    token for token in tokens
    if token.isalpha() and token not in stop_words
]

print(filtered)
```

Inspect or customize the list:

```python
print(sorted(list(stop_words))[:20])

custom_stop_words = stop_words - {"not", "no", "nor"}
```

### 6.2 Stemming

Stemming applies rules to remove affixes. The result may not be a dictionary word.

```python
from nltk.stem import PorterStemmer

stemmer = PorterStemmer()
words = ["connect", "connected", "connecting", "connection", "connections"]

for word in words:
    print(word, "->", stemmer.stem(word))
```

Snowball stemmer:

```python
from nltk.stem import SnowballStemmer

stemmer = SnowballStemmer("english")
print(stemmer.stem("generously"))
```

### 6.3 Lemmatization

Lemmatization uses a lexicon and returns a dictionary form. WordNet lemmatization works best when the correct part of speech is supplied.

```python
from nltk.stem import WordNetLemmatizer

lemmatizer = WordNetLemmatizer()

print(lemmatizer.lemmatize("cars", pos="n"))
print(lemmatizer.lemmatize("running", pos="v"))
print(lemmatizer.lemmatize("better", pos="a"))
```

WordNet POS codes:

| Code | Part of speech |
|---|---|
| `n` | noun |
| `v` | verb |
| `a` | adjective |
| `r` | adverb |

### 6.4 Stemming versus lemmatization

| Stemming | Lemmatization |
|---|---|
| rule-based trimming | vocabulary and morphology based |
| fast | usually slower |
| may produce nonwords | aims for dictionary forms |
| useful for rough matching | useful when linguistic form matters |

---

## 7. Part-of-speech tagging

Part-of-speech (POS) tagging labels tokens as nouns, verbs, adjectives, and other grammatical categories.

```python
from nltk import pos_tag
from nltk.tokenize import word_tokenize

sentence = "The curious student studies language carefully."
tokens = word_tokenize(sentence)
tagged = pos_tag(tokens)

print(tagged)
```

Common Penn Treebank tags:

| Tag | Meaning | Example |
|---|---|---|
| `NN` | singular noun | student |
| `NNS` | plural noun | students |
| `NNP` | proper noun | Python |
| `VB` | base verb | study |
| `VBD` | past-tense verb | studied |
| `VBG` | gerund/present participle | studying |
| `VBN` | past participle | written |
| `VBP` | non-third-person present verb | study |
| `VBZ` | third-person present verb | studies |
| `JJ` | adjective | useful |
| `RB` | adverb | quickly |
| `DT` | determiner | the |
| `IN` | preposition/subordinating conjunction | in |
| `PRP` | personal pronoun | she |

Get a tag explanation:

```python
import nltk

nltk.download("tagsets_json")
nltk.help.upenn_tagset("VBG")
```

Use the simpler universal tagset with a tagged corpus:

```python
from nltk.corpus import brown

print(brown.tagged_words(categories="news", tagset="universal")[:15])
```

### POS-aware lemmatization

```python
from nltk import pos_tag
from nltk.corpus import wordnet
from nltk.stem import WordNetLemmatizer
from nltk.tokenize import word_tokenize

lemmatizer = WordNetLemmatizer()

def treebank_to_wordnet(tag):
    first = tag[0].upper()
    return {
        "J": wordnet.ADJ,
        "N": wordnet.NOUN,
        "V": wordnet.VERB,
        "R": wordnet.ADV,
    }.get(first, wordnet.NOUN)

text = "The striped bats were hanging on their feet."
tagged = pos_tag(word_tokenize(text))
lemmas = [
    lemmatizer.lemmatize(word.lower(), treebank_to_wordnet(tag))
    for word, tag in tagged
    if word.isalpha()
]

print(lemmas)
```

---

## 8. Named-entity recognition

Named-entity recognition (NER) finds names of people, organizations, locations, and related categories.

```python
from nltk import ne_chunk, pos_tag
from nltk.tokenize import word_tokenize

sentence = "Satya Nadella leads Microsoft in the United States."
tokens = word_tokenize(sentence)
tagged = pos_tag(tokens)
tree = ne_chunk(tagged)

print(tree)
```

Extract entities into a list:

```python
entities = []

for subtree in tree:
    if hasattr(subtree, "label"):
        name = " ".join(word for word, tag in subtree.leaves())
        entities.append((name, subtree.label()))

print(entities)
```

NLTK's built-in NER is useful for teaching classical NER. Modern pretrained entity models generally provide broader coverage and higher accuracy.

---

## 9. Corpora and lexical resources

### 9.1 Gutenberg corpus

```python
from nltk.corpus import gutenberg

print(gutenberg.fileids())

words = gutenberg.words("austen-emma.txt")
sentences = gutenberg.sents("austen-emma.txt")
raw_text = gutenberg.raw("austen-emma.txt")

print(len(words))
print(sentences[0])
print(raw_text[:200])
```

### 9.2 Brown corpus

The Brown corpus contains texts from multiple genres.

```python
from nltk.corpus import brown

print(brown.categories())
print(brown.words(categories="news")[:20])
print(brown.tagged_sents(categories="news")[:1])
```

### 9.3 Movie reviews corpus

```python
from nltk.corpus import movie_reviews

print(movie_reviews.categories())
print(len(movie_reviews.fileids("pos")))
print(movie_reviews.words(movie_reviews.fileids("pos")[0])[:30])
```

### 9.4 NLTK `Text`

`nltk.Text` adds exploratory methods such as concordance and similar-word searches.

```python
import nltk
from nltk.corpus import gutenberg

emma = nltk.Text(gutenberg.words("austen-emma.txt"))
emma.concordance("woman", lines=5)
```

Other useful methods:

```python
emma.similar("woman")
emma.common_contexts(["woman", "man"])
```

---

## 10. Frequency distributions, n-grams, and collocations

### 10.1 Frequency distribution

```python
from nltk import FreqDist
from nltk.tokenize import word_tokenize

text = "NLP uses text. Text contains words, and words have patterns."
words = [w.lower() for w in word_tokenize(text) if w.isalpha()]

frequency = FreqDist(words)

print(frequency.most_common(5))
print(frequency["words"])
print(frequency.N())   # total sample count
print(frequency.B())   # number of unique samples
```

Plotting in a notebook:

```python
frequency.plot(10, cumulative=False)
```

### 10.2 Bigrams, trigrams, and general n-grams

```python
from nltk import bigrams, trigrams, ngrams

tokens = "natural language processing is useful".split()

print(list(bigrams(tokens)))
print(list(trigrams(tokens)))
print(list(ngrams(tokens, 4)))
```

### 10.3 Padding n-grams

```python
from nltk.util import pad_sequence
from nltk import bigrams

tokens = ["I", "learn", "NLP"]
padded = list(pad_sequence(
    tokens,
    n=2,
    pad_left=True,
    pad_right=True,
    left_pad_symbol="<s>",
    right_pad_symbol="</s>",
))

print(list(bigrams(padded)))
```

### 10.4 Collocations

Collocations are word combinations that occur together more strongly than chance alone would suggest.

```python
from nltk.collocations import BigramCollocationFinder
from nltk.metrics import BigramAssocMeasures
from nltk.tokenize import word_tokenize

text = "machine learning uses data and machine learning builds models"
tokens = [w.lower() for w in word_tokenize(text) if w.isalpha()]

finder = BigramCollocationFinder.from_words(tokens)
finder.apply_freq_filter(2)

measures = BigramAssocMeasures()
print(finder.nbest(measures.pmi, 10))
```

PMI can overvalue rare pairs, so applying a minimum frequency is usually important.

---

## 11. WordNet

WordNet groups words into synonym sets called **synsets** and records semantic relationships.

### 11.1 Synsets and definitions

```python
from nltk.corpus import wordnet as wn

synsets = wn.synsets("bank")

for synset in synsets[:5]:
    print(synset.name(), "->", synset.definition())
```

### 11.2 Lemmas and examples

```python
synset = wn.synset("car.n.01")

print(synset.definition())
print(synset.examples())
print(synset.lemma_names())
```

### 11.3 Hypernyms and hyponyms

- **Hypernym:** more general category, such as `vehicle` for `car`.
- **Hyponym:** more specific category, such as `ambulance` for `car`.

```python
car = wn.synset("car.n.01")

print(car.hypernyms())
print(car.hyponyms()[:10])
```

### 11.4 Antonyms

```python
for synset in wn.synsets("good"):
    for lemma in synset.lemmas():
        if lemma.antonyms():
            print(lemma.name(), "->", lemma.antonyms()[0].name())
```

### 11.5 Semantic similarity

```python
dog = wn.synset("dog.n.01")
cat = wn.synset("cat.n.01")
car = wn.synset("car.n.01")

print(dog.path_similarity(cat))
print(dog.path_similarity(car))
```

Similarity depends on the selected senses. Word-sense ambiguity must be handled before treating the score as definitive.

---

## 12. Text classification

Classification assigns a label to text. This example trains a Naive Bayes sentiment classifier using the NLTK movie-review corpus.

### 12.1 Prepare labeled documents

```python
import random
from nltk.corpus import movie_reviews

documents = [
    (list(movie_reviews.words(fileid)), category)
    for category in movie_reviews.categories()
    for fileid in movie_reviews.fileids(category)
]

random.Random(42).shuffle(documents)
print(len(documents))
```

### 12.2 Select vocabulary features

```python
from nltk import FreqDist

all_words = FreqDist(
    word.lower()
    for word in movie_reviews.words()
    if word.isalpha()
)

feature_words = [word for word, count in all_words.most_common(2000)]

def document_features(document):
    document_words = set(word.lower() for word in document)
    return {
        f"contains({word})": word in document_words
        for word in feature_words
    }
```

### 12.3 Build train and test sets

```python
feature_sets = [
    (document_features(words), label)
    for words, label in documents
]

split = int(0.8 * len(feature_sets))
train_set = feature_sets[:split]
test_set = feature_sets[split:]
```

### 12.4 Train and evaluate

```python
from nltk import NaiveBayesClassifier, classify

classifier = NaiveBayesClassifier.train(train_set)

accuracy = classify.accuracy(classifier, test_set)
print(f"Accuracy: {accuracy:.3f}")

classifier.show_most_informative_features(15)
```

### 12.5 Classify new text

```python
from nltk.tokenize import word_tokenize

review = "The story was moving and the performances were excellent."
features = document_features(word_tokenize(review))

print(classifier.classify(features))
print(classifier.prob_classify(features).prob("pos"))
```

### Important modeling lessons

- Split train and test data before making data-dependent choices.
- Use a fixed random seed for reproducibility.
- Accuracy alone can be misleading on imbalanced datasets.
- Do not evaluate a model on its training data.
- Traditional bag-of-words features ignore word order and much context.

---

## 13. Sentiment analysis with VADER

VADER is a rule- and lexicon-based sentiment analyzer designed for short, informal English text.

```python
from nltk.sentiment import SentimentIntensityAnalyzer

analyzer = SentimentIntensityAnalyzer()

examples = [
    "NLTK is excellent!",
    "The lesson was okay.",
    "I do not like this result.",
]

for text in examples:
    print(text)
    print(analyzer.polarity_scores(text))
```

The result contains:

- `neg`: negative proportion;
- `neu`: neutral proportion;
- `pos`: positive proportion;
- `compound`: normalized overall score from `-1` to `1`.

A simple label rule:

```python
def vader_label(text):
    compound = analyzer.polarity_scores(text)["compound"]
    if compound >= 0.05:
        return "positive"
    if compound <= -0.05:
        return "negative"
    return "neutral"

print(vader_label("This tutorial is very helpful!"))
```

VADER is not a universal truth detector. Domain language, sarcasm, context, and languages other than English require additional validation or different models.

---

## 14. Chunking and parsing

### 14.1 Noun-phrase chunking

Chunking uses POS-tag patterns to find phrases.

```python
from nltk import RegexpParser, pos_tag
from nltk.tokenize import word_tokenize

sentence = "The quick brown fox jumps over the lazy dog."
tagged = pos_tag(word_tokenize(sentence))

grammar = r"""
    NP: {<DT>?<JJ.*>*<NN.*>+}
"""

chunker = RegexpParser(grammar)
tree = chunker.parse(tagged)
print(tree)
```

Extract noun phrases:

```python
noun_phrases = [
    " ".join(word for word, tag in subtree.leaves())
    for subtree in tree.subtrees(lambda t: t.label() == "NP")
]

print(noun_phrases)
```

### 14.2 Context-free grammar

```python
import nltk

grammar = nltk.CFG.fromstring("""
    S  -> NP VP
    NP -> Det N | Det Adj N
    VP -> V NP
    Det -> 'the' | 'a'
    Adj -> 'curious'
    N -> 'student' | 'book'
    V -> 'reads'
""")

parser = nltk.ChartParser(grammar)
sentence = "the curious student reads a book".split()

for parse_tree in parser.parse(sentence):
    print(parse_tree)
```

A grammar only parses sentences covered by its vocabulary and rules. Real language needs much larger statistical or neural models.

---

## 15. A reusable preprocessing pipeline

The following pipeline lowercases, tokenizes, removes stop words and punctuation, and performs POS-aware lemmatization.

```python
from nltk import pos_tag
from nltk.corpus import stopwords, wordnet
from nltk.stem import WordNetLemmatizer
from nltk.tokenize import word_tokenize

STOP_WORDS = set(stopwords.words("english")) - {"no", "not", "nor"}
LEMMATIZER = WordNetLemmatizer()

def to_wordnet_pos(treebank_tag):
    return {
        "J": wordnet.ADJ,
        "N": wordnet.NOUN,
        "V": wordnet.VERB,
        "R": wordnet.ADV,
    }.get(treebank_tag[0].upper(), wordnet.NOUN)

def preprocess(text):
    tokens = word_tokenize(text)
    tagged_tokens = pos_tag(tokens)

    cleaned = []
    for token, tag in tagged_tokens:
        token = token.lower()
        if not token.isalpha():
            continue
        if token in STOP_WORDS:
            continue

        lemma = LEMMATIZER.lemmatize(token, to_wordnet_pos(tag))
        cleaned.append(lemma)

    return cleaned

sample = "The students were not enjoying the poorly written textbooks."
print(preprocess(sample))
```

This is not a universal pipeline. Adapt it to the task:

- preserve case for entity recognition;
- preserve punctuation, emojis, intensifiers, and negation for sentiment;
- preserve numbers for finance, measurements, and dates;
- avoid stop-word removal when word order or grammar matters.

---

## 16. Evaluation

### 16.1 Accuracy

```python
from nltk.metrics import accuracy

gold = ["pos", "neg", "pos", "pos"]
predicted = ["pos", "neg", "neg", "pos"]

print(accuracy(gold, predicted))
```

### 16.2 Precision, recall, and F-measure

NLTK's set-based metrics expect sets of item identifiers.

```python
from nltk.metrics import precision, recall, f_measure

gold_positive = {0, 2, 3}
predicted_positive = {0, 3}

print("Precision:", precision(gold_positive, predicted_positive))
print("Recall:", recall(gold_positive, predicted_positive))
print("F1:", f_measure(gold_positive, predicted_positive))
```

- **Precision:** of predicted positives, how many were correct?
- **Recall:** of actual positives, how many were found?
- **F1:** harmonic mean of precision and recall.

### 16.3 Confusion matrix

```python
from nltk import ConfusionMatrix

gold = ["pos", "neg", "pos", "pos", "neg"]
predicted = ["pos", "pos", "pos", "neg", "neg"]

matrix = ConfusionMatrix(gold, predicted)
print(matrix)
```

---

## 17. Common errors and fixes

### Error: no matching distribution for `-u`

Incorrect:

```python
!pip install -u nltk
```

Correct:

```python
%pip install -U nltk
```

The option is case-sensitive.

### Error: `No module named 'nltk'`

Install NLTK into the notebook's active kernel:

```python
%pip install nltk
```

Restart the kernel and import it again.

### Error: `No module named 'piplite'`

The notebook is likely not using the Pyodide kernel. On Try Jupyter's Xeus Python kernel, use:

```python
%pip install -U nltk
```

Do not import `piplite` when it is unavailable.

### Error: `module 'nltk' has no attribute 'internals'`

This can occur when NLTK was upgraded while an older version remained loaded.

1. Choose **Kernel → Restart Kernel**.
2. Run:

```python
import nltk
import nltk.internals

print(nltk.__version__)
```

### Error: `LookupError: Resource ... not found`

Read the error message to find the resource name, then download it:

```python
import nltk
nltk.download("punkt_tab")
```

Common examples:

```python
nltk.download("stopwords")
nltk.download("wordnet")
nltk.download("averaged_perceptron_tagger_eng")
nltk.download("vader_lexicon")
```

### Find NLTK's data search paths

```python
import nltk
print(nltk.data.path)
```

### Browser/JupyterLite limitations

JupyterLite runs Python in the browser rather than on a normal Python server. Some packages, network downloads, native extensions, file-system operations, and desktop GUIs may be unavailable or behave differently. If a required NLTK dataset cannot be downloaded in the browser environment, use local Jupyter, Google Colab, or another full Python environment.

---

## 18. Quick-reference cheat sheet

```python
# Installation in Jupyter
%pip install -U nltk
```

```python
# Import and download data
import nltk
nltk.download("punkt_tab")
```

```python
# Sentence and word tokenization
from nltk.tokenize import sent_tokenize, word_tokenize
sentences = sent_tokenize(text)
tokens = word_tokenize(text)
```

```python
# Stop words
from nltk.corpus import stopwords
stop_words = set(stopwords.words("english"))
```

```python
# Stemming
from nltk.stem import PorterStemmer
stem = PorterStemmer().stem("running")
```

```python
# Lemmatization
from nltk.stem import WordNetLemmatizer
lemma = WordNetLemmatizer().lemmatize("running", pos="v")
```

```python
# POS tagging
from nltk import pos_tag
tagged = pos_tag(tokens)
```

```python
# Named entities
from nltk import ne_chunk
entities = ne_chunk(pos_tag(tokens))
```

```python
# Frequency distribution
from nltk import FreqDist
frequency = FreqDist(tokens)
print(frequency.most_common(10))
```

```python
# N-grams
from nltk import ngrams
three_grams = list(ngrams(tokens, 3))
```

```python
# WordNet
from nltk.corpus import wordnet as wn
synsets = wn.synsets("language")
```

```python
# VADER sentiment
from nltk.sentiment import SentimentIntensityAnalyzer
scores = SentimentIntensityAnalyzer().polarity_scores(text)
```

```python
# Naive Bayes classifier
from nltk import NaiveBayesClassifier
classifier = NaiveBayesClassifier.train(train_set)
label = classifier.classify(features)
```

---

## 19. Practice exercises

### Beginner

1. Tokenize a paragraph into sentences and words.
2. Count the ten most frequent alphabetic words.
3. Remove English stop words but retain `not`, `no`, and `nor`.
4. Compare Porter stemming with WordNet lemmatization.
5. POS-tag a sentence and print only its nouns.

### Intermediate

1. Build a function that returns POS-aware lemmas.
2. Extract named entities from a news paragraph.
3. Find frequent bigrams after removing punctuation and stop words.
4. Compare VADER scores for text with and without punctuation.
5. Explore how `dog`, `cat`, and `car` differ in WordNet similarity.

### Advanced

1. Train a Naive Bayes classifier with the movie-review corpus.
2. Compare unigram features with unigram-plus-bigram features.
3. Report accuracy, precision, recall, F1, and a confusion matrix.
4. Create a chunk grammar for noun and verb phrases.
5. Analyze errors and explain which linguistic signals the model misses.

---

## 20. Official references

- [NLTK home and documentation](https://www.nltk.org/)
- [Natural Language Processing with Python — NLTK Book](https://www.nltk.org/book/)
- [NLTK API reference](https://www.nltk.org/api/nltk.html)
- [Installing NLTK data](https://www.nltk.org/data.html)
- [NLTK how-to guides](https://www.nltk.org/howto/)
- [WordNet interface](https://www.nltk.org/howto/wordnet.html)
- [Collocations guide](https://www.nltk.org/howto/collocations.html)
- [VADER API](https://www.nltk.org/api/nltk.sentiment.vader.html)
- [JupyterLite Python kernels](https://jupyterlite.readthedocs.io/en/stable/howto/configure/kernels.html)

---

## Suggested learning order

For a fast review, study sections in this order:

1. tokenization;
2. normalization;
3. stop words, stemming, and lemmatization;
4. POS tagging;
5. frequency distributions and n-grams;
6. corpora and WordNet;
7. named entities and chunking;
8. sentiment and classification;
9. evaluation.

The main habit to develop is to match preprocessing to the task. More cleaning is not automatically better: every removed token can also remove useful information.
