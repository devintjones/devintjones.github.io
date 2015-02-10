---
layout: post
title: Maximum Entropy Models
category: Adv. Machine Learning
tags : [maximum entropy models, exponential family,class notes]
---


# Maxiumum Entropy Models cont''d

Build constraints for moments and fit a distribution. 
* Each linear constraint cuts the probability space with lines/half planes
	* Produces a convex set in the probability space
* Add epsilon to constraints to avoid over-fitting noisy data

Find max entropy by maximizing concave dual lagrangian objective funcion (solve for $$lambda$$)

The solution is globally unique because of concavity of obj. function
	* however, there may be many f(x) in this unique solution

## SVMs via Max Entropy Models
* SVM finds dist over theta, the paramters of the model
	* but other solutions close to theta may be almost as good
* Instead consider solving for a distribution P(theta)
	* Put high probability weigh ton good solutions
* Classify examples by aggregating expected value over the distribution of paramters/models

## Max Entropy Discrimination
* Max Ent applied to SVM

* 1 constraint per data point instead of per moment fn

* P(theta,b) = N(theta|0,I)N(b|0,sigma^2)
	* guassian distribution over SVM params
	* Use this to solve partition function, integrate over big theta => integrate over theta and b 
		* need to complete the square
* Produces an SVM

## MED: Nonlinear classifiers (without kernels)
* log likelihood ratio/classifier 
	* compare two distributions of models to return a classification
	* generative-style
* this breaks Max Entropy for SVM - non-convex
* can instead build a quadratic classifier
	* also a ratio of two normals with different mean/variance


