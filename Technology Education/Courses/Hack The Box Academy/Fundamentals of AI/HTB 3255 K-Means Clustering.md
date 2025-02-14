# K-Means Clustering

K-Means Clustering is an unsupervised learning algorithm that partitions datasets into k amount of non-overlapping clusters. it groups data points into distinct segments based on likeness. 

K-Means is an iterative algorithm that minimized the variance within each cluster. It places the points as close to similar data points as possible while keeping the clusters remote from eachother.

There are four steps this algorithm follows:

1. Initialization - randomly selects k number of data points to determine the initial cluster centers, known as centroids. A Centroid represents the average point of each cluster.
2. Assignment - assigning points to clusters based on distance metrics like Euclidean Distances.
3. Update - take the mean of all data points in the cluster to determine the centroid when new poiints are added.
4. Iteration - repeat prior steps until very little changes in the clusters is observed. When they are no longer experiencing noticable changes, the clusters are stable.

#### Euclidian Distance

A Euclidean Distance measures the similarity between data points by finding the straight line distance between two points in space. 

The formula for Euclidean Distance is shown below:

>d (x, y) = sqrt( Σ (xi - yi) ^2 )

- xi and yi are the i-th features for data points x and y.

#### Determining K

When K is determined, this can be thought of as determining the number of clusters. Too few clusters results in broad groupings while too many clusters can produce results that are too granular. 

The Elbow Method is a visual way of estimating the optimal number K by graphing the outcomes.

There are four steps to the elbow method:

1. Run K-Means for a range of values - start with value 1 and increase in increments.
2. Calculate WCSS - measure the total variance of each cluster via WCSS. Lower values indicate more similar points within clusters.
3. Plot WCSS vs K - plot these features graphically.
4. Identify the Elbow Point - Where the 'elbow' forms in the graph, this is where WCSS decreasing slows which indicates a balance between variance and granularity. 

 Silhouette Analysis means measuring how similar a data point is to the peers within it's assigned cluster.
 
There fore four steps for Silhouette Analysis:

1. Run K-means for a range of values - perform k-means clustering for different K values.
2. Calculate Silhouette Scores - These scores range from -1 to 1 with the following conditions:
	1. 1 indicates a good match to the cluster and bad match to other clusters.
	2. 0 indicates a point that could belong to either of two clusters.
	3. -1 indicates incorrect cluster assignment.

3. Calculate Average Silhouette Score 
4. Choose the K with the highest score

When making decisions for K values - remember that sometimes situations and practicality will dictate different results than pure calculations can.

Consider:

- Computational Cost - higher K values require more access to hardware resources.
- Interpretability - clusters should be easy to interpret and display meaningful visual information.

#### Assumptions

We should assume the following when using K-means clustering:

- Cluster Shape - clusters should be circular or spherical with similar sizes. Complex shapes and various sizes may not perform well.
- Feature Scale - Large features have greater influence on the resulting clusters. They should therefore be standardized or normalized. 
- Outliers - points that deviate significantly distort cluster centers.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB K-Means Clustering](https://academy.hackthebox.com/module/290/section/3255 "HTB K-Means Clustering")