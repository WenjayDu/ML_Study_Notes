# Pruning Filters for Efficient ConvNets

Understanding pruning filters across consecutive layers at once is vital, because 

>1. pruning and retraining layer by layer can be quite time-consuming; 
2. pruning layers across the network gives a holistic view of the robustness of the network resulting in a smaller network;
3. a holistic approach may be necessary;

And, to prune filters across multiple layers, authors consider 2 strategies for layer-wise filter selection:

* Independent pruning determines which filters should be pruned at each layer independent of other layers;
* Greedy pruning accounts for the filters that have been removed in the previous layers. This strategy does not consider the kernels for the previously pruned feature maps while calculating the sum of absolute weights.

The above two strategies are combined to generate the new kernel matrix.

Different from simple CNNs like VGGNet or AlexNet, of which, any of filters in any conv layers can be pruned, complex network like ResNet cannot be pruned straightforward, because `the correspondence between the output feature maps of the second conv layer and the identity feature maps make it difficult to prune`. Therefore, the corresponding projected feature maps must also be pruned to ensure the success of pruning the 2nd conv layer of the residual block. And now that the identical feature maps are more vital than the added residual maps, the feature maps should be determined by the pruning results of the shortcut layer.

To compensate the loss in accuracy caused by pruning, we should retrain the network. And there are also 2 strategies to operate:

1. Prune once and retrain: Prune filters of multiple layers at once and retrain them until the original accuracy is restored.
2. Prune and retrain iteratively: Prune filters layer by layer or filter by filter and then retrain iteratively. The model is retrained before pruning the next layer for the weights to adapt to the changes from the pruning process.

Authors find that layers are resilient to pruning, and the former strategy `can be used to prune significant portions of the network and any loss in accuracy can be regained by retraining for a short period of time`, but if some filter in sensitive layers or larger portions of the networks are removed, it may be not possible to recover the original accuracy. The latter strategy may get better results, but its disadvantage lies in that the iterative process is time-consuming, especially for DNNs.

## References
1. H. Li, A. Kadav, I. Durdanovic, H. Samet, and H. P. Graf. *Pruning filters for efficient convnets.* In ICLR, 2017.