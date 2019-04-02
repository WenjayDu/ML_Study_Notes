# Pruning Filters for Efficient ConvNets

Authors propose a method to accelerate CNNs, which prune filters that are selected by *l1*-normal having small effect on resulting output. Different from magnitude-based pruning of weights, which removes many params from FCLs rather than conv layers, this approach pruning filters with their connecting feature maps can significantly reduce the computation costs. Additionally, filter pruning is a more natural way of pruning without introducing sparsity, therefore, it do not need extra support of sparse libs or other specialized hardware.

To determine which filters to prune, authors measure the importance of a filter in each layer by calculating the sum of absolute values of weights. They find that compared to other filters in current layer, filters with smaller kernel weights tend to produce feature maps with weak activations, and pruning smallest filters can work better in comparison with pruning the same number of other combinations like random or larger filters. 


## References
1. H. Li, A. Kadav, I. Durdanovic, H. Samet, and H. P. Graf. *Pruning filters for efficient convnets.* In ICLR, 2017.