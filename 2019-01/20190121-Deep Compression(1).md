# Deep Compression with Pruning, Trained Quantization and Huffman Coding

When it comes to reasons why we need to compress our models, there are two main aspects, about storage and hardware:

1. To put deep NNs into our apps, we'd better compress our NN models to make our binary files as small as possible, because the bigger the size of the app, the more scrutiny, just like in Apple's APP Store, to download apps over 100MB, you have to connect to WIFI.

2. Of course, to enable NN models run on mobile devices, we must guarantee that electric power can satisfy them, or more general, hardware resources must be capable of supporting NN models, such as memory, computational power.

To handle 2 regards referred to above, authors propose "deep compression" in the paper[1]. To achieve this goal, there are 3 stages to process the NN. Firstly, NN should be pruned to remove redundant connections; secondly, weights are be quantized and multi connections will share the same weight; finally, Huffman coding will be applied to utilize the biased distribution of effective weights. 

Network pruning is a useful and vivid way to reduce complexity and over-fitting of the NN, additionally, recently pruning is able to achieve these goals without any loss of accuracy. After learning the connectivity, connections with small weights which are below a threshold will be pruned, namely be removed. This will surely reduce parameters. After, we get the remaining sparse connections. Moreover, to compress further, authors store the index difference rather than absolute position, which means they assign 8 bits for conv layer and 5 bits for fc layer, and if the difference surpass the bound, like 8, a zero will be filled at that position which is 8 bits away from the previous index.


## References
1. Song Han, Huizi Mao, William J. Dally: DEEP COMPRESSION: COMPRESSING DEEP NEURAL NETWORKS WITH PRUNING, TRAINED QUANTIZATION AND HUFFMAN CODING. 2016.