---
layout: post
title: Wordnet
category: NLP
tags : [class notes]
---

# Wordnet
A lexical database for english

Created/maintained by Fellbaum, Christiane (2005)

Mostly nouns and verbs
Each word has multiple senses (definitions) for each POS

Interface in nltk or web-based search

Wordnet maintains a  heirarchy/tree structure of words/their meanings

## Compare similarity of words using wordnet

### Version 1
* sim(v,w) = -pathlength(v,w)

### Version 2
* sim(v,w) = -log(pathlength(v,w))

Problems - trees could be very dense or imbalanced

### Version 3
* sim(v,w) = -log P(LCS(vw,w))
	* LCS - lowest common subsumer (parent node)

### Version 4 (DekangLin)
* Wordnet augment with probabilities(lin 1998)
* IC(C) = -log(P(C))
	* IC -> information content
* sim(v,w) = 2 log P(LCS(v,w)) / (log P(v) + log P(w))

## Wordnet similarity
* Library wordnetsimilarity - implements all above methods
* NLTK
	* lin_similarity()

# Text similarity
The vector space model

## Document similarity
### Cosine similarity
* Information retrieval to determine which doc is similar to a query
* use noemalized dot product of two vectors
	* vectors are frequencies of words
* will get a perfect similarity if there are the word frequencies are the same proporition - word order does not matter
* will get no similarity if the intersect of words in the documents is null

### (Jaccard coefficient)[http://en.wikipedia.org/wiki/Jaccard_index]
* intersect over the union
* ignored frequencies of words

## Vector space model applied to word similarity
### Distributional Similarity
Two words that appear in similar contexts are likely to be semantically related
* "You will know a word by the company that it keeps." ( JR Firth 1957 )
	* in computational ling. - collocation determines meaning

_context_ defined as:
* word before the target word
* word after the target word
* with n words of the target word
* within a specific syntactic relationship of the target
* any word in the same sentence
* any word within the same doc

### Associatoin Strength
* ignore pairs with low frequencies
	* however, this is not sufficient
* a common technique is poinwise mutual information (PMI)
* $w$ is a word and $c$ is a feature from the context

\[ PMI(w,c) = log \frac{P(W,c)}{P(w)P(c)} \]

Measures the strength of the relationship of two words


# Text Kernels
In the case where there are the same words but differetn word order changes the meaning of the sentence

One method: Transform feature space to cartesian product of words and their syntactic representation (subject, verb, noun phrase etc)
another: Use the bigrams as features

## Unigram kernel
Same as bag of words

## Longer ngrams
useful in information retireval - fast retrieval of similar docs

## Letter and substring kernels
* letter n grams - used for spelling correction, langugae recognition, and named entity recognition






