# Logistic Regression

A Logistic Regression is another facet of supervised learning that is used to classify new data and is ironically not used for modeling regression. It predicts categorical target variables that have two possible outcomes - these are represented as binary values in binary classification.

A Classification in the context of machine learning is a type of supervised learning that assigns data points to specific categories or classes. Note that these differ from linear regressions in that they create a discrete label instead of predicting continuous values.

These regressions are used for things like:

- Identifying fraudulent transactions.
- Classifying images.
- Diagnosing diseases based on symptoms.

Logistic Regression renders it's output as a probability score with a range of 0 to 1 where 1 is a strong positive indicator that the data point belongs to a known class.

#### Sigmoid Function

A Sigmoid Function is often employed as a probability function that maps any input value within the range of 0 to 1. This is a non-linear function that can observe and display complex relationships between features and outcome probability.

The graph of the sigmoid function appears as an S shape between two limits in the x-direction. It transforms the linear combination of inputs into a probability score that represents the likelihood that input belongs to a positive class.

The Sigmoid expression is below:

>P(x) = 1 / (1 + e^-z)

- P(x) is the predicted probability.
- e is the base of the natural logarithm
- z is the linear combination oof input features and their weights.

A Decision Boundary is a line between two classes of data points that is determined by learned parameters and a chosen threshold for probability.

A Hyperplane is a subspace with a dimension that is one less than that of the ambient space and is used to visualize decision boundaries in higher dimensions. 
- In two-dimensional space the hyperplane is a line that divides the space into two distinct regions.
- In three-dimensional space the hyperplane is a plane that divides the space into two distinct regions.

Threshold Probability can be adjusted between true and false positives but is usually assigned to the value 0.5. 
- If a data point falls above the threshold, it is considered a positive class.
- If P(x) falls below the threshold, it is considered a negative class.

#### Assumptions

- Binary Outcome - variable must be categorical with only two outcomes.
- Linearity of Log Odds - a linear relationship between the predictor variables and the log-odds of the outcomes must exist.
	- Log Odds are a transformation of probability that represent the logarithm of the odds ratio.
- Little to No Multicollinearity - there should be very little to no multicollinearity between predictor variables.
	- Multilinearity occurs when predictor variables are highly correlated which makes it difficult to determine how they effect the outcome.
- Large Sample Size - performs better with a larger dataset allowing for more reliable parameter estimation. 

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Logistic Regression](https://academy.hackthebox.com/module/290/section/3250 "HTB Logistic Regression")