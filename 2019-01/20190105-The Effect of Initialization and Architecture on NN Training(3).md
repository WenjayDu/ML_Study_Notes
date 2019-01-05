# The Effect of Initialization and Architecture on NN Training

> **(FM1)**: The mean length scale in the final layer increases/decreases exponentially with the depth. 

With regard to ResNet, authors say FM1 is caused by weights of residual modules, and it can be handled by properly rescaling the residual modules. 

🚩 I have not understood part of this section. More information will be added after I get it right. 

> **(FM2)**: The empirical variance of length scales across layers grows exponentially with the depth. 

FM2 for fully connected networks is dependent on the architecture of the network, and as authors illustrated, training efficiency has a negative correlation with the sum of the reciprocals of the widths of the hidden layers. 
Moreover, this conclusion has been proved by their experiments that different types networks having the same sum of reciprocals and depth show similar training efficiency and even the depth increases, this conclusion still works no matter details of network architectures. Therefore, we know that not only the depth of the network, widths of hidden layers also play a vital role in determining network's training efficiency. And of course, all these networks are initialized in the same way to avoid FM1. 

In terms of ResNet, as said before, FM2 will occur if FM1 does too. Additionally, authors assumes that FM2 doesn't occur in the individual residual module.

Furthermore, authors say their logic of proofs about fully connected networks is able to carry over to other architectures, especially, ConvNets.


## References
1. Boris Hanin, David Rolnick: How to Start Training: The Effect of Initialization and Architecture. 2018.