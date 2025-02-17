# Neural Networks

Neural Networks, or Multi-Layer Perceptrons (MLP) are used to overcome the limitations of individual or singularly layered perceptrons. 

These networks are composed of three layers:

- Input
- Hidden 
- Output

Neurons are fundamental computational units that receive inputs, process them in association with their related weights and biases, then applies them to activation functions for the production of output. Neurons can use sigmoid, ReLU, and tanh functions. This allows the neurons to handle non-linear relationships to produce continuous output.

Hidden Layers are between the input and output layers and are used to extract features from the data. The neurons in the hidden layers perform the following series of tasks:

1. Receives input from all neurons in the previous layer.
2. Performs weighted sum of all inputs.
3. Adds biases to weighted sums.
4. Applies the activation function.

This output is then passed to the neurons of the next layer for further processing. 

The output layer produces the final outcome and is dependent on specific tasks.

A Binary classification task would have one output neuron.

A multi-class classification would have one neuron for each class.

Multi-Layer Perceptrons (MLP) circumvent the limitations of single-layer perceptrons by learning non-linear boundaries. This allows these networks to evaluate complex functions and observe patterns that are not linearly separable.

While single-layer perceptrons are unable to solve XOR functions, multi-layer perceptrons are able to solve the XOR function.

All MLPs are trained using backpropagation and gradient descent to adjust network weights and biases to normalize the errors.

A simple review of backpropagation is below:

1. Forward Pass - data is fed into the neural network to calculate output.
2. Calculate Error - loss functions calculate differences between predictions and target values.
3. Backward Pass - error signal is propagated through the network and for each layer, the weights and biases are calculated using the calculus chain rule.
4. Update Weights and Biases - updates are performed to reduce errors, often done via optimization algorithms like gradient descent.

Gradient Descent is an iterative optimization algorithm to find the minimum of a function. This is used to minimize the loss function. This is accomplished by taking steps toward the negative gradient of the loss function. Step size is determined by learning rate.

A simple review of gradient descent is below:

1. Initialize - random values are assigned for weights and biases.
2. Calculate Gradient - backpropagation is used to calculate gradient of the loss function.
3. Update - weights and biases are updated by subtracting the fraction of the gradient from the currently defined weights and bias