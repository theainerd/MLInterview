# Deep Learning

## Activation Function

* Sigmoid (not used because they suffer from vanishing and exploding gradient problem, except in LSTM/RNN)
* Tanh 
* ReLu (Dead Neurons Problem)
* Leaky ReLu (Solve the Dead Neurons Problem)
* ELU (Exponential Linear Unit)

## Dropout

A form of regularization useful in training neural networks. Dropout regularization works by removing a random selection of a fixed number of the units in a network layer for a single gradient step. The more units dropped out, the stronger the regularization. This is analogous to training the network to emulate an exponentially large ensemble of smaller networks.
