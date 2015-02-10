---
layout: post
title: Language Models Part 3
category: NLP
tags : [class notes]
---

# Language Models Part 3

## Evaluating Langugae Models

### Perplexity (PP)

Does the model fit the data?

PP logarithmic version
* per - 2^( (1-/N) * sum(log2(P(wi))))

### PP across distributions
Use cross-entropy = log(perplexity)

### Word Error Rate
Number of insertions, deletions, and substitions normalized by sentence length
Same as levenshtein edit distance

### Issues
* Out of vocabular words (OOV)
	* label as _RARE_
* Long distance dependencies
	* Distances longer than n cant fit into an n gram model
	* Can condition most recent subject or other syntax (like a modified n-gram)
		* Paper by Channing on courseworks discusses these other models

# Noisy channel models
Example: 
* speech recognition
* OCR (scanning a text document)

## Encoding and decoding
* Given f and e'', guess e
Ex: Where f is a translator, e'' is the translated text, and e is the original text. 

_e'' = argmax_e P(e|f) = argmax_e P(f|e) P(e)_ 

* P(f|e) is language model
* P(e) is translation model

## Uses
* handwriting recongnitoin
* text genreatoin
* text summarization
* machine translatoin
* spelling correction

# Hidden Markov Models for POS taggers

## The general markov model
* Sequence of RV that aren''t independent
* Uses
	* weahter reports
	* text

### Properties
* There is a limited horizon. 
	* ie weather today depends only on yesterday (this is a bigram)
* Time invariant/stationary
* There is a transition matrix A and initial state probabilities (big pi)
	* the same as a markov chain
* They use 'automata' to visualize different states of a markov chain

## HMM
* Motiviation
	* observe a sequence of symbols
	* the seuqnce of states that led to the genraitons of symbols is hidden
* Def:
	* Q = sequence of states
	* O = sequence of observations (drawn from a vocab)
	* po,pf = inital and final states
	* A = state transition probabilities
	* B = symbol emission probabilities
	* pi = initial state of probabilities
	* mu = (A,B,pi) - all parameters of probabilistic model


