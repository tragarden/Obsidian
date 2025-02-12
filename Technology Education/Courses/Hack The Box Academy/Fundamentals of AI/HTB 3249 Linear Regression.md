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

You can think of OLS as the line that minimizes the total area of the squares formed between the data points and the regression line.

There is a specific process for determining the OLS values:

1. Calculate Residuals - the residual is the difference between the actual value and the predicted values.
2. Square the Residuals - this ensures all values are positive and are used to illustrate large errors.
3. Sum the Squared Residuals - this represents the model's overall error and is called the Residual Sum of Squares (RSS).
4. Minimize the Sum of Squared Residuals - adjusts the coefficients to find the values that will return the smallest possible RSS.

#### Assumptions

In order to use linear regressions we need to make certain assumptions:

- Linearity - a linear relationship exists between predictor and  target variables.
- Independence - observations within the dataset are independent of each other.
- Homoscedasticity - variance of the errors remains constant across all levels of predictor variables. Thusly the spread of residuals is roughly the same across the full range of predicted values.
- Normality - errors are normally distributed to ensure that valid inferences are made about the coefficients used by the model.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Linear Regression](https://academy.hackthebox.com/module/290/section/3249 "HTB Linear Regression")