# How Many Samples are Needed to Estimate a CNN

Authors theorem shows the estimation error scales approximately with the number of parameters in a network. 

In authors experiments, they prove that the prediction error of the CNN (with one conv layer, one conv filter, an average pooling layer and linear activations) is not affected by the stride. Additionally, the prediction error decreases with the quantity of samples increasing, in contrast, it increases with the dimension of filters growing.

While when it comes to the one-layer CNN with a prediction layer, with the stride size increasing, CNN gives better and better performance than FNN, because the number of CNN's parameters is declining.


## References
1. Simon S. Du, Yining Wang, Xiyu Zhai, Sivaraman Balakrishnan, Ruslan Salakhutdinov, Aarti Singh: How Many Samples are Needed to Estimate a Convolutional Neural Network? 2018.
