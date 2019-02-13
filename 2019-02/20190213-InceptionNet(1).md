# Inception Network

The idea of Inception Net introduced in this paper[1] for CV, which is able to use the computing resources better, allows us to increase the depth and width of the NN with the constant computational power. 

The most straightforward way to improve the performance of the NNs is by increasing both their depth and width, which means more parameters, bringing stronger expressive ability. However, more params make NNs easier to overfitting and of course, and need more computational resources. Hence, to increase depth and width but decrease the number of params, the fundamental way of handling these two issues is by moving from fully connected to sparsely connected architectures. Whereas, todays computing infrastructures are very inefficient when calculating on non-uniform sparse data. Therefore, we have to design an architecture that can not only make use of extra sparsity, but also utilize the computation on dense matrices. Vast research shows that clustering sparse matrices into relatively dense submatrices can improve performance for sparse matrix multiplication.

## References
1. Christian Szegedy, Wei Liu, Yangqing Jia, Pierre Sermanet, Scott Reed, Dragomir Anguelov, Dumitru Erhan, Vincent Vanhoucke, Andrew Rabinovich: Going Deeper with Convolutions. In 2014.