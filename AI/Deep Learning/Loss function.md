The loss of a neural network quantifies the error between the predicted output and the true expected value.  
It measures how well the model is performing on a given example. This value is used to guide the update of the model’s parameters (weights and biases) during training, with the goal of minimizing the prediction error.
- **EMPIRICAL LOSS:** A general loss function computed during the training phase that measures the total error over the entire training dataset. It is used to evaluate how well the model fits the observed data.
$$
J(W,b)=\frac{1}{m} * \sum_{i=0}^m L(\hat{y}^i,y^i)
$$
- **BINARY CROSS ENTROPY LOSS:** used in binary classification problems in which the output is a probability going from 0 to 1
$$
J(W,b)=-\frac{1}{m} * \sum_{i=0}^m y^i * log(h_{W,b}(x^i))-(1-y^i)*log(1-h_{W,b}(x^i))
$$
- **MEAN SQUARED ERROR LOSS:** used with regression tasks in which the output is a continuous value
$$
J(W,b)=\frac{1}{m} * \sum_{i=0}^m (h_{W,b}(x^i)-y^i)^2
$$
