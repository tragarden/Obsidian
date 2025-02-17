# Convolutional Neural Networks

A Convolutional Neural Network (CNN) are intended to process grid-like data like images. They capture spatial hierarchies of features which is fundamental for image recognition, object detection, and image segmentation.

In most cases, CNNs have three layers:

- Convolutional - the core layers that perform convolutions on the input data via learnable filters. The filter computes the dot product of filter weights and input values. This is used to extract features like edges, corners, and textures. The output of this layer is a feature map that highlights the presence of learned features. Different filters detect different features.
- Pooling - layers that reduce dimensionality of feature maps to make the network less computationally expensive and reduce the susceptibility for overfitting. Max Pooling and Average Pooling are commonly implemented.
- Fully Connected - similar to the layers used in MLP, they connect every neuron in one layer to every neuron in the following layer. This is used as one of the final processes for determining high-level reasoning and predictions based on the extracted features.

During the learning process for detecting edges, corners, or textures, the filter weights are adjusted and refined to become detectors for complex visual elements.

This is a hierarchical process as described below:

- Initial - layers that learn simple features like edges, blobs, and vertical or horizontal edges.
- Intermediate - all previous layers combine basic features for complex patterns.
- Deeper - layers that learn high-level features like shapes and object parts like wheels, windows, or cars.

What this ultimately means is that even in the case of a simple symbol like a handwritten version of the number 7, the outer edges, angles, changes in direction, and even the internal parts of the '7' figure are assessed by evaluating the feature maps. Many features are evaluated and observed by the agent to determine if the 7 matches the case for what the agent recognizes as a 7.

#### Assumptions

There are many assumptions that must be made when using CNNs. While these tools are powerful, they are much less effective when they do not meet the following assumed criteria:

##### Grid-Like Structure

CNNs are designed to work with data that is organized in grid patterns. Images are 2-D grids and videos are represented as 3-D grids because a dimensionality of time is considered.

##### Spatial Hierarchy of Features

Features within the data must be organized in a hierarchical fashion. Lower-level features like corners, edges, and textures are localized and represented in early layers. Higher-level features are less obvious and are built upon the lower level features. This allows for identification of more complex shapes, patterns, or objects.

##### Feature Locality 

This means that in images, neighboring pixels are more likely to be correlated and have meaningful patterns than more distant pixels. The convolutional filters focus on small local regions of input to capture local dependencies specific to that area.

##### Feature Stationarity

Stationarity implies that the meaning or significance of a feature is consistent regardless of it's position within the data. Features like vertical edges will always be recognized as the same feature no matter it's position within the image. This is accomplished through height sharing within the convolutional layers.

##### Sufficient Data 

CNNs require large, labeled data sets in order to learn complex patterns to make generalizations about unknown data. When there is not enough data, overfitting can occur where the model trains well on existing data but is poor at making predictions about new data.

##### Normalization

Input must be normalized to a standard range to ensure stable and efficient training by preventing large variations in input values from causing disruptions.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Convolutional Neural Networks](https://academy.hackthebox.com/module/290/section/3264 "HTB Convolutional Neural Networks")