# Curriculum learning

Research shows that human and animals can learn much better if examples are organized in a meaningful order that illustrates gradually more concepts which are more complex, rather than randomly. This is the main basis of the training method in this paper[1], called Curriculum Learning. Its basic idea is start with small and easier tasks, and then gradually increase the difficulty level. In addition, authors assume that a well chosen curriculum can act like a continuation method, which can help to find better local minima of a non-convex training criterion. Besides, experiments on convex criteria show that curriculum learning method also can speed the convergence of training.

Authors try to use deep architectures to test their assume, because deep architectures perform well in the aspect of finding local minima. But training deep architectures is confronted with the non-convex optimization problem. About what is non-convex optimization, I will read the paper[2] later. Training deep architectures cannot be implemented well until an unsupervised training algorithm, which trains one layer at a time, proposed by Hinton. This algorithm trains each layer one after the other, one first learns simpler content, then more complex content. Related work about this algorithm suggest that unsupervised pre-training might help start supervised optimization in a region of parameter space. Authors say pre-training with a curriculum strategy might act similarly to unsupervised pre-training in the aspects of finding better local minima and acting as a regularizer.


## References
1. Bengio, Y.: Curriculum Learning. In 2009. 
2. Prateek Jain, Purushottam Kar: Non-convex Optimization for Machine Learning. In 2017.