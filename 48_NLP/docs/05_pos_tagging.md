# Parts of Speech Tagging


Part of Speech (POS) tagging in Natural Language Processing (NLP) is the process of labeling each word in a sentence with its corresponding grammatical category or "part of speech," such as noun, verb, adjective, adverb, etc. This helps in understanding the role of each word in a sentence and how it relates to the other words.

For example, in the sentence "The quick brown fox jumps over the lazy dog", POS tagging might label the words as follows:

- The: Determiner (DET)
- quick: Adjective (ADJ)
- brown: Adjective (ADJ)
- fox: Noun (NOUN)
- jumps: Verb (VERB)
- over: Preposition (PREP)
- the: Determiner (DET)
- lazy: Adjective (ADJ)
- dog: Noun (NOUN)

This step is essential in many NLP tasks like text parsing, machine translation, and sentiment analysis because it helps in analyzing the structure and meaning of a sentence.

## POS Tags

| **Tag** | **Description**                | **Example**                      |
|---------|---------------------------------|----------------------------------|
| **CC**  | Coordinating conjunction        | and, but, or                    |
| **CD**  | Cardinal number                 | one, two, 100                   |
| **DT**  | Determiner                      | the, a, an                      |
| **EX**  | Existential there               | there (as in "There is...")      |
| **FW**  | Foreign word                    | rendezvous, etc.                |
| **IN**  | Preposition/Subordinating conjunction | in, on, at, of, because        |
| **JJ**  | Adjective                       | quick, tall, beautiful           |
| **JJR** | Adjective, comparative          | faster, taller                  |
| **JJS** | Adjective, superlative          | fastest, tallest                |
| **LS**  | List item marker                | 1., a., etc.                    |
| **MD**  | Modal                           | can, should, would              |
| **NN**  | Noun, singular or mass          | dog, car, happiness             |
| **NNS** | Noun, plural                    | dogs, cars                      |
| **NNP** | Proper noun, singular           | Sarah, London                   |
| **NNPS**| Proper noun, plural             | Americans, Wednesdays           |
| **PDT** | Predeterminer                   | all, both, half                 |
| **POS** | Possessive ending               | 's, s'                          |
| **PRP** | Personal pronoun                | I, you, he, she                 |
| **PRP$**| Possessive pronoun              | my, your, his, her              |
| **RB**  | Adverb                          | quickly, very, well             |
| **RBR** | Adverb, comparative             | better, faster                  |
| **RBS** | Adverb, superlative             | best, fastest                   |
| **RP**  | Particle                        | up, off, out                    |
| **SYM** | Symbol                          | $, %, @, +                      |
| **TO**  | to (preposition or infinitive marker) | to (as in "to run")           |
| **UH**  | Interjection                    | oh, wow, oops                   |
| **VB**  | Verb, base form                 | run, jump, be                   |
| **VBD** | Verb, past tense                | ran, jumped, was                |
| **VBG** | Verb, gerund/present participle | running, jumping                |
| **VBN** | Verb, past participle           | run, jumped, been               |
| **VBP** | Verb, present tense, not 3rd person singular | run, jump, am           |
| **VBZ** | Verb, present tense, 3rd person singular | runs, jumps, is           |
| **WDT** | Wh-determiner                   | which, that                    |
| **WP**  | Wh-pronoun                      | who, what                      |
| **WP$** | Possessive wh-pronoun            | whose                          |
| **WRB** | Wh-adverb                       | where, when, why               |

### Example

```python
import nltk
from nltk.tokenize import word_tokenize
from nltk.tokenize import sent_tokenize
from nltk.corpus import stopwords

nltk.download('punkt')
nltk.download('stopwords')
nltk.download('average_perceptron_tagger')

corpus = "I'm currently having a bad day and I will like to get some rest. But I can't my employer expects the work to be submitted by the end of the day."

sentences = sent_tokenize(corpus)

for sentence in sentences:
    words = word_tokenize(sentence)
    words = [word for word in words if word not in set(stopwords.words('english'))]
    pos_tag = nltk.pos_tag(words)
    print(pos_tag)

""" Output
[('I', 'PRP'), ("'m", 'VBP'), ('currently', 'RB'), ('bad', 'JJ'), ('day', 'NN'), ('I', 'PRP'), ('like', 'VBP'), ('get', 'VB'), ('rest', 'NN'), ('.', '.')]
[('But', 'CC'), ('I', 'PRP'), ('ca', 'MD'), ("n't", 'RB'), ('employer', 'VB'), ('expects', 'VBZ'), ('work', 'NN'), ('submitted', 'JJ'), ('end', 'NN'), ('day', 'NN'), ('.', '.')]
"""
```