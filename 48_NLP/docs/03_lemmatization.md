# Lemmatization

emmatization is a process in natural language processing (NLP) that reduces words to their base or root form, known as the "lemma." Unlike stemming, which simply trims the end of words, lemmatization considers the meaning and context of the word to ensure it returns a valid word in the language. For example, the words "running," "ran," and "runs" would all be reduced to "run" through lemmatization. It requires understanding the part of speech (POS) of a word to decide its correct base form.

## Lemmatization with nltk

In the `WordNetLemmatizer` from the Natural Language Toolkit (NLTK), you can specify the part of speech (POS) tag for each word to improve the accuracy of lemmatization. WordNetLemmatizer requires the POS tag to understand how to correctly transform the word into its base form.

Here are the common POS tags used with WordNetLemmatizer:

- 'n' for nouns.
- 'v' for verbs.
- 'a' for adjectives.
- 'r' for adverbs.

If no POS tag is provided, the WordNetLemmatizer assumes the word is a noun by default, which may result in incorrect lemmatization for verbs or adjectives.

### Example

```python
from nltk.stem import WordNetLemmatizer

nltk.download('wordnet')
lemmatizer = WordNetLemmatizer()

print(lemmatizer.lemmatize("running", pos='v'))  # Output: 'run'
print(lemmatizer.lemmatize("better", pos='a'))    # Output: 'good'
```
