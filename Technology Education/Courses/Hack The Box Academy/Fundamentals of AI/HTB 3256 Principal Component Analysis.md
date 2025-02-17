# Principal Component Analysis

Principal Component Analysis (PCA) is a method for reducing dimensions to transform high-dimensional data into lower level representations while retaining the integrity of the data. 

It identifies principal components and new variables that are linear combinations of the originals in order to capture maximum variance. This is commonly used in feature extraction, data visualization, and noise reduction. 

In laymen terms, this can be thought of as recognizing and capturing the key components and features to provide directions for the data. PCA will capture the lines that best represent the data.

##### Key Concepts

The main components of PCA include Variance, Covariance, Eigenvectors, and Eigenvalues.

- Variance is the spread or dispersion of points around the known mean. PCA aims to find maximum variance to capture the most significant data.
- Covariance is the measure of relationship between two variables to identify the directions of maximum variance.
- Eigenvectors and Eigenvalues 
	- Eigenvectors represent the directions of the principal components.
	- Eigenvalues represent the amount of variance for principal components.

The PCA algorithm has six steps in it's process:

1. Standardization - subtracting the man and dividing by the standard deviation for all features to ensure they have the same scale.
2. Covariance Matrix - represents the relationships between the features.
3. Eigenvectors and Eigenvalues - determine these values from the covariance matrix.
4. Sort the Eigenvectors and Eigenvalues - in descending order of corresponding eigenvalues to capture the most variance.
5. Select Principal Components - choose the top K eigenvectors where K is the desired number of dimensions in the new representation.
6. Transform - project the original data onto the lower-dimensional representation.

An Eigenvector is a unique vector that maintains direction during linear transformations.

The formula for finding Eigenvectors is:

>A \* V = λ \* V

- λ represents the Eigenvector as an Eigenvalue  
- V represents the Eigenvector
- A represents the covariance matrix or the relationships between features.

##### Solution Methods

Eigenvalue Decomposition is when the Eigenvalues and Eigenvectors are directly calculated.

Singular Value Decomposition (SVD) is more stable as it decomposes the data matrix into singular vectors and values.

##### Selecting Components

This decision leans in either the direction of dimensionality reduction or information preservation.

#### Assumptions

We must make the following assumptions when using PCA:

- Linearity - all relationships between features are linear.
- Correlation - there should be strong correlation between features.
- Scale - the data must be standardized to have the same scaling.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Principal Component Analysis](https://academy.hackthebox.com/module/290/section/3256 "HTB Principal Component Analysis")