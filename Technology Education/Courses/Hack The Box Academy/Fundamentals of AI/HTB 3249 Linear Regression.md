# Linear Regression

A Linear Regression is the fundamental model for supervised learning as it predicts a continuous target variable that the algorithm uses to make predications. This method identifies outliers and finds the common trend in the data.

A Regression in the context of machine learning is a type of supervised learning with the intention of predicting a continuous target variable that falls within an expected range of outcomes. These predictions are used to categorize new input data.

The distinguishing feature of regressions is that they generate categorical labels for new input.

##### SLR

A Simple Linear Regression involves a predictor variable and one target variable. 

In the following expression:

>y = mx + b:

- y is the predicted target variable
- x is the predictor variable
- m is the slope of the line that represents the relationship between two variables
- b is the y-intercept 

In the context of machine learning this algorithm finds the optimized values for m and b that minimize the error between predicted values y and actual values y derived from known data.

##### MLR

A Multiple Linear Regression is when multiple predictor variables are involved in the linear equation y = mx + b as shown below:

>y = b0 + b1x1 + b2x2 + .... + bnxn

- y is the predicted target variable
- x1, x2, ...., xn are the predictor variables
- b0 is the y-intercept
- b1, b2, ..., bn are coefficients representing the relationship between the predictor variables and the target variables.

##### OLS

Ordinary Least Squares (OLS) are used as a method for estimating optimal values for the coefficients within the linear regression. It is used to minimize the sum of squared differences between actual values and the predicted values.

There is a specific process for determining the OLS values:

1. 