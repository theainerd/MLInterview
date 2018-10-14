# Natural Language Processing

## How to clean your text data?

  - Remove all irrelevant characters such as any non alphanumeric characters
  - Tokenize your text by separating it into individual words
  - Remove words that are not relevant, such as “@” twitter mentions or urls
  - Convert all characters to lowercase((**Case folding**), in order to treat words such as “hello”, “Hello”, and “HELLO” the same. (Note)
  - Consider combining misspelled or alternately spelled words to a single representation (e.g. “cool”/”kewl”/”cooool”)
  - Consider lemmatization (reduce words such as “am”, “are”, and “is” to a common form such as “be”)
  - Consider removing stopwords (such as a, an, the, be)etc.

Note : For tasks like speech recognition and information retrieval, everything is mapped to lower case. For sentiment anal-
ysis and other text classification tasks, information extraction, and machine translation, by contrast, case is quite helpful and case folding is generally not done (losing the difference, for example, between US the country and us the pronoun can out-
weigh the advantage in generality that case folding provides)

## What is Tokenization?

**Tokenization** is the process of converting a sequence of characters into a sequence of tokens.
Ex :RegexpTokenizer & Word Tokenize (scikit-learn)</br>
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-10-04%2014-14-08.png)

## What is stop words?

**Stop words** are words that are particularly common in a text corpus and thus considered as rather un-informative.
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-10-04%2014-14-25.png)
## What is Stemming and lemmatization?

The goal of both stemming and lemmatization is to reduce inflectional forms and sometimes derivationally related forms of a word to a common base form.</br>

**Stemming** usually refers to a crude heuristic process that chops off the ends of words in the hope of achieving this goal correctly most of the time, and often includes the removal of derivational affixes. Different types of stemmers in NLTK are PorterStemmer, LancasterStemmer, SnowballStemmer.</br>
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-10-04%2014-14-52.png)

**Lemmatization** usually refers to doing things properly with the use of a vocabulary and morphological analysis of words, normally aiming to remove inflectional endings only and to return the base or dictionary form of a word, which is known as the lemma.</br>
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-10-04%2014-16-00.png)

Note : It uses a knowledgebase called WordNet. Because of knowledge, lemmatization can even convert words which are different and cant be solved by stemmers, for example converting “came” to “come”.

## Parts-of-Speech (POS) tagging

Part-of-speech tagging (POS tagging) is the task of tagging a word in a text with its part of speech. A part of speech is a category of words with similar grammatical properties. Common English parts of speech are noun, verb, adjective, adverb, pronoun, preposition, conjunction, etc. 

## Named Entity Recognition (NER)

In the Named Entity Recognition (NER) task, systems are required to recognize the Named Entities occurring in the text. More specifically, the task is to find Person (PER), Organization (ORG), Location
(LOC) and Geo-Political Entities (GPE). For instance, in the statement ”Shyam lives in India”, NER system extracts Shyam which refers to name of the person and India which refers to name of the country.

## Corefrence resolution(CR)

Coreference Resolution is the task which determines which noun phrases (including pronouns,
proper names and common names) refer to the same entities in documents . For instance, in the sentence, ”I have seen the annual report. It shows that we have gained 15% profit in this financial year”. Here, ”I” refers to name of the person, ”It” refers to annual report and ”we” refers to the name of the company in which that person works.(Kong et al., 2010)

## What is Bag of Words?
**Bag of words (BoW)** builds a vocabulary of all the unique words in our dataset, and associate a unique index to each word in the vocabulary.It is called a "bag" of words, because it is a representation that completely ignores the order of words.
![Bag of Words](https://github.com/theainerd/MLInterview/blob/master/images/bag.jpg)

## What is tf - idf?
**TF-IDF** reveals what words are the most discriminating between different bodies of text. It is dependent on term frequency, how often a word appears, and Inverse document frequency, whether it is unique or common among all documents. It is particularly, helpful if you are trying to see the difference between words that occur a lot in one document, but fail to appear in others allowing you interpret something special about that document.

**Example**:

Consider a document containing 100 words wherein the word cat appears 3 times. The term frequency (i.e., tf) for cat is then (3 / 100) = 0.03. Now, assume we have 10 million documents and the word cat appears in one thousand of these. Then, the inverse document frequency (i.e., idf) is calculated as log(10,000,000 / 1,000) = 4. Thus, the Tf-idf weight is the product of these quantities: 0.03 * 4 = 0.12.

## N gram

* n-gram is a contiguous sequence of n items from a given sample of text or speech
* An n-gram of size 1 is referred to as a "unigram"; size 2 is a "bigram" size 3 is a "trigram". Larger sizes are sometimes referred to by the value of n in modern language, e.g., "four-gram", "five-gram", and so on.</br>
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-10-04%2014-17-53.png)
* ngram model models sequence, i.e., predicts next word (n) given previous words (1, 2, 3, ..., n-1)
* multiple gram (bigram and above) captures **context**
* to choose n in n-gram requires experiments and making tradeoff between stability of the estimate against its appropriateness. Rule of thumb: trigram is a common choice with large training corpora (millions of words), whereas a bigram is often used with smaller ones.
* n-gram can be used as features for machine learning and downstream NLP tasks

## What is word2vec ?

It is a shallow two-layer neural networks that are trained to construct linguistic context of words.
It Takes as input a large corpus, and produce a vector space, typically of several hundred dimension, and each word in the corpus is assigned a vector in the space.
The key idea is context: words that occur often in the same context should have same/opposite meanings.
![](https://github.com/theainerd/MLInterview/blob/master/images/WordEmbeddings.png)

Two Algorithms:
* **Skip-Grams** : The skip-gram model does the exact opposite of the CBOW model, by predicting the surrounding context words
given the central target word.
* **Continuous Bag of Words (CBOW)**: CBOW computes the conditional probability of a target word given the context words surrounding it across a window of size k.

**Limitations**:

* When we want to obtain vector representations for phrases such as “hot potato” or “Boston Globe”. We can’t just simply combine the individual word vector representations since these phrases don’t represent the combination of meaning of the individual words. And it gets even more complicated when longer phrases and sentences are considered.
* use of smaller window sizes produce similar embeddings for contrasting words such as “good” and “bad”, which is not desirable especially for tasks where this differentiation is important such as sentiment analysis.At times these embeddings cluster semantically-similar words which have opposing sentiment polarities.



![](https://github.com/theainerd/MLInterview/blob/master/images/CBOW.png)

## NLP Metrics

**Perplexity** : The perplexity (sometimes called PP for short)
of a language model on a test set is the inverse probability of the test set, normalized
by the number of words. (*Smaller is better*)

Note : Perplexity does not guarantee an (extrinsic) im-
provement in the performance of a language processing task like speech recognition
or machine translation.


