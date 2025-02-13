# Support Vector Machines 

Support Vector Machines (SVM) are algorithms used within supervised learning to perform classifications and regression tasks. They are great for handling high-dimensional data and complex noon-linear relationships between features and target variables.

The SVM finds the hyperplane that maximally separates different classes or fits the data regression.

The Margin is the distance between the hyperplane and the nearest data points of each class.

Support Vectors are data points that are nearest to the hyperplane and are critical for determining the hyperplane and margin. 

The SVM are used to find a decision boundary that generalizes new and unknown data. 

When the margin is large, this indicates more separation between classes and reduces the likelihood of misclassification.

#### Linear SVM

A Linear SVM can be used when data is linearly separable. This means that the hyperplane will perfectly separate known classes.

An Optimal Hyperplane maximizes the margin between the closest data points of different classes. This determined margin is known as the Separating Hyperplane. The data points that are closest to this hyperplane are the support vectors.

When the margin is maximized, the classifier is stronger. This means some variability can be tolerated without misclassification of points.

The formula for a hyperplane is shown below:

>w \* x + b = 0

- w is the weight vector and is perpendicular to the hyperplane.
- x is the input feature vector.
- b is the bias term that shifts the hyperplane relative to the origin.

The SVM algorithm is used to find optimized values for w and b during model training.

### Non-Linear SVM

In many cases data is not separable in a linear way. In these cases we will need to use alternative methods for modeling our data and features. This can be achieved by something known as the Kernel Trick.

A Kernel Trick uses kernel functions to map data pints to a higher-dimensional space where they can become linearly separable. The goal is to add an extra dimension (like from 2D to 3D) to divide data points when the 2D plane is not a good option.

#### Kernel Functions

Commonly used kernel functions for achieving non-linear SVMs include:

- Polynomial Kernel - uses polynomial terms to capture non-linear relationships between feastures. This can be thought of as implementing a curved decision boundary.

- Radial Basis Function (RBF) - uses Gaussian functions to map data points to higher-dimensional spaces. This is a popular method capable of capturing non-linear patterns.

- Sigmoid Kernel - similar to the sigmoid function for logistic regression, it maps data points too a space with a sigmoid shaped decision boundary.

The formula for finding the optimal hyperplane for kernel functions is below:

>Minimize: 1/2 ||w||^2
>Subject to: yi (w \* xi + b) >= 1 for all i

- w is the weight vector that defines the hyperplane
- xi is the feature vector for data point i
- yi is the class label for data point i (-1 or 1)
- b is a bias term

#### Assumptions

There are few assumptions that need to be made when using SVM:

- No Distributional Assumptions - no strong assumptions about the distribution need to be made.
- High Dimensionality - useful when the number oof features is larger than the number of data points.
- Robust to Outliers - focuses on maximizing the margin instead of plotting points perfectly.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Support Vector Machines](https://academy.hackthebox.com/module/290/section/3253 "HTB Support Vector Machines")