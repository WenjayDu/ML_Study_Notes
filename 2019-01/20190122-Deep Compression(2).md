# Deep Compression with Pruning, Trained Quantization and Huffman Coding

After pruning, authors try to use quantization and weight sharing to compress the NN further. Quantization is a way which divides weight matrix into different clusters, each cluster has a certain range, weights that are in the same range should be put into the same cluster. Then sum every weight in each cluster, we get a group of nums. In each relative position in the gradient matrix, gradients also are put into different clusters, then sum, get another group of nums. We subtract the second one with the first one, then get the final group called "fine-tuned centroids".

Weight sharing is realized by k-means clustering which is used to identify shared weights, after clustering, those in the same cluster share the same weight. Larger weights play a more important role than smaller ones, but the number of the former is much smaller. After their experiments, authors found that the linear initialization performs best in all methods.

## References
1. Song Han, Huizi Mao, William J. Dally: DEEP COMPRESSION: COMPRESSING DEEP NEURAL NETWORKS WITH PRUNING, TRAINED QUANTIZATION AND HUFFMAN CODING. 2016.