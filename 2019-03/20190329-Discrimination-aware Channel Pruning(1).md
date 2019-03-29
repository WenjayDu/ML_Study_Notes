# Discrimination-aware Channel Pruning

Existing pruning methods fall into 2 categories, they either train from scratch with sparsity constraints on channels, or minimize reconstruction error between the pre-trained feature maps and compressed ones. However, the former requires too much computational power and is hard to converge
, and the latter ignore the discriminative power of channels, in addition, in the latter methods, actually redundant channels may be kept wrong to minimize the reconstruction error.


In this paper, to avoid these defects, authors emphasize the informative channel which should has its own discriminative power, or it should be removed. Therefore, to find these channels with true discriminative power, authors add multiple additional losses to the net. They first use one additional loss and the final loss to do fine-tuning to improve discriminative power of intermediate layers. Then doing channel pruning on each layer with both the additional loss and reconstruction error of feature maps. Making up the drawbacks of the second category of methods, this can not only optimize the reconstruction error, but also takes care of discriminative power.



## References
1. Zhuangwei Zhuang, Mingkui Tan, Bohan Zhuang, Jing Liu, Jiezhang Cao, Qingyao Wu, Jun-zhou Huang, and Jinhui Zhu: *Discrimination-aware channel pruning for deep neural networks*. InAdvances in Neural Information Processing Systems (NIPS). 2018.