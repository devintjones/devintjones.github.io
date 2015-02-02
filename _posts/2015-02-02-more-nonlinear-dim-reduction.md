---
layout: post
title: Nonlinear Dimension Reduction Class Notes
category: Adv. Machine Learning
tags : [Kernel PCA, Local Linear Embedding,class notes]
---


# Nonlinear dimension reduction

Kernel PCA & Local Linear Embedding both do not provide methods of reconstruction to original dimensions (one way mapping)

## Semidefinite Embedding
AKA Max variance unfolding
Similar to LLE and kernel PCA
Maintains only distance in neighborhood
Stretch data to a 2d space while maintaining the distances
Then apply PCA (or kPCA, but PCA should be fine in most cases)

## PCA and Kernel PCA
* Get matrix A of affinities betwen pairs Aij=K(xi,xj) : this could be the inner product between all rows
* SVD A & view top projections

## Semidefinite Embedding
* Get k nNN graph of data
* Get matrix A
* Use max trace SDP to stretch graph A into PD graph K
* SVD K & view top projections

## More SDE detail
* SDE unfolds knn ocnnected graph C but preserves pairwise distances with Cij = 1
* Reminder- Positive Semidefinite means:
	* all eigenvalues are non-zero
	* symmetrix matrix
* If the matrix is not positive semidefinite, it will not product a Gram matrix
* Trace: sum of eigenvalues which is  = to the sum of the diagonals
* Want to max(tr(K)) so as to max variance of resulting flattened data


## SDE optimization with YALMIP
Optimaztion heirarchy:
* Linear programming
	* quadratic programming
		* quadraticall constrained quadratic programming
			* semidefinite programming
				* convex programming
					* polynomical time algorithms

## SDE Results
3D dataset will have 3 high eigenvals.
After SDE, the 3rd eigenvalue will be near zero
SDE improves 2D visualization (in most cases)
Gets more use/energy out of tip eigenvetors than PCA on original data

If dataset is not connected well, SDE could stretch eigenvals to more dimensions (this would be counter productive)

# Minimum Volume Embedding
* Different appraoch to account for multi-dimension stretching exaggeration by SDE
* Constrain problem to drive variability into the first two lambdas
* Max fidelity F(K) or % energy in top dims
* Equivalent to maximizing L1 + L2 - B*sum(Li) for some B


## MVE optimization: Spectral SDP
* Spectral fuction : f(L1,L2,...,Ld) eginevalues of matrix K
* SDP packages use restricted cost fucntions of hull kappa
* If alphas ordered, it is a linear spectral SDP
* For max over K use SDP. For max over U use SVD. Iterate to obtain monotonic improvement


