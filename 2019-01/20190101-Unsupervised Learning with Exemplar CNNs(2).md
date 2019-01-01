# Unsupervised Learning with Exemplar CNNs

In the paper, what authors always highlight is that their approache, Exemplar-CNN training does not need any labeled data. Additionally, coz of the design, their algorithm is less sensitive to transformations, compared with earlier research.

To get the trainging data, authors use a series of transformation and their own sampling method to generate surrogate classes. The key is the learning algorithm. Authors illustrate that, to help unsupervised learning methods to learn a useful representative feature from samples, there should be two requirements: 1. images in the same class should have at least one similar feature; 2. images in different classes should have at least obviously different feature. 

In the comparison of previous unsupervised learning methods, most unsupervised learning methods learn this representative feature by modeling the input distribution, which requires the sample class has such a good distribution, and the distribution model is able to contain these information. In addition, this means the sample can be prefactly reconstracted according to the model that contain the representative feature. However, different from them, authors' method learn the feature representation that can distinguish input samples from each other rather than modeling the input distribution. Besides, in contrast, this representation is not requiered to reconstracted samples, which is "unnecessary in a recognition or matching task" as authors say. This makes the net more freely model the desired variability of a sample. Authors point out that " this approach assumes that the transformations do not change the identity of the image content", which means if the identity in a image is not the color but another feature, and we change the color of this image, the net should make no change to this just because the identity is not the color. This is interesting!

The rest of this paper will be discussed tomorrow.


## References
1. Dosovitskiy, A., Springenberg, J.T., Riedmiller, M., Brox, T.: Discriminative unsupervised feature learning with convolutional neural networks. In: NIPS (2014) .