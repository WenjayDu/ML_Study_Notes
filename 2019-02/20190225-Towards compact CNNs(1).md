# Less is more: Towards compact CNNs

To make CNNs more light and compact, authors present a new method to decimate the number of neurons. 

There are 4 advantages of their method: 

* it doesn't need pre-training, because neurons are assessed and decimated during training
* reduction of params doesn't rely on the sparsity of neurons, therefore, this method can be included into deep learning toolboxes directly
* the number of filters in Fourier domain is proportional to the number of neurons in the spatial domain, thus this method can reduce the params in the Fourier domain as well
* reducing the number of the neurons can condense the data dimensionality when the output of an internal layer is used as image features

Additionally, authors' method impose sparse constraints on neurons of a CNN in the objective function during training phase. And to minimize the computational cost of adding the constraints, they use the Forward-Backward Splitting method[2] to solve the sparse constrained optimization problem. About what is Forward-Backward Splitting method, I will read the paper[2] latter. ReLU, which helps to reduce the number of neurons leading to the more compact NNs, also plays a vital role in the sparse constrained CNNs.

## References
1. Hao Zhou, Jose M. Alvarez, Fatih Porikli: Less Is More: Towards Compact CNNs. In ECCV, 2016.
2. Duchi, J., Singer, Y.: Efficient online and batch learning using forward backward splitting. J. Mach. Learn. Res. 10, 2899–2934 (2009) 
