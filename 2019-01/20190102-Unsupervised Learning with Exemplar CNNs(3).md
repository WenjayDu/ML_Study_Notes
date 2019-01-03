# Unsupervised Learning with Exemplar CNNs

In experiments, the NN's accuracy rises with the number of surrogate classes and reaches the peak finally(the NN's scale bigger, needed amount of classes larger), after that, the accuracy even has a decline although more classes are fed into the NN. They say too many samples decrease the performance of NN. Hence, the number of samples is a key for training, however, this problem can be solved by clustering(I don't know much about clustering, just know it is a representation of unsupervised learning).

Besides this, authors found that their NN cannot deal with blur well that meant increasing blur would cause performance to drop. Therefore, they trained another Exemplar-CNN to handle this problem, I take their design below 👇 for my future reference maybe:

> First, we increased the filter size and introduced a stride of 2 in the first convolutional layer, resulting in the following architecture: 64c7s2-128c5-256c5-512f. This allows the network to identify edges in very blurry images more easily. Secondly, we used unlabeled images from Flickr for training, because these represent the general distribution of natural images better than STL. Thirdly, we applied blur of variable strength to the training data as an additional augmentation. We thus call this network Exemplar-CNN-blur. As with AlexNet, we max-pooled the feature maps produced by the Exemplar-CNNs to a 4x4 spatial size.


Compared with previous unsupervised learning methods, the method proposed in this paper that learning invariance from data improves performance a lot on classification tasks. With the Exemplar-CNN-blur mentioned above, authors solved the blur problem which troubled the state of the art algorithm before and they say this proves the flexibility of unsupervised learning methods, in addition, data augmentation plays an vital role in both supervised and unsupervised learning.  


## References
1. Dosovitskiy, A., Springenberg, J.T., Riedmiller, M., Brox, T.: Discriminative unsupervised feature learning with convolutional neural networks. In: NIPS (2014) .
