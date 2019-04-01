# U-Net Compression using KD

In this paper, authors try to use knowledge distillation to compress a U-Net, and they find that the compressing effect is not satisfactory when using only standard distillation whether vanilla or mixed, and the effect can be much better if KD works with other methods like BN and class re-weighting.

With regard to BN, authors add BN into every conv layer of the contracting path. As for class re-weighting, authors re-weight classes according to their proportions in the training dataset. Both these two methods are applied to the student network only. Two modifications allow authors to compress their model by over 1000x of original quantity of params with little decrease in accuracy. Speaking of the principle of 2 methods, BN operations reduce the internal covariate shift and the class re-weighting combats the inherent class imbalance.


## References
1. Karttikeya Mangalam, Mathieu Salzamann: *On Compressing U-net Using Knowledge Distillation*. In 2018.