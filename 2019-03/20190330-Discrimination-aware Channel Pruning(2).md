# Discrimination-aware Channel Pruning


Reconstructing feature maps can preserve most info in the trained model. However, it has 2 limitations 1. the pruning performance will be influenced by the quality of the pre-trained model; 2. although some channels in intermediate layers have no relevance with the network's discriminative power, they are kept mistakenly to minimize the reconstruction error, especially when the network is deeper.

Authors want to pruning channels according to their contribution for the discriminative power of the network. But it is quite difficult to measure the discriminative power of channels because of complex operations in CNNs.

One key of authors' method is the construction of discriminative-aware loss. To make computation feasible and accelerate the convergence, authors apply an average pooling operation, which can help to decrease the amount of params and computation, over the feature maps and BN & ReLU before the average pooling respectively. Therefore, the input feature maps for the loss at layer *L<sub>p</sub>* cab be written as **F**<sup>p</sup>(**W**) = AvgPooling(ReLU(BN(**O**<sup>p</sup>)))

where **O**<sup>p</sup> represents the output feature maps of the layer L<sub>p</sub>. Make **F**<sup>(p,i)</sup> be the feature maps with regard to the i-th example, then the discriminative-aware loss w.r.t the p-th loss can be formulated as 


<img style="display:block; margin-left:auto; margin-right:auto; width:500px;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190401193054.png?imageslim"/>

where I{·} is the indicator function, <img style="width:10%;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190401193913.png?imageslim"/> denotes the classifier weights of the fully connected layer(FCL), n<sub>p</sub> denotes the number of input channels of the FCL and m is the number of classes. 

In practice, authors take both cross-entropy loss and reconstruction loss into consideration and obtain a joint loss function as ***L***(**W**) = ***L***<sub>M</sub>(**W**) + λ***L***<sup>p</sup><sub>S</sub>(W), where λ is used to balance the two terms.


## References
1. Zhuangwei Zhuang, Mingkui Tan, Bohan Zhuang, Jing Liu, Jiezhang Cao, Qingyao Wu, Jun-zhou Huang, and Jinhui Zhu: *Discrimination-aware channel pruning for deep neural networks*. InAdvances in Neural Information Processing Systems (NIPS). 2018.
