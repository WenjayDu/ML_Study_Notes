# The Effect of Initialization and Architecture on NN Training

> **(FM1)**: The mean length scale in the final layer increases/decreases exponentially with the depth. 

In a fully connected NN, the lengths of vectors of activations will change during propagation, as a result, lengths of the final output vectors may be dramatically different with lengths of input ones. These changes can be summarized by a formula. And authors prove that the mean of the normalized output length, which controls the occurrence of FM1, is determined by the variance of the distribution that is used to initialized weights. Hence, FM1 cannot be directly solved by batch normalization for it renormalizes by averaging over inputs to the layer, rather than averaging over initializations for the layer. Additionally, authors point out that ReLU is one of the most common activation functions and many initializations are blindly used with ReLUs without recognizing the effect on training.


## References
1. Boris Hanin, David Rolnick: How to Start Training: The Effect of Initialization and Architecture. 2018.