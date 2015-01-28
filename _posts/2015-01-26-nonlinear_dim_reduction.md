---
layout: post
title: Nonlinear Dimension Reduction Class Notes
category: Adv. Machine Learning
tags : [Kernel PCA, Local Linear Embedding,class notes]
---


# Nonlinear dimension reduction

## manifold learning & embedding

* transition image by shifting pixels to the right

## multidimensional scaling

* find low dimensional data set that behaves like high dimensional dataset
* _behaves_ : want similar distance between data points
* dissimillairty is a function of two inputs. 
	* 
* _distance metric_ must satisfy triangle inqueality
* _divergance_ is similar but does not caputre symmetry property
* standard example is euclidean l2 distance = 1/2 * (x1-x2)**2
* for N object we can computer a dissimilarity matrix with tellus how far apart the points are
* want to find a new dataset why whose distance matrix is similar to the distance matrix of the original dataset X

### Example
* have coordinates in 3d. Embed this data into a 2d dataset

## Locally linear embedding (LLE)

* preserve the k nearest neighbor distances
* represent each point as a linear combination of its neighbors'' locations (W vectors)
* for 2d: can re-construct dataset with 3 neighbors (as long as they are not on a line)
* weights must be between 0 and 1 to maintain a convex objective function

* new y dataset has zero mean and identity covariance matrix
* need to enforce low dimensionality - otherwise we can simply set y=x and acheive zero error
* Findings W''s (convex combination of weights on neighbors)
	* 

### Solving for optimal w
* C(w/lambda) = 1 
	* Can solve this linear system with 'the backslash operator'

### Run time
Runs in O( (n*k) **3)
Where k is the number of neighbors

### Finding the Y matrix
* delta = 0 unless i=j
* To min objective function, set Y as the bottom d+1 eigenvectors of M
	* We specify that the new dataset is d dimensions
* M is positive definite & square
	* M = V*lambda*transpose(V)
	* = trace(V*lambda*trasnpose(V)*V*transpose(V)
	* = trace (tranpose(V)*V*lambda*tranpose(V)*V)
	* = trace ( I * lambda * I )
	* = sum of lambda i
* finding eigenvalues takes O(n^3)

## Kernal PCA
* Recall, PCA approximates using eigenvectors, mean, and coefficients
* For example, C = 1/n * sum*x*xt  =>  eigen values and eigen vactors satsify lambda * v = C * v
	* or an NxN Gram matrix: Kij = xit*xj (dot product kernel)
* Fo nonlinearity do PCA on feature expansions: phi
* phi must statisfy Mercer''s theorem  
* Assume data is zero-mean (bc we can''t compute the mean in these high dimensions O(d^2) or O(d^3)

### Efficiently find eigen vectors of C
* Eigenvectors are in the sapn of th efeature vectors: v = sum(alphai * phi(xi))
	* if we move beyond the span of the data, the covariance is 0

### Centering Kernel PCA
* take original kernel, subtract column avg, subtract row avg, add matrix avg





