# Anomaly Detection

Anomaly Detection, or Outlier Detection, is a part of unsupervised learning that identifies points that deviate significantly from the expected or observed behavior of the dataset. These points often indicate critical events like fraud, failure, or emergencies.

Anomalies fall under three categories:

- Point Anomalies - points significantly differing from the rest of the data points.
- Contextual - points that are anomalies within specific contexts but not independently of this context.
- Collective - a group of points that deviate together although the points may not be anomalies when considered independently. An example would be a surge in login attempts that aren't expected.

Techniques for identifying anomalies include:

- Statistical Methods - using math to determine an expected distribution to find points that deviate significantly. Z-scores and boxplots are common methods.
- Clustering-based - grouping similar points together and identifying outliers that do not closely align with existing clusters or are part of small and sparse clusters.
- Machine-Learning - utilizing machine learning algorithms to observe patterns in the data to find points that do not align with theses patterns. Methods include One-Class SVM, Isolation Forests, and Local Outlier Factors (LOF.)

#### One-Class SVM

One-Class SVM is an algorithm for machine learning that finds anomalies by learning the boundaries of normal data and identifying the points that fall outside of this boundary. It can be used to find non-linear relationships via kernel functions.

#### Isolation Forest

An Isolation Forest is an algorithm that randomly partitions data and constructs related isolation trees. This method tests the attributes of the data points and attempts to determine their category. If the algorithm can identify a point by using very few characteristics, the point is likely an outlier.

Isolation Forests recursively partition data until each point is isolated within it's leaf node. Random features are selected at each step and then a random split value is assigned. Anomaly scores are calculated based on path length needed to achieve an isolated state. Shorter path lengths often identify anomalies.

Anomaly scores can be calculated with the following formula:

>score(x) = 2^(-E (h (x)) / c ( n ))

- E(h(x)) is the average path length of data point x within the isolation trees.
- c(n) is the average path length of unsuccessful search in Binary Search Tree (BST) with n nodes.
- n is the number of points.

#### Local Outlier Factor 

Local Outlier Factors (LOF) is an algorithm that is based on density to find outliers by comparing local density of a single point to that of it's neighbors.

The formula for LOF is below:

>LOF(p) = ( Σ lrd(o) / k) / lrd(p))

- lrd(p) is the local reachability density of point p.
- lrd(o) is the local reachability density of point o, one of the k nearest neighbors to p.
- k is the number of nearest neighbors.

