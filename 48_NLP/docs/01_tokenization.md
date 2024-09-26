# Tokenization in Natural Language Processing

Please read through the document before checking out the code tutorial
[Code Tutorial: Tokenization](https://github.com/kayc0des/thenotebook/blob/main/48_NLP/tutorial/01_tokenization.ipynb)

## Introduction: Basic Terminologies

1. `Corpus`: A collection of written or spoken texts that are used for training and analyzing language models. It’s like a large dataset of language, usually stored as text files, that helps machines learn how humans use language. For example, a collection of news articles could be a corpus.

2. `Documents`: Individual pieces of text within a corpus. Each document can be a single article, a book, a sentence, or even a tweet—basically, any unit of text that makes up the corpus. If a corpus is a library, each document is a book or an article.

3. `Vocabulary`: The set of unique words or tokens in a corpus. It’s like a dictionary of all the words that appear across the documents in the corpus. For instance, if your corpus has 1000 different words, those words make up the vocabulary.

4. `Words`: The basic units of language found in the text. In NLP, words (also called tokens) are the individual elements of a document or corpus. They are the building blocks that make up sentences and are analyzed to find patterns, meanings, and relationships.

## Tokenization

Given a paragraph like: 

    "Natural Language Processing (NLP) is a field of artificial intelligence that focuses on the interaction between computers and human language. Through NLP, machines can understand, interpret, and generate human languages, making it possible for applications like chatbots, voice assistants, and language translation tools to function. Techniques like tokenization, stemming, and lemmatization help break down text into manageable units for processing. Word embeddings, on the other hand, provide meaningful numeric representations of words, enabling models to capture relationships between words based on their usage. As NLP continues to evolve, its impact on technology and everyday life becomes increasingly significant."

This paragraph will be my entire `Corpus`

Perfoming a `Tokenization operation` on the corpus above will be converting the paragraph into individual sentences (documents)

- Document 1

    Natural Language Processing (NLP) is a field of artificial intelligence that focuses on the interaction between computers and human language.

- Document 2

    Through NLP, machines can understand, interpret, and generate human languages, making it possible for applications like chatbots, voice assistants, and language translation tools to function.

- Document 3

    Techniques like tokenization, stemming, and lemmatization help break down text into manageable units for processing.

- Document 4

    Word embeddings, on the other hand, provide meaningful numeric representations of words, enabling models to capture relationships between words based on their usage.

- Document 5

    As NLP continues to evolve, its impact on technology and everyday life becomes increasingly significant.


Performing further `Tokenization` on each document will convert the sentences/documents into separate `Words`

### `Vocabulary` a set of unique words across all documents or in the entire corpus

```python
vocab = [natural, language, processing, nlp, is, a, field, of, artificial, intelligence, that, focuses, on, the, interaction, between, computers, and, human, through, machines, can, understand, interpret, generate, languages, making, it, possible, for, applications, like, chatbots, voice, assistants, translation, tools, to, function, techniques, tokenization, stemming, lemmatization, help, break, down, text, into, manageable, units, processing, word, embeddings, provide, meaningful, numeric, representations, words, enabling, models, capture, relationships, based, their, usage, as, continues, evolve, its, impact, technology, everyday, life, becomes, increasingly, significant]
```