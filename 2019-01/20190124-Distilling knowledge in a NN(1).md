# Distilling knowledge in a neural network

One sample way to improve performance of ML algorithms is to train different models on the same data set, then average their results to get better predictions. However, an ensemble of models like this is too ponderous that not suitable for practical application. Thus, authors tried to distill knowledge in different models into a single model.

The advantage of this way is that cumbersome models make it easier to extract knowledge structure from data and transfer knowledge to a small model. Authors call this process "distillation" that is a different kind of training. While there is an obstacle preventing us from getting closer to this approach. We use parameter values to describe learned knowledge, hence we cannot or it is very hard to change the model without losing knowledge. A more abstract way to see knowledge is that it is a learned mapping from input vectors to output vectors.

We know, to train the network to generalize better to data, we must know the information about the correct way to generalize which is usually not available. However, if we have an ensemble of models which can better generalize to data because the result is an average of many different models, we can use results from ensemble to train the small model, and finally the small model can perform as well as the ensemble.


## References
1. Geoffrey Hinton, Oriol Vinyals, Jeff Dean: Distilling the Knowledge in a Neural Network. 2015.