# Inception Network

The main idea of Inception Net is based on covering the optimal local sparse structure in the net with easily available dense components. The second idea of this architecture is applying dimension reductions and projections flexibly to decrease computational requirements. A InceptionNet consists of modules stacked upon each other, in other words, it is built from conv building blocks. 

With regard to advantages to this architecture, one is that it can help increase depth and width of NNs without increase of computational complexity, just like said before. Another is it is in line with experience that visual data should be processed at various different scales and aggregated together so that next step can abstract features from different scales at the same time.

One way to utilize the Inception architecture is that create a little inferior version, but requiring less computational power. In this case, the significance of using this architecture is that the created NN can run much faster than those NNs similarly performing without Inception architecture.

## References
1. Christian Szegedy, Wei Liu, Yangqing Jia, Pierre Sermanet, Scott Reed, Dragomir Anguelov, Dumitru Erhan, Vincent Vanhoucke, Andrew Rabinovich: Going Deeper with Convolutions. In 2014.