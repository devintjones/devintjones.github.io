---
layout: post
title: Truncated Gaussian Detection
category: Adv. Machine Learning
tags : [Gaussian Facial Recognition,class notes]
---


## approximate sigma matrix with pca plus spherical term

* need to compute inverse and determinate
* -> 
* only keep eigenvalues up to some M. set the rest to rho
* approximate msigma: subtracted rho from eigvin vals, use rho*I to approxmate the rest
* only need to store diagonal cov matrix instead of storing whole matrix
* to invert diaginal matrix, only need to invert elementwise

* a good choice for rho is the average of eigenvalues that are not used

This was the bets facial recognition algo up to 10 years ago

## Gaussian face recognition

* measure the diffrenct between two faces - is this an acceptable difference to the be the same person?
* difference between pictures is called delta
* maximimze the log likelihood function to find best mu and sigma of each photo. 
* Bayes optimal decsion is the choice that maximizes the bayesian posterior
* will product a nonlinear (quadratic) classification boundary if covariances are different
	* can product eliptical or hyperboloic decision boundary (not hyperbolic)
* if covariances are equal, decision boundaries will be linear

## Intra-extra personal guassians

* Intra persaonl images will vary things like eyebrows and facial expressoins
* Extra personal will vary things like nose width (things that can't be easily changed for a person over multiple pictures)


