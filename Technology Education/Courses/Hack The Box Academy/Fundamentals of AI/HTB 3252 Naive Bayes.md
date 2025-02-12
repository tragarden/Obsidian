# Naive Bayes

Naive Bayes is an algorithm that uses probability to classify tasks based on the Bayes theorem.

The Bayes' Theorem is used to describe the probability of an event based on prior knowledge and observed evidence. It is often used for spam filtering and offers great performance in real-world scenarios.

The formula for Naive Bayes is below:

>P(A|B) = \[P(B/A) \* P(A)] / P(B)

- P(A|B) is the likelihood of event A happening after B has happened.
- P(B|A) is the likelihood of B happening after A has happened.
- P(A) is the prior probability of A happening.
- P(B) is the prior probability of B happening.

Naive Bayes in the context of machine learning is a classifier that leverages Bayes' theorem to predict the probability of a data point belonging to a class based on it's features.

The 'Naive' part of the name refers to an assumption of conditional independence. This means assuming the presence or absence of one feature will not affect the presence or absence of any other feature if the class label is known.

This works in the following way:

- Calculate Prior Probabilities - find the probability of each class and the probability of the data points belonging to that class based on it's known features.
- Calculate Likelihoods - determines the probability of seeing particular feature values when the data point belongs to a known class.
- Apply Bayes' Theorem - combines the prior probabilities using Bayes' theorem to calculate the posterior probability of the data point belonging to each class. 
	- Posterior Probability is the updated probability of an event after assessing new information - it is a revised belief about a class label after observing new information.
- Predict the Class - assign the data point to a class with the highest posterior probability.

#### Classifier Types

There are three types of Naive Bayes distributions:

- Gaussian Naive Bayes - used when features are continuous and assumed to follow a bell curve aka Gaussian Distribution. This can be used with data that is normally distributed.
- Multinomial Naive Bayes - suitable for discrete features and used with text classifications. 
- Bernoulli Naive Bayes - used for binary features where the feature is either present or absent. An example is whether or not a specific word is found within a given text.

#### Assumptions

Naive Bayes is easily implemented and resistant to influences, but some assumptions should be made:

- Feature Independence - features are conditionally independent given the class.
- Data Distribution - choosing Gaussian, Multinomial, or Bernoulli is dependent on the assumed distribution of features.
- Sufficient Training Data - you must have sufficient data for accurately estimating probabilities.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Naive Bayes](https://academy.hackthebox.com/module/290/section/3252 "HTB Naive Bayes")