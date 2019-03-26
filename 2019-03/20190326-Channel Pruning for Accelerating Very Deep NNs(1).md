# Channel Pruning for Accelerating Very Deep NNs

Authors propose a new channel pruning algo, which has 2 steps(channel selection and feature map reconstruction), to efficiently prune a trained CNN at inference time. It can not only reduce accumulated errors, but also be compatible with various architectures. And more attractively, this algo is able to accelerate modern CNNs twice at the cost of a tiny accuracy loss.

Recently, efforts to accelerate CNNs can be divided into 3 categories: optimized implementation, quantization and structured simplification(like convert into compact CNNs). Structured simplification mainly involves tensor factorization, sparse connection, and channel pruning. Tensor factorization factorizes a convolutional layer into several ones, however, feature map width(num of channels) cannot be reduced, which makes it hard to factorize the 1x1 convolutional layer that is common in modern NN architectures. By contrast, channel pruning can easily reduce feature map width. Additionally, channel pruning is not only implementation friendly, but also needs less amount of computation.

One challenge is that removes channels in one layer may dramatically change the output, which is the input of the following layer. 


## References
1. Yihui He, Xiangyu Zhang, Jian Sun: *Channel Pruning for Accelerating Very Deep Neural Networks*. In ICCV, 2017.