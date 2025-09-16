# Covariance-matrix-estimation

The aim of that research is finding the way of estimating assets covariation
The question of estimating the covariance matrix arises for the following reason:
sometimes we need to now covariance between assets for efficient portfolio rebalancing or other goals,
but some covariance coefficients can be distorted if the length of data sample (N) is comparable to the number of assets (T).

Why? Because covariance matrix has about 0.5 * (N-1) * N params (where N is the number of assets).
If the N/T ratio is near to 1 or even 0.01, we will use number of the observations comparable to the number of params that we estimate.
That can lead to inadequate results. And in that step we need use some methods for matrix covariance matrix shrinkage.

Shrinkage is a synonym to the compression. We make the biggest covariance matrix eigenvalues less bigger, and the smallest more bigger
Eigenvalues correction will lead to the eigenvectors correction and will make ratios between them more balanced
There are a lot of ways to do that, and in this notebook you will learn about 3 different types of shrinkage,
compared to the base covariance matrix without any shrinkage. The inspiration and the math behiind them can be taken out of this article:
https://www.zora.uzh.ch/id/eprint/170824/1/econwp231.pdf

In that notebook we will compare shrinkage methods in terms of proxy-volatility of portfolio at the each moment of testing
You can add returns prediction and use predicted covariance matrices and predicted returns for portfolio optimization,
that approach can be very powerfull.
