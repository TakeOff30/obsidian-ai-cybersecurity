A neural network is a parametrized function $f:R^n\rightarrow R^m$ that represents a mapping form an input vector $x\in R^n$  to an output vector $y\in R^m$, the mapping is composed of multiple layers each defined as: 
$f^{(l)} (z)=g(W^{(l)} * x + b^l)$ 
where
	$z$ is the input sample
	$W^{(l)}$ is the weight matrix for the layer $l$
	$b^l$ is the bias term
	$g$ is the [[Activation function]] 
