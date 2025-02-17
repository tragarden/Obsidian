# Deep Learning

Deep Learning is a field of machine learning that uses neural networks utilizing multiple layers to analyze complex patterns.

Neural Networks used for Deep Learning are modeled on the human brain. Due to this, these systems are able to automatically learn features from raw data without manual interventions. The agent is then able to learn hierarchical representations of data to evaluate increasingly complex information.

Deep Learning is most often used in the fields of natural language processing, computer vision, and robotics.

#### Artificial Neural Networks

Artificial Neural Networks (ANN) are developed via neural networks that are based on biological animal brains. Within ANN, interconnected nodes known as neurons are organized in layers with corresponding strengths known as weights.

The weights are adjusted based on input data so that predictions and decisions can be made.

##### Layers

The layered structure of the neural networks have three types of layers:

- Input - receives initial data.
- Hidden - computations are performed to extract features from the input data. There are multiple hidden layers.
- Output - the final output in the form of predictions or classifications.

##### Activation Functions

Activation Functions introduce non-linear functionality to the network which facilitate the learning of complex patterns. These functions determine when and if neurons should be activated. 

The most common activation functions include:

- Sigmoid - scales input btween 0 and 1. 
- Rectified Linear Unit (ReLU) - 0 for negative inputs and returns the input value for positive inputs.
- Hyperbolic Tangent (Tanh) - scales input between -1 and 1.
- Backpropagation - calculates the gradient of the loss function related to weights before updating the weights in a direction that will minimize losses. This is an iterative process.
- Loss Function - measures errors between network predictions and target values. The goal of agent training is to minimize this loss function. Different tasks require different loss functions. Mean Square Error and Cross-Entropy Loss are examples of this.
- Optimizer - determines updates for weights during training by using gradients calculated during the backpropagation process. This is to minimize loss. Some popular optimizers include:
	- Stochastic Gradient Descent (SGD)
	- Adam
	- RMSprop
- Hyperparameters - determined before training as a way to control learning processes. These include the learning rate, number of hidden layers, and number of neurons per layer.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Deep Learning](https://academy.hackthebox.com/module/290/section/3261 "HTB Deep Learning")