# Channel Pruning for Accelerating Very Deep NNs

<img style="display:block; margin-left:auto; margin-right:auto; width:500px;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190329212127.png?imageslim"/>

To address these problems in ResNets, authors present some variants.

For the last layer, the output of the layer is composed of Y1 and Y2. Y2 can be approximated with the formula proposed by authors. The main point is Y1 from the shortcut that cannot be recovered directly. Authors change the optimization goal from Y2 to Y1-Y1'+Y2, where Y1' is the current feature map after previous layers pruned. While pruning, volumes should be sampled from theses two branches.

For the first layer, there are two option. One is performing feature map sampling before the first convolution and sampling selected channels on shared feature maps to construct a new input for the later convolution. The other is filter-wise pruning, which applies the original method to each filter independently, each filter choose its own representative input channels, since input channels of param-free shortcut cannot be pruned. However, compared with the first option, it output irregular convolution, which needs specific lib implementation support.


## References
1. Yihui He, Xiangyu Zhang, Jian Sun: *Channel Pruning for Accelerating Very Deep Neural Networks*. In ICCV, 2017.