---
layout: post
title: Feature and Kernel Selection
category: Adv. Machine Learning
tags : [feature selection]
---

# Feature selection & sparcity

Isolates interesting dimension of data for a task
Reduces complexity of data
Augments sparse vectors (SVMs) w sparse dimensions
Can _improve generalization_

Example:
* find the subset of features that lives the largest margin SVM

Typically needs exponential search (if we consider all possible subsets of dimensions)

How to do this eficiently (and jointly) with SVM?

# Filtering & Wrapping


## Filtering
Find/eliminate some features before even training

### Fisher Information Criterion

Compute this for each feature for over the two classes, keep top d features

* this fits a Gaussian over each class - could be the wrong assumption
	* only measures how linearly separable data is

### Pearson Correlation Coefficients
Score how similar/redundant features are
* Gaussian assumption
* Covariance matrix obsevation ij divided by the product of root diagonals for i and j

### Kolmogorov-Smirnov Test
Like Pearson but,
Non-parametric, ore general than gaussian, but only 1 feature at a time
* For each feature, compare the empirical cumulative distribution over both classes with the cumulutive given y=1. 
* Identify max distance between the two distribution functions -> KS distance
* Find KS score, keep top d features


## Wrapping 
Find/eliminate by evaluating accuracy after you train your classifier

Incorporate a binary vector s that selects features
* take element-wise product of s and x to select features
* pre-specfiy a max number/% of features

### Marign & Radius Bound

Or, optimize a generalization bound (SRM vs ERM)
* SRM structural risk minimization (SVMs do this)
* ERM imperirical risk min

Like VC-bound
Incorporates max margin (seperability) and min data radius (variance) in Hilbert space
Professor presented the dual solution

Then, try to compute gradient over s, the feature selector
* but constrain to the binary space
=> gradient is partial derivative of R^2*W^2 over s
* R^2: lock betas

### Better Span Bound
* `if Support vectorss dont change when doing leave-one out cross-validation`
* uses a Gram matrix of only support vectors





