# Do DNNs Really Need to be Deep?

In experiments on TIMIT, which is a speech corpus, although the shallow model had much more params, its accuracy was still lower than DNNs. However, after the shallow one was trained with the model compression to mimic a more accurate one, it could perform as well as the deep model. This shows that a sample net with a big single hidden layer without any careful design can perform similarly to a DNN.

Results of experiments show that in the case where the parameter numbers of each model are equal and increasing, the mimic model is capable of outperforming the DNN, and comparable to the CNN, though never reach the accuracy of ECNN(an ensemble of CNNs) because of no enough unlabeled data, authors say. 


## References
1. Lei Jimmy Ba, Rich Caruana: Do Deep Nets Really Need to be Deep? In NIPS, 2014.