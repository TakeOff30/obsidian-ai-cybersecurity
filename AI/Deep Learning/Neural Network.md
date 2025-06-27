A neural network is a parametrized function $f:R^n\rightarrow R^m$ that represents a mapping form an input vector $x\in R^n$  to an output vector $y\in R^m$, the mapping is composed of multiple layers each defined as: 
$f^{(l)} (z)=g(W^{(l)} * x + b^l)$ 
where
	$z$ is the input sample
	$W^{(l)}$ is the weight matrix for the layer $l$
	$b^l$ is the bias term
	$g$ is the [[Activation function]] 

**HYPERPARAMETERS**: are parameters set before the training that describe the neural network:
- Learning rate: $\alpha$
- Number of epochs.
- Size of the BATCH: need to be experimented in order to find the correct one
- Number of hidden layers (depth of the network)
- Number of units for each layer (width of the network)
- Activation functions.

The hypothesis denoted as $h_{W,b}(x)$ is the final output of the network after applying all the layers on input $x$.

To find the optimal weights and biases that allow us to obtain the lowest possible value for the [[Loss function]]. The training alternates between:
- **FORWARD STEP**: in which the samples are fed into the network and the value of the loss function is computed.
- **BACKPROPAGATION**: in which we exploit the chain rule of derivatives and compute the gradient descent on the loss function obtaining the updated value of the parameters.