# Accelerating Learning via Knowledge Transfer

The second function-preserving transformation is `Net2DeeperNet` transformation, which allows us to transform a NN into a deeper one through replacing a layer with 2 layers. Authors' approach is to build a multi-layer NN that factorizes the original layer, which is a specific case of a more general approach. With it, they can make a deeper NN with equivalent ability.

Different from Net2WiderNet, there is no need to add noise while using Net2DeeperNet, though a small quantity of noise can be added to break symmetry. Additionally, Net2WiderNet may be composed with Net2DeeperNet so any hidden layer can be added, which is at least as wide as the below layer.

In evaluation stage, authors used an Inception-BN net trained on ImageNet. About what is Inception Net, I have no clear idea right now and will read the paper[2] about it after.


## References
1. Tianqi Chen, Ian Goodfellow, Jonathon Shlens: Net2Net: Accelerating Learning via Knowledge Transfer. In ICLR, 2016.
2. Christian Szegedy, Wei Liu, Yangqing Jia, Pierre Sermanet, Scott Reed, Dragomir Anguelov, Dumitru Erhan, Vincent Vanhoucke, Andrew Rabinovich: Going Deeper with Convolutions.