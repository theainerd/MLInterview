# Natural Language Processing

## How to clean your text data?

  - Remove all irrelevant characters such as any non alphanumeric characters
  - Tokenize your text by separating it into individual words
  - Remove words that are not relevant, such as “@” twitter mentions or urls
  - Convert all characters to lowercase, in order to treat words such as “hello”, “Hello”, and “HELLO” the same
  - Consider combining misspelled or alternately spelled words to a single representation (e.g. “cool”/”kewl”/”cooool”)
  - Consider lemmatization (reduce words such as “am”, “are”, and “is” to a common form such as “be”)
  - Consider removing stopwords (such as a, an, the, be)etc.

## What is Tokenization?

**Tokenization** is the process of converting a sequence of characters into a sequence of tokens.
Ex :RegexpTokenizer & Word Tokenize (scikit-learn)

## What is Stemming and lemmatization?

The goal of both stemming and lemmatization is to reduce inflectional forms and sometimes derivationally related forms of a word to a common base form.</br>
**Stemming** usually refers to a crude heuristic process that chops off the ends of words in the hope of achieving this goal correctly most of the time, and often includes the removal of derivational affixes. Different types of stemmers in NLTK are PorterStemmer, LancasterStemmer, SnowballStemmer.</br>
**Lemmatization** usually refers to doing things properly with the use of a vocabulary and morphological analysis of words, normally aiming to remove inflectional endings only and to return the base or dictionary form of a word, which is known as the lemma.

Note : It uses a knowledgebase called WordNet. Because of knowledge, lemmatization can even convert words which are different and cant be solved by stemmers, for example converting “came” to “come”.

## What is Bag of Words?
**Bag of words (BoW)** builds a vocabulary of all the unique words in our dataset, and associate a unique index to each word in the vocabulary.It is called a "bag" of words, because it is a representation that completely ignores the order of words.
![Bag of Words](https://github.com/theainerd/MLInterview/blob/master/images/bag.jpg)

## What is tf - idf?
**TF-IDF** reveals what words are the most discriminating between different bodies of text. It is particularly, helpful if you are trying to see the difference between words that occur a lot in one document, but fail to appear in others allowing you interpret something special about that document. It is dependent on term frequency, how often a word appears, and Inverse document frequency, whether it is unique or common among all documents.

## What is word2vec ?

It is a shallow two-layer neural networks that are trained to construct linguistic context of words.
It Takes as input a large corpus, and produce a vector space, typically of several hundred dimension, and each word in the corpus is assigned a vector in the space.
The key idea is context: words that occur often in the same context should have same/opposite meanings.
