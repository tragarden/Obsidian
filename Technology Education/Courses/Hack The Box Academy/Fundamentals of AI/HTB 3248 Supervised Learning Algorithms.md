# Supervised Learning

Machine Learning is dependent on Supervised Learning to enable it's systems to learn from established and categorized data to make accurate predictions. Data points are associated with known outcomes, almost as if you were taking a multiple choice test with the answers pre-selected.

The algorithm develops a mapping function to predict identifiers for new and unknown data by identifying patterns and relationships between existing labels. This allows the model to use it's known data to generate new general knowledge.

The algorithm looks at the characteristics of a given item in order to learn how to distinguish that item from others. This allows the model to begin making predictions for unknown items in the future.

This model works in two stages:

- Classification - predict and create an accurate categorical label for the item.
- Regression - prediction of continuous values like estimating a price based on size or regional factors.

### Core Concepts

Training Data is the most fundamental element of supervised learning. This means finding relationships between input and output labels to develop more accurate models.

Features are properties that can be measured in order to serve as input for the model so the algorithm can use them to learn and make accurate predictions. Features include:
- Size
- Amount
- Location
- Age

Labels are known outcomes associated with data points within the training set that represent the 'correct' answers for the model to predict.

Models are mathematical representations of relationships between features and labels. You can think of the model as a function that takes input and predicts output.

Training refers to the process of the model ingesting training data to modify it's algorithm to minimize errors. This is done when the model iteratively modifies parameters to improve prediction outcomes.

Prediction is when the model observes a new data point and outputs a prediction about this data point via labeling.

Inference is a broad concept that includes prediction as well as structure and patterns within the data. This means using a trained model for determining insights, estimating parameters, and interpreting relationships between variables.

Evaluation refers to the assessment of model performance to determine it's accuracy and ability to generalize about new data points. Relevant metrics include:
- Accuracy - the ratio of correct predictions compared to incorrect predictions.
- Precision - the ratio of true positive predictions among the total positive predictions.
- Recall - the ratio of true positive predictions among total positive instances.
- F1-Score - the harmonic mean of precision and recall that provides a measure of performance.

Generalization refers to a model's ability to accurately predict outcomes for new data input that has not been observed during training.

Overfitting is when machine learning was too effective and included data related to noise and outliers. This inclusion of extraneous data results in poor generalization.

Underfitting is when the model is not nuanced enough to recognized underlying patterns within a set of data. This results in poor performance during training as well as during generation of new labels for unknown data.

Cross-Validation is a technique that allows us to assess how well a model can generalize within an independent data set. This process divides data into subsets called folds. The model is trained on varying combinations of folds while validating the remaining fold. This method reduces the chance of overfitting and provides reliable estimates of model performance.

Regularization is a technique that prevents overfitting by placing a penalty on loss functions that discourages the model from learning overly complex patterns.
- L1 Regularization is when a penalty equal to the absolute value of the magnitude of coefficients.
- L2 Regularization is when a penalty equal to the square of the magnitude of coefficients is added.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Supervised Learning](https://academy.hackthebox.com/module/290/section/3248 "HTB Supervised Learning")