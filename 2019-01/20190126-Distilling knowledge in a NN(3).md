# Distilling knowledge in a neural network

Another reason why we should not use an ensemble of models to improve the performance is that if the individual models and data sets are both quite big, the amount of computation required will be too large that unavailable. 
Based on the problem of dig training dataset containing lots of classes, authors present that except a generalist model trained on the whole dataset, many other models called specialists should be trained on confusable subsets. Besides, these specialist models are initialized with weights of the generalist model to reduce overfitting and share results obtained during the training of the generalist model previously. Because of this, specialist models train very fast.

Regarding to why using soft targets rather than hard ones, there are 2 reasons, just as said before, one is the former contains much useful information that the latter does not. Additionally, soft targets are also an effective way to transfer regularities from one generalize model to another model, right like results in authors' experiments on MNIST. Another is soft targets can help reduce overfitting during the training of specialists

The ensemble of specialists is a bit like the mixtures of experts, which use a gating network to assign an input to an expert. Different from these mixtures, authors say they use a confuse matrix to define which subsets should be used to train which specialists. When testing, predictions from the generalist model will decide which specialists should handle the input.

## References
1. Geoffrey Hinton, Oriol Vinyals, Jeff Dean: Distilling the Knowledge in a Neural Network. 2015.