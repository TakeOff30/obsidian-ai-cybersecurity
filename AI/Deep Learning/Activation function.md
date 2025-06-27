Activation functions introduce non-linearity into the network. **Without them, a neural network, no matter how many layers it has, would collapse into a simple linear model** and it would be incapable of learning complex relationships.

-          **SIGMOID**: maps the input value into a value that ranges between 0 and 1 and is usually used in the **_output layer_** for binary classification and is not suitable for intermediate layers because kills the gradient 
$$
sigmoid(z)=\frac{1}{1+e^{-z}}
$$
-          **TANH**: maps the input in values from -1 to 1 and is not used in intermediate layers (doesn’t help backpropagation, as sigmoid). Typically has better performance than sigmoid:  
$$
tanh(z)=\frac{e^{z}-e^{-z}}{e^{z}+e^{-z}}
$$
-          **RELU**: default activation for many NNs, it is often used in intermediate layers because it is easy to train and is efficient to calculate its derivative  
it is affected by the **_Dying ReLu_** **_problem_** in which some neurons after many derivative calculations and updates the gradient becomes zero and the network does not learn anymore.
$$
ReLu(z) = 
\begin{cases} 
0 & \text{if } z \leq 0 \\
z & \text{if } z > 0 
\end{cases}
$$
-          **LEAKYRELU**: maps values smaller than 0 to negative numbers overcoming the Dying ReLu problem  
 The value less than 0 being mapped to negative numbers allow to obtain a derivative different from 0. The parameter ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAZCAMAAAA7W5+HAAAAAXNSR0IArs4c6QAAAE5QTFRFAAAAAAAAAAA6ADqQOgBmOpDbZgA6ZjoAZmY6ZmZmZma2ZrbbZrb/kNv/tmYAtmY6ttv/tv//25A625CQ27Zm2////7Zm/9uQ//+2///bLjH3BwAAAAF0Uk5TAEDm2GYAAAAJcEhZcwAADsQAAA7EAZUrDhsAAAAZdEVYdFNvZnR3YXJlAE1pY3Jvc29mdCBPZmZpY2V/7TVxAAAAP0lEQVQYV8WONwKAIBDAwiE2BGy0/3+U+4KTmTJkCPxLT0ZCPCDaXLcd2hyo0wXFZm6ndyrv6p6Ttogvou0XBpBzAgGeU/06AAAAAElFTkSuQmCC) can be adjusted but it is not easy to choose it.
$$
LeakyReLu(z)=
\begin{cases}
\alpha * z & \text{if } \leq 0 \\
z & \text{if } z > 0 
\end{cases}
$$
-       **SOFTMAX**: used in the output layer for multi-class classification. Allows to obtain values   indicating the probability of each class. N depends on the number of units in the output layer
$$
a^{[i]} = \frac{e^{z^{[i]}}}{\sum_{j=1}^{N} e^{z^{[j]}}}

$$
On each layer the units share the same activation function.