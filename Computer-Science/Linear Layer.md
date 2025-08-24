Tags: #cs #math #ml
### Overview
A simple neural network is composed of multiple 'linear layers', each layer carrying out a linear transformation of an input vector using weights and biases.
### Key Concepts
The linear layer is broken down into two parts: **Forward Feed** and **Backpropagation**.
#### Forward Feed
When feeding forward, we multiply our weight matrix with an input vector to produce an output.
The feed forward needs to do three things
1. Accept an input vector
2. Multiply the input vector with our weight matrix
3. Output the product vector
Then it needs to store the input and output vector for backpropagation.
#### Backpropagation
Backpropagation changes the weights in our network to minimize the error between our network's output and the expected output.

We minimize our error with a method called gradient descent. Gradient descent involves identifying the direction of the steepest descent for our error function given our current weights. We then want to change the weights such that we move in the given direction to reduce error.

So in order to actually perform backpropagation, we expect our linear layer to receive the partial derivatives of the error with respect to each of the layer's outputs. In turn, we calculate the partial derivatives of the error with respect to each of the layer's inputs.

(ToDo Make Gradient Descent Note).
