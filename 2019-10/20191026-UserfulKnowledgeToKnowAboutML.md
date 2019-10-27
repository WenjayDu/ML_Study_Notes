# A Few Useful Things to Know about Machine Learning

* **Learning = Representation + Evaluation + Optimization**

* **It’s Generalization that Counts**: Generalization is the fundamental goal of ML. Be careful with data usage and avoid data leakage. Since the objective function is only a proxy for the true goal, we may not need to fully optimize it and in fact, a local optimum may be better than the global optimum.

* **Data Alone Is Not Enough**: No learner can handle everything. Therefore chosen of learner is of importance. ML is not magic, what it does is get more from less, rather than something from nothing. Compared with programing like engineering, learning is more like farming, which lets nature do most of the work. Farmers combine seeds with nutrients to grow crops. Learners combine knowledge with data to grow programs.

* **Overfitting Has Many Faces**: Bias is a learner's tendency to consistently learn the same wrong thing. Variance is the tendency to learn random things irrespective of the real signal. Contrary to intuition, a more powerful learner is not necessarily better than a less powerful one. To figure out whether the distribution of the class is effected by a new structure, performing a statistical significance test like chi-square before adding this structure can help. Noise can aggravate overfitting, but don't cause it.

* **Intuition Fails in High Dimensions**：High dimensions make it hard for ML to generalize correctly, mainly because a size-fixed training set covers only a little fraction of the whole input space as dimensions go higher. Even worse, if there are many irrelevant features, noise from them will overwhelm useful information. And conversely, even all features are relevant, it's still difficult to generalize because all examples in high dimensions look like. It is hard to figure out what is happening in high dimensions. After all, we shouldn't think more dimensions equals more features or this is always good. If many dimensions provide duplicate info, their benefits will be surpass by the curse of dimensionality. 

* **Theoretical Guarantees are not What they seem**：They are just theoretical justification for learners. Learning is combination of theory and practice, it is complex, and theory looks nice doesn't mean the learner will also work in practice.

* **Feature engineering is necessary and important** and maybe the most time-consuming part in ML. Features used during learning could determine whether a ML project succeeds or fails. 

* **more Data Beats a cleverer algorithm**: To improve performance of classifiers, getting more data is usually more pragmatical than designing a better learning algo. Empirically, a poor algo with large amounts of data can outperform a clever one with modest amounts of data. 

* **Learn many models, not Just one**: Learn many models and ensemble them together can much improve the results. Model ensembling is different from Bayesian Model Averaging (BMA), which is a theoretically optimal approach to learning. 

* **Simplicity Does not imply Accuracy**: Contrary to intuition, there is no necessary connection between the number of parameters of a model and its tendency to overfit, just like there is no hypothetical connection between simplicity and accuracy.

* **Representable Does not imply Learnable**: For example, if the hypothesis space has many local optima of the evaluation function, then the learner may cannot find the true function even it is representable. Therefore, the key question should be 'Can it be learned?' rather than 'Can it be represented?'.

* **Correlation Does not imply Causation**: Correlation is a sign of a potential causal connection and can be utilized for further investigation. 


## References
1. P Domingos: [A Few Useful Things to Know about Machine Learning](https://homes.cs.washington.edu/~pedrod/papers/cacm12.pdf).