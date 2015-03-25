---
layout: post
title: Question Answering
category: NLP
tags : [nlp, lecture notes]
---


Motivation: People ask questions online
- excite had 2.5 MM queries / day
- 8% were questions 


## Available tech
* Siri
* Aks jeeves
* wofram alpha
* IBM Watson

## Older systems
Text Retreieval Evaluation C
* Baseball 1961
	* baseball stats
* Eliza 1966
	* emulates psychiatrist
	* Answers questions in the frame of a question
	* doesnt acutall ''answer'' questions
* SHRDLU 1972
	* next 6 most frequent letters
	* answers sophisticated questions about boxes such as spatial awareness, size, color, keeps track of changes in enviroment
* Lunar 1972
	* Lunar Sciences Natural Language Informaiton System
	* mapping from semantic grammar to logic representation
* Murax 1973
	* open domain encyclopedia based
* Start 1977
	* open domain web based
* Start 1997
	* open domain
	* uses the web
	* online since 1993
* Deep red 1999
	* reading comprehension
* Jupiter 2000
	* spoken questions

## Most influencial systems
* AnSel
Predictive Annotation
Has components
* NLP/parsing
* knowledge/data base



# Evaluating Q&A systems
* Questions asked based on training corpus
* Answers assumed to be present
* Systems can return up to 5 passages of 50-250 bytes
* After 2002, single passage of 50 bytes, confidence score were used

## Metrics
MRR (mean reciprocal rank) 
* averge over all questions of  inverse ranks of truth in returned results


# Question type taxonomy
* factual, short answer
* definitial
* list
* crosslingual
* a series questions from a certain theme or that refrence eachother

Need to determine the difference between:
* yes/no vs who-
* facbutal vs procedural
* single answer vs multiple answers
* objective vs subjective
* context-specific (personalized) vs generic
* known answer vs unknown


Map sentence to question type taxonomy
examples: 
* SYN-classes (IBM AnSel)
* UIUC Questin types


# System archetecture
* IR
* Statistical aproaches using lots of data
* relatively little knowledge 
	* mostly wordnet

## System components
* Sources identification
* query modulation
	* query search engine, then search ranking
* sentence ranking
	* n-gram matching , Okapi
* answer extraction
	* question type classification
	* phrase chunking
* answer ranking
	* term frequency across result set would indicate a high rank for that potential answer

### Query Formulation
Determine which words to include in the IR query

### Passage retrieval
Short passage of text from the corpus that contain the query words
Include Proper nouns that match the query
Small distance between words in the query
Entities that match the expected answer type

### Redundancy
Should influence answer ranking




