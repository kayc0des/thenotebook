# Bag of Words (BoW)

Bag of Words (BoW) is a simple and widely used technique in Natural Language Processing (NLP) to represent text data as numerical features. This method transforms text into a fixed-length vector of word occurrences.

## How it Works

1. **Text Preprocessing**: 
    - The input text (sentence or document) is split into individual words (tokenization).
    - Steps like lowercasing and removing punctuation or stopwords may be applied.

2. **Vocabulary Creation**:
    - A **vocabulary** is created from the input text, which consists of all the unique words present in the corpus.
    - Each word in the vocabulary is treated as a feature.

3. **Vector Representation**:
    - For each sentence or document, a vector is created where:
        - Each position corresponds to a word in the vocabulary.
        - The value at each position is the count of how many times the word appears in the sentence.
        - If the word does not appear in the sentence, its value is 0.

### Example

Consider the following sentences:

- Sentence 1: "I love programming"
- Sentence 2: "Programming is fun"
- Sentence 3: "I love fun"

The **vocabulary** from these sentences is: `['I', 'love', 'programming', 'is', 'fun']`

Now, using the vocabulary, the sentences can be represented as vectors:

- "I love programming" → `[1, 1, 1, 0, 0]`
- "Programming is fun" → `[0, 0, 1, 1, 1]`
- "I love fun" → `[1, 1, 0, 0, 1]`

### Key Characteristics of Bag of Words

- **Simple & Intuitive**: BoW is a straightforward method that provides a numerical representation of text based on word occurrences.
- **Order-agnostic**: The position of words in the sentence does not matter. Only the frequency of word occurrences is considered.
- **Sparse Representation**: As the vocabulary grows, vectors become large and sparse, containing mostly zeros.
- **Context Limitations**: BoW ignores the semantic meaning of words and context. It only considers how many times each word appears.

## Applications

- Text Classification
- Sentiment Analysis
- Information Retrieval
- Document Categorization

BoW is often used as a baseline technique in NLP before more complex models, such as TF-IDF and word embeddings like Word2Vec or GloVe, are applied.

---

### BoW using Sklearn

```python
from sklearn.feature_extraction.text import CountVectorizer

sentences = ["I love programming", "Programming is fun", "I love fun"]
vectorizer = CountVectorizer()
X = vectorizer.fit_transform(sentences)

print(vectorizer.get_feature_names_out())
print(X.toarray())
```

### BoW from Scratch - Intranet Assignment

[Source Code](https://github.com/kayc0des/alu-machine_learning/blob/master/supervised_learning/word_embeddings/0-bag_of_words.py)