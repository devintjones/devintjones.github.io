---
layout: post
title: Log linear, Logistic Regression and Conditional Random Fields
category: Adv. Machine Learning
tags : [maximum entropy models, exponential family,class notes]
---


# Log linear, Logistic Regression and Conditional Random Fields

## Generative model
Max likelihood Gaussians
* Choose family of cuntoins ptheta(x,y) parametrized by theta
* Find theta by maximizing likelihood over teh functions ptheta
* Can use this for classification by maximizing probability over y (the output)

## Conditional Learning
Logistic regression
* Instead, maximize the conditional likelihood (instead of maximizing the joint)
* We have a distribution over the paramters, and the function returns a probability

## Discriminative Learning
SVMs
* Most aggressive approach
* Minmizes classification error
* Will return only the best output, or right/wrong in the classification case

# Examples 

## Max entropy genreative
Simple case: discrete, 2 class output. Frame bernouli as exponential family

exponential family form:
p(y|theta) = h(y)exp(theta_transp * f(y) - a(theta))

-> Unsupervised generative learning. 
Find theta that maximizes the likelihood over y -> MLE for theta
To parameterize the exponential family _distribution_

## Conditional: Logistic Regression
Given iid data y in {0,1}, binary loigstic regression computes a _probability_ for y = 1

p(y|x,theta) = ..(get from slides)
Function now depends on x and theta (not only theta as before), 
Returns y = argmax_y p(y|x,theta)

This is an example of a log-linear model

### The multi-class case

Feature vector is now a matrix [N,k] where k is the number of classes

## Conditional Random Fields
CRFs generalize max entropy 
Its a log-linear model with big n (# of classes)
Objective function is concave

Traditionally max ent, log linear, and CRFs were trained using *majorizatoin*
	* The EM algo is a majorization method
Algos were caled *improved iterative scaling* or *generalized iterative scaling*

### Majorizatoin
If cost funciton has no closed form solution, use a surrogate funciton Q with closed form update to monotonically minimuze the cost from an initial theta*

But, gradient descent apears to be faster.
	* But newer majorization methods are faster still

### Gradient Ascent for CRF
Same as minimizing the sum of log parittion functions plus linear


