# Pruning Filters for Efficient ConvNets


To prune *m* filters  from the *i*th conv layer, we should take the following steps:

1. calculate the sum of each filter's absolute kernel weights;
2. sort filters by the sum of absolute kernel weights;
3. prune *m* filters with the smallest sum values and their corresponding feature maps, correspondingly, filters in the next conv layer taking pruned feature maps as input also should be removed;
4. then a new filter matrix is created for both the *i*th and *i+1*th layers, and the remaining kernel weights are copied to the new model.

Authors say that their method is similar to pruning low magnitude weights, which removes whole filters if all kernel weights are lower than the given threshold. Difficulties lie in that this threshold need to be chosen carefully and it is quite hard to predict the exact number of removed filters. And pruning low magnitude weights generates sparse conv kernels, which are hard to accelerate given the lack of efficient sparse libraries. 

To understand the sensitivity of each layer, authors prune each layer independently and evaluate the accuracy of the resulting pruned network. Authors empirically determine that the number of filter to prune for each layer based on their sensitivity to pruning. Therefore, for layers that are sensitive to pruning, authors only prune a smaller proportion of these layers or skip pruning them directly.


## References
1. H. Li, A. Kadav, I. Durdanovic, H. Samet, and H. P. Graf. *Pruning filters for efficient convnets.* In ICLR, 2017.