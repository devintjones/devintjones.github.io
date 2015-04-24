---
layout: post
title: Final exam notes
category: NLP
tags : [class notes]
---

# Slides
1: Intro to NLP
2: Basic NLP pipeline (understanding & generation)
	* ambiguities
		* syntactic
		* morphological
	* genres of text
		* news
		* medical records
		* tweets (noah smith parser)
	* dont need history of alc
3: Ambiguity
	* syntax vs semantics
	* colang is void of ambiguity (not real langugaes)
	* synonyms & paraphrases
	* phonetics & morphology
		* had morphology on midterm
4: Linguistics
	* different writing systems
	* languages are related to each other
5: Parts of Speech (HW1)
	* substitution test
	* open pos vs closed
	* penn tree bank pos set
6: Morphology & Lexology
	* morph: finding root word
	* Semantics vs pragmatics

skipped 7 & 8

9: Preprocessing
	* normalization & stemming
	* segmentation
	* sentence boundary recognition
10: Syntax (HW2)
	* pos
	* constituents (must be mutually exclusive)
	* syntactic structure of sentence
	* optional categories (pp is optional, vp is not)
	* pp ambiguity (important, also in parsing chapter)
	* repetition (how it can be represented in CFG)
	* nested sentences (...such that...)
		* recursion
	* skip meta-patterns
11: Into to parsing
	* syntactic ambiguities
	* applications of parsing
		* grammer checking
		* quesiton answering
		* summarizagin
		* machine translation
* Context-free grammars
	* CKY (implemented in NLTK)
	* phrase strucutre gramers (same as CFG)
	* penn treebank
	* leftmost derivation
		* replace leftmost non-terminal with possible expansion
* Classic parsing methods
	* parsing as search
		* top-down (can fail)
		* bottom up 
		* solution: dynamic programming
	* CKY parser
	* Shift-reduce parsing
		* first was used for constituent (we used for dependency parsing)
		* bottom up
		* tries to match RHS of a production until it can build S
		* shift operation
		* reduce operation (terminal node)

12: CKY Parsing
	* requires chomskey grammer (?)
	 


