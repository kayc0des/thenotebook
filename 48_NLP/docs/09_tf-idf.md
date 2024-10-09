# TF-IDF

Term Frequency-Inverse Document Frequency is a numerical statistic that reflects how important a term is to a document in a collection or corpus. It is often used as a weight in information retrieval and text mining.

## Term Frequency (TF)

The Term Frequency (TF) measures how frequently a term appears in a document. It is calculated as the ratio of the number of times a term appears in a document to the total number of terms in the document.

## Inverse Document Frequency (IDF)

The Inverse Document Frequency (IDF) measures the importance of a term across documents in a corpus. It is calculated as the logarithm of the ratio of the total number of documents to the number of documents containing the term.

## Calculation

The TF-IDF score for a term in a document is calculated by multiplying the TF and IDF scores for that term.

## Example

Let's say we have a corpus with 10 documents and we want to calculate the TF-IDF score for the term "cat" in document 1.

1. Calculate the TF score for "cat" in document 1:
   - Let's say "cat" appears 3 times in document 1 and the total number of terms in document 1 is 100.
   - TF = 3 / 100 = 0.03

2. Calculate the IDF score for "cat":
   - Let's say the term "cat" appears in 2 documents.
   - IDF = log(10 / 2) = log(5) ≈ 0.69897

3. Calculate the TF-IDF score for "cat" in document 1:
   - TF-IDF = TF * IDF = 0.03 * 0.69897 ≈ 0.0209691

## Usage

TF-IDF is widely used in information retrieval, text mining, and natural language processing. It helps in ranking documents based on their relevance to a query and in feature extraction for machine learning models.

## Implementation in Python

You can use the `TfidfVectorizer` class from the `sklearn` library to calculate the TF-IDF scores for a corpus of documents.

```python
from sklearn.feature_extraction.text import TfidfVectorizer

corpus = ["This is a sample document.", "This document is another example."]

vectorizer = TfidfVectorizer()
X = vectorizer.fit_transform(corpus)

print(X.toarray())
print(vectorizer.get_feature_names_out())
```

This code will output the TF-IDF scores for each term in the corpus.
