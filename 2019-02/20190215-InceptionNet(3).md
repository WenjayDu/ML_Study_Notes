# Inception Network

GoogLeNet is a particular instance of InceptionNet and its name is a homage to LetNet5. Although the number of layers with params is 22, the overall number of layers is about 100. Therefore, taking into account the relative large depth, ensuring that gradients are propagated back though all layers effectively is a problem. To handle it, authors add auxiliary classifiers that are in the form of ConvNets and encourage discrimination in them to increase gradient signal propagated back and provide additional regularization. It is noteworthy that these classifiers only work during training that their loss are added to the total loss with a weight, but at inference time, they are discarded.

As authors have always emphasized, the main merit of authors' method is that the network can get an obvious improvement at a modest increase of computational resource.

## References
1. Christian Szegedy, Wei Liu, Yangqing Jia, Pierre Sermanet, Scott Reed, Dragomir Anguelov, Dumitru Erhan, Vincent Vanhoucke, Andrew Rabinovich: Going Deeper with Convolutions. In 2014.