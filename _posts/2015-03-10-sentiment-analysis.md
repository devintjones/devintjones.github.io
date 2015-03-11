---
layout: post
title: Sentiment Analysis
category: NLP
tags : [class notes, sentiment analysis]
---

# Research questions
* subjectivity analysis
	* extract subjective statement about an entity
* polarity analysis
* viewpoint analysis
* sentiment target
	* ie features of a product would be targets

# Other ares to note
## Level of granularity
document/sentence/attribute

## Opinion words
base/comparative

## Negation analysis

# Other examples of sentiment analysis
* product reviews
	* assigning stars based on polarity
* twitter

# Challenges in sentiment analysis
* subtlety
* concession
	* even though its great, I hate it
	* negation after praise
* manipulation
* sarcasm & irony

# SA as a classification problem
Set of features:
* words	
	* presence of words more important than frequency
* punct
* phrases
* syntax

# Training data
cornell movie review data

# Techniques
* KNN
* SVM
* Logistic Regression
* MaxEnt

# Resources
* CMU Twitter parser
	* bc twitter is such a unique datasource

# How to build a sentiment lexicon
## available softwares
* SentiWordNet
* General Inquirer
	* 2k pos words, 2k neg words
	* available on harvard website
* LIWC
* MPQA subjectivity lexicon

## Dictionary based methods
start with known pos/neg words
retreive sentiment from wordnet relationship

### Random-walk based methods
conduct 10k random walks on a graph
	* monte carlo method
start at unlabeled node, run until you reach a labeled node
count how many times you reach pos node vs neg node
* also see: 
	* harmonic functions
		* value of node is the average of its neighbors
	* power method

### How to build the graph
1. nodes are words
2. edges occur if two words are found in the same review
3. propogate known polarities

### PMI (Pointwise mutual information) - Turney
Check how off an unlabeled word appears with a positive word vs negative word
PMI(w_1,w_2) = log_2(w_1 near w_2 / (count_w1 * count_w2))
* quantified the association of any two words

# Information Extraction
from unstructred of semi-structered data
* ie not in a DB

entities
* who did what, where, why

build knowledge base

## Named entities
Types
* people
* locaitons
* orgs
	* teams
	* companies
* geo political entities

Ambiguity

Useful for intefaces to databases, question answering


## Sequence Labeling
* POS
* NER named entity rec
* SRL semantic role labling

Input: seuqence, output: labeled words
Methods: classificatoin
Features: previous tokens
* direction of 

## Named Entity Recognition (NER)
Segmentation
* Which words belong to a named entity?

Use classification
* what type of named entity is it?
* features: use gazetters, spelling, adjacent words, etc

### NER in biomedical 
Gene labeling


# Relation Extraction
example: MUC competition



