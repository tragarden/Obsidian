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

The formula for Informatin Gain is below:

>Infoormation Gain(S, A) = Entropy(S)  -  ((|Σ