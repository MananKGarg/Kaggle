# Intro to NLP

Text is some of the most valuable data for the ones who know how to use it. In this course about **NLP** , we will use the NLP library (spaCy) to take on some of the most important tasks in working with text.

We will learn - 

* Basic text processing and pattern matching.
* Building machine learning models with text.
* Represent text with word embeddings that numerically capture the meaning of words and documents.

## 1. NLP with SpaCy

* spaCy has language specific models that come in various sizes. We can load a spaCy model with ```python spaCy.load()```. For example

```python

import spacy
nlp = spacy.load('en')
```

* We can process text with inputing it in the model like - 

```python

doc = nlp("Tea is healthy and calming, don't you think?")

```

## 2. Tokenizing

* Returns a document object that contains tokens which are units of text in document like individual words and punctuations. spacy splits contractions like don't into tokens,"do" and "n't". We can see tokens by looping over the text in document

```python

for token in doc:
    print(token)
    
 output - 
 
 Tea
is
healthy
and
calming
,
do
n't
you
think
?
```

* Each of the tokens come with additional and sometimes unuseful information.

## 3. Text Preprocessing

* **Lemmatizing** - 'Lemma' of a word is it's base form. 'Talk' is the lemma of 'talking','talked' etc. ```python token.lemma_``` returns lemma.
* **Stopwords** - These are words that occur in the language but don't contain much information. Examples are 'the','is','and'etc. ```python token.is_stop ``` returns a boolean True if the token is a stopword.

```python

print(f"Token \t\t Lemma \t\t Stopword".format('Token','Lemma','Stopword'))
print('-'* 40)
for token in doc:
    print(f"{str(token)}\t\t{str(token.lemma)}\t\t{str(token.is_stop)}"
    
output - 

Token 		Lemma 		Stopword
----------------------------------------
Tea		    tea		    False
is		be		        True
healthy		healthy		False
and		and		        True
calming		calm		  False
,		,		            False
do		do		        True
n't		not		        True
you		-PRON-		    True
think		think		    False
?	 	?		            False

```
* Lemmatisinf and dropping stopwords is important to reduce noise in the text data and focus on the important stuff.

## 4. Pattern Matching

* It refers to matching tokens or phrases in the text. When we need to match individual tokens, we can use **Matcher** and **PhraseMatcher** when we need to use list of terms.Let us search smartphone models in a piece of text. We create PhaseMatcher first.

```python

from spacy.matcher import PhraseMatcher
matcher = PhraseMatcher(nlp.vocab, attr='LOWER')
```

* The matcher is created using vocabulary of our model.
* Next you create a list of terms to match in the text. The phrase matcher needs the patterns as document objects. The easiest way to get these is with a list comprehension using the nlp model.

```python

terms = ['Galaxy Note', 'iPhone11', 'iPhone XS', 'Google Pixel']
patterns = [nlp(text) for text in terms]
matcher.add("TerminologyList", None, *patterns)

```
* Then we create a from text to search and use phrase matcher to find where the terms occur in text.

```python

text_doc = nlp("Glowing review overall, and some really interesting side-by-side "
               "photography tests pitting the iPhone 11 Pro against the "
               "Galaxy Note 10 Plus and last year’s iPhone XS and Google Pixel 3.") 
matches = matcher(text_doc)
print(matches)

output - 

[(3766102292120407359, 17, 19), (3766102292120407359, 22, 24), (3766102292120407359, 30, 32), (3766102292120407359, 33, 35)]

```

The matches here are match id'd and positions of start and end of phrase.

```python

match_id, start, end = matches[0]
print(nlp.vocab.strings[match_id], text_doc[start:end])

output - 

TerminologyList iPhone 11
```




























