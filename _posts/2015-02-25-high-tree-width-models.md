---
layout: post
title: High Tree Width Models
category: Adv. Machine Learning
tags : [high tree width models]
---


# High Tree-Width Models
Beyond Junction Tree

junction tree becomes inefficient for 
* computer vision
* classification over a large social network (FB)
	* for a conditional probability, have to sum over the whole graph (2^n)

## Goals
* Perform inference on large networks
* Approach: find max and marginal of probability distribution over the graph
* Limitation: for cyclic these are intractable
* Methodolo

## Graphical Models
* G is a bipartite _factor graph_ with round variable vertices and square factor vertices. xi are discrete variables
	* We introduce functions to describe the square factor vertices \psi
	* This is a more specific representatoin of the graph - we can distinguesh the number of values need to describe the probability distribution over the graph

* Marginal inference and MAP inference are both NP-hard, and hard to approximate O(2^n)

* However on acyclic graphical models both are easy 
	* Belief propagation via junction tree
	* but most models are not acyclic

## Cyclic Graphical Models
* _Tree width:_ The size of largest clique after triangulation
	* Triangulatoin increased the size of the graph
	* Let''s try to skip triangulation
		* Junction Tree Algorithm will not converge
		* But generally works in practice

What are some models where we can skip triangulation and junction tree will converge?

## Bipartite matching (b-matching)
* Used in google adwords
	* For the example: Two constraints: one ad slot, one ad per advertiser
	* in reality, Google solves B matching with budget constraints - see paper by Vazeroni (?) on 'Adwords problem'
* Can be framed as a very looop graphical model
* However max-product also finds MAP solution in o(n^3) [HJ 2007]


### Bipartite generalized matching: More detail
4 words xi, 
4 advertisers, yi

find a list of advertisers for each word, find a list of words for each advertiser
constained by advertiser''s budget, and reciprocated matches

* Can frame bipartite message sequence as a tree, can prove that messages must alternate, and therefore converge

## Generalized matching vs. kNN
k=2 : [kissing number](http://en.wikipedia.org/wiki/Kissing_number_problem)
In high dimensional data, its possible for all data to select the same number (kissing number exponentially increases in high dimensions)

b-matching wil give a more robust neighbor seletion
* enforces constraint on the number of neighbors of each point

## Perfect Graphs

* A graph is perfect if for all subgraphs H, the coloring number of H  equals the size of the biggest clique in H (the clique number of H)
* State Strong Perfect Graph Conjecture, open for 50 years
* Many NP-hard problems become polynomial time for perfect grpahs
	* Graph coloing
	* Max clique
	* Max stable set

### Max Weight Stable Set
This is a linear program
* Clique constraint: Build matix of cliquex x vertices
* also constrain x >= 0 
* For perfect graphs, LP is binary and finds MWSS in O(sqrt(m)*n^2)

### Perfect graph theory
G is perfect if G contains no odd hole of antihold
* hole: and induced subgraph which is a (chordless) cycle of lenth at least 4. An odd hold has odd cycle length
* Anithole: the compliment of a hole

### Reduction: graphical model M -> NMRF N
given a graphical model M, construct a nand Markov random vield
* Map nodes in cliques in N to a clique group of N with one node for each config of x_c, all pairwise adjacent
* weights of each node in N set as psi_c(x_c) - min(psi_c(x_c)

-> 

* A MMWSS of the NMRF finds a MAP solution










