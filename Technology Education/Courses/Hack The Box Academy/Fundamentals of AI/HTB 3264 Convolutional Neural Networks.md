# Convolutional Neural Networks

A Convolutional Neural Network (CNN) are intended to process grid-like data like images. They capture spatial hierarchies of features which is fundamental for image recognition, object detection, and image segmentation.

In most cases, CNNs have three layers:

- Convolutional - the core layers that perform convolutions on the input data via learnable filters. The filter computes the dot product of filter weights and input values. This is used to extract features like edges, corners, and textures. The output of this layer is a feature map that highlights the presence of learned features. Different filters detect different features.
- Pooling - layers that reduce dimensionality of feature maps to make the network less computationally expensive and reduce the susceptibility for overfitting. Max Pooling and Average Pooling are commonly implemented.
- Fully Connected - similar to the layers used in MLP, they connect every neuron in one layer to every neuron in the following layer. This is used as one of the final processes for determining high-level reasoning and predictions based on the extracted features.

During the learning process for detecting edges, corners, or textures, the filter weights are adjusted and refined to become detectors for complex visual elements.

This is a hierarchical process as described below:

- 