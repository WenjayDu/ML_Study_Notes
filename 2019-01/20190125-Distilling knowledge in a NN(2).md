# Distilling knowledge in a neural network

The distillation is that we use an ensemble of models to train a smaller single model, just like a teacher teaches a student. Different from training the small NN with correct labels which called hard targets are one to one, the ensemble's output of possibilities of different results called soft targets is able to give more valuable information to the small model, just like the example of MNIST taken by authors in the paper. The purpose of this method is just the same with the softmax layer applied in many NNs. One of their functions is to reduce overfitting. 

In their experiments on MNIST, authors found that soft targets could transfer much knowledge to the distilled model, including knowledge about how to generalize data learned from the original training set.

In experiments on speech recognition, the distilled model performed better than the model with the same size learning from the same training set that used to train the ensemble of models.

## References
1. Geoffrey Hinton, Oriol Vinyals, Jeff Dean: Distilling the Knowledge in a Neural Network. 2015.