# Decision Trees

Decision Trees are algorithms used within supervised learning to facilitate classification and regression tasks. They predict the value of target variables by learning decision rules inferred from processed data.

Decision Trees have three main parts:

- Root Nodes - the starting point of the tree containing the entire dataset.
- Internal Nodes - features or attributes of the data where each node branches into two or more child nodes based on decision rules.
- Leaf Nodes - the terminal nodes of the tree that represent the final outcome or prediction.

#### Gini Impurity

Gini Impurity measures the probability of misclassifying a randomly chosen element from a set. Lower values indicate a more pure set.

The Gini Impurity function is shown below:

>Gini(S) = 1 - Σ (pi)^2

- S is the dataset
- pi is the proportion of elements that belong to class i within the set.

Example:

- If dataset S contains two classes A and B and there are 30 instances of class A and 20 instances of class B:

>pA = 30 / (30 + 20) = 0.6

>pB = 20 / (30 + 20) = 0.4

The Gini Impurity expression for this data set is:

>Gini(S) = 1 - (0.6^2 + 0.4^2) 
>= 1 - (0.36 + 0.16) 
>= 1 - 0.52 = 0.48

#### Entropy

Entropy is a means of measurement for disorder or uncertainty within a data set. Lower entropy represents a more homogenous set.

The formula for entropy is below:

>Entropy(S) = - Σ pi \* log2(pi)

- S is the dataset
- pi is t he proportion of elements belonging to class i in the set

Using the values from the previous example we can also calculate the entropy:

>Entropy(S) = - (0.6 \* log2(0.6) + 0.4 \* log2(0.4))
>= - (0.6 \* (-0.73697) + 0.4 \* (-1.32193))
>= - (-0.442182 - 0.528772)

#### Information Gain 

Information Gain is used to measure the reduction in entropy achieved by dividing a set based on a feature. The feature that provides the highest amount of information is used for the split. 

The formula for Information Gain is below:

>Information Gain(S, A) = Entropy(S)  - Σ ( (|Sv| / |S|) \* Entropy(Sv) )

- S is the dataset
- A is the feature used for splitting
- Sv is the subset of S for which feature A has value v

If we consider a dataset with 50 instances and two classes A and B with a feature F that can take two values of either 1 or 2:

- F = 1: 30 instances, 20 class A, 10 class B
- F =2: 20 instances, 10 class A, 10 class B

The calculation for our example data set is below:

>Entropy(S) = - (30/50 \* log2(30/50) + 20/50 \* log2(20/50))
>= - (0.6 \* log2(0.6) + 0.4 \* log2(0.4))
>= - (0.6 \* (-0.73697) + 0.4 \f* (-1.32193))
>= 0.970954

Now we will calculate the entropy for each subset of Sv:

- F = 1:
	- pA = 20/30 = 0.6667
	- pB = 10/30 = 0.3333
	- Entropy(S1) = - (0.6667 \* log2(0.6667) + 0.3333 \* log2(0.3333)) = 0.9183

- F = 2:
	- pA = 10/20 = 0.5
	- pB = 10/20 = 0.5
	- Entropy(S2) = - (0.5 \* log2(0.5) + 0.5 \* log2(0.5))

The formula below is for weighted entropy:

>(|S1| / |S|) \* Entropy(S1) + (|S2| / |S|) \* Entropy(S2)
>= (30/50) \* 0.9183 + (20/50) \* 1.0
>= 0.55098 + 0.4
>= 0.95098

Lastly we can calculate the information gain:

>Information Gain(S, F) = Entropy(S) - Weighted Entropy
>= 0.970954 - 0.95098
>= 0.019974

### Building a Decision Tree

The root node or initial node of the tree is selected and the splits are determined based on elements such as the Gini Impurity, Entropy, or Information Gain. This feature becomes the internal node and branches are created for each possible value or range oof values related to that feature.

These determined branches further determine the next branches via recursive processes. This continues to occur until the tree satisfies any of the following conditions:

- Maximum Depth - a maximum depth has been specified to prevent the tree from becoming overly complex or overfitting the  data.
- Minimum Data Points - the number of data points within a node fall below a specified threshold ensuring that splits are meaningful and not based on small subsets.
- Pure Nodes - all the data points within a node fall within the same classification indicating that more splits will not improve the purity of the subset.

#### Assumptions

An advantage to data trees is that they do not have many assumptions associated with their use:

- No Linearity Assumption - relationships can be non-linear between features and  target variables making theses trees more flexible than other methods.
- No Normality Assumption - a normal distribution is not required.
- Outlier Handling - these models are resistant to the influence of outliers since the data is partitioned based on feature values instead of distance-based calculations