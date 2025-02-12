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

