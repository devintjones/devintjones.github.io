---
layout: post
title: NLP Lecture 3
category: NLP
tags : [class notes]
---

HW1 will be assigned next week. Based on the next 3 lectures - POS tagging. 

Numbers from lecture slides are out of order. 

3rd edition of Jurafsky book will be available in August. 

# Linguistics cont'd

## Language Diversity
7000 languages in the year. 
Language preservatoin is an initiative to preserve languages. 

## Language changes 
* Grimm's law
	* Voiceless stops turn into voicless fricatives
	* Voiced stops become voicelss stops
	* voiced aspriated stops change to voiced stops or fricatives. 
* Ex 1
	* ancinet greek
	* english foot swedish fot

## NACLO Problem
* challenge: identify similarities between languages. 
	* words, syntax are similar across differenct languages

* Beowulf (written in old english)
* historical computational linguistics

### Diversity of languages
 understand how they are different & how they are similar
* articles (a,the)
* cases (in latin, not in english)
	* pos determined by ending of word - order doesn't matter
* sound systems
	* velar fricatives
* social status
	* japanaese - your father vs someone else's father
* kinship systems

### Language univesals
two types: unconditional an docnditoinal
* ex: all languages ave verbs and nouns
* all spokne lanugages anve consonants and vowels

### (WALS: the World Atlas of Language Structures)[http://wals.info]
* feature 83a: order of object and verb
* (Ethnolgue)[http://www.ethnologue.com]
* Number of workds
* (Endangered languages)[www.endangeredlanguages.com]

# Syntactic Categories
substition test:
Natalie likes [balkc, persion, tabby, samll] cats. 
Open(lexical) and closed (functional) categories


## POS
* Nouns
	* vary in: number, gender, case (nominative, genitve, accusative, dative)
* Pronouns
	* vary in person, gender, number, case
	* reflixve and anphoric forms
* determiners 
	* articles, demonstratives (this, that)
* adjectives
	 describe properties
	attributeive adn predictive adjectives
	agreemtn
	comparitve and superliative
* verbs
	* vary in tense, number, person
	* can have gerunds an dinfinitive
	* aspect
	* progressive and perfective
	* voice (active/passive)
	* participles, auxiliaries
	* arguements
		* the dog sleeps (intranstiive)
		* the dog chased the cat (transtiive)
		* mary gave th edog a bone (ditranstivie)
	* irregular verbs
	* conjugation
* adverbs
* prepositions
* particles (phrasal verbs - 'to run up' up)
* coordinating conjunctions (and, or, but)
* subordinating conjunctions (if because, that, although)
* interjections

## POS Tags (some)


|---|---|
|NN | singular noun|
|IN | presopostion|
|AT | article|
|NP | proper noun|
|JJ | adjective|
|,  | comma|
|NNS| plural noun|
|CC | conjucntion|
|RB | adverb|
|VB | unflected verb|
|VBN| verb + en|
|VBD| verb + ed|
|CS | subordinating conjuciton|

## Penn Treebank
from the 90s, developed at U Penn (Marcus Santorini and Marcinkiewiz 93)

Size: 40,000 training sentences, 2400 test sentences

Genre: mostly WSJ and some spoken conversatoins
* Major criticism: only WSJ - some say that systems trained with penn tree bank will only work for news
Importance: helped launch modern automatic parsing me thods

Treebank-3

A more recent tree bank is American National Corpus - it contains genre, type of text and other things

### Peculiarities
* complementizers
* gaps
	* labeled as "NONE"
* SBAR
	* a sentence that has less sofisticated structure than a regular sentence

### trep
allows you to search the penn tree bank
similar to cypher

### Using treebanks
Can be used for:
* summary of occurances of events
* trainig systems
* evaluating systems

# The POS Task
### Some notes:
*Type & token
	*"To be or not to be " 6 words/tokens, 4 types
*11% of types but 40% of toekns in Brown corpus are ambiguous
* POS can determine pronounciatoin

## Main techniques
* rule based
* machine learning (conitional random fields, max entropy markov models)
* transformation-based

Usefule for parsing, translation, etc


## Evalution
Number of words is the same as number of POS
Will get a higher score if there are less POS in total
Can measure accuracy in the same way it is measured in ML

Baseline:
* Tag each word with its most likely tag
* Tag each out of vocab (OOV) word as a noun
* Around 90% accuracy
Current accuracy
* around 97% for English
* compared to 98% human performance

## Rule-based POS tagging
* use dicitonary or finite-stae transducers to find all possible pos
* use diambiguatoin rules
* hundreds of constraints can be designed manually


# Probabilities
## Probabilistic reasoning
* Very important for NLP
* some classes excluseively use probability & ML and avoid linguistics
* speech recognition example: "recognize speech" vs "wreck a nice beach"
 








