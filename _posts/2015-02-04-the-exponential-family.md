---
layout: post
title: Maximum Entropy Models
category: Adv. Machine Learning
tags : [maximum entropy models, exponential family,class notes]
---


# Maxiumum Entropy Models

##The Exponential Family

Family of distributions where model and data interact via a dot product

Has a natural paramter form that I need to write in latex

### Conjugate priors of Exponential family
* Gaussian mean -> Gaussian mean
* Bernoulli -> Beta
* Multinomial -> dirichlet
* Gaussian Cov >-> inverse Wishart

### Table of E-Families
Gaussian
Multinomial
Exponential
Gamma
Poisson

* but, we can also derive e-family form via Maximum Entropy

## Max Entropy
* Jaynes, Shannon, 1950s-60s
* Based on principles of indifference or insufficient reason
* Looks like this
	* H(p) = -sumx(p(x)*log(p(X)))
* Max entropy wants to spread probability on all x
	* Uniform dist has highist H
* Want to find stats that describe the data that also max entropy/smoothness of distribution

* Can constrain distribution to certain statitics or moments

* Max entropy is equivielnt to min relative entropy, using the uniform dist as a relative comparision
	* this is because the uniform distribution has the largest entropy of any distribution

* All exponential family distributions are max entropy


