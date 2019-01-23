# Deep Compression with Pruning, Trained Quantization and Huffman Coding

Huffman coding is a common way to compress data losslessly, which can help reduce data storage size, especially when original data is non-uniformly distributed. 

Conclusion from authors' experiments shows that pruning and quantization perform unsatisfactorily when working individually, because high compression rates and high accuracy cannot be obtained at the meanwhile, although they are both able to compress the NN. However, when combined, the network can be compressed to a much smaller size without any loss of accuracy that means they work well with each other.

In addition, the model size is dominated by FC layers that are compressed the most by deep compression and consume much time during computation on the model.

## References
1. Song Han, Huizi Mao, William J. Dally: DEEP COMPRESSION: COMPRESSING DEEP NEURAL NETWORKS WITH PRUNING, TRAINED QUANTIZATION AND HUFFMAN CODING. 2016.