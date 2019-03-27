# Channel Pruning for Accelerating Very Deep NNs

One step of the algo present in this paper is that find out the most representative channels and prune redundant ones. Once these channels are removed, those channels taking them as input and filters producing them can be remove as well. So, one channel pruned wrong could mess up the whole model. According to authors, an exhaustive search to select proper channels is infeasible, therefore, they design a method based on LASSO regression to find out those most representative channels.

The other step is to reconstruct outputs with the remaining channels with linear least squares. 

To prune the whole model, authors apply their approach layer by layer. However, confronted with multi-branch networks like ResNet, the situation is much more complicated. The main reason is that the first layer and the last layer cannot be pruned as is described above. The first layer with large input feature map width and is shared with shortcuts cannot be pruned easily. Because of the param-free shortcut, accumulated error at the last layer is difficult to be recovered.


## References
1. Yihui He, Xiangyu Zhang, Jian Sun: *Channel Pruning for Accelerating Very Deep Neural Networks*. In ICCV, 2017.
