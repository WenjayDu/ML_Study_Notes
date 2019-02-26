# Less is more: Towards compact CNNs

Related work can be organized in 3 categories: knowledge distillation, memory efficient structures and parameter pruning. To learn more about memory efficient structures, I will read the paper[2] later. About pruning, authors say the approach proposed in the paper[3], which I read before, is complementary to theirs and can be utilized to further compress the model trained using their method.

Authors' goal is to add sparse constraints on neurons in a CNN, and they convert the optimization problem to a formula. However, a sub-formula in it is non-differentiable at some points and sub-gradient methods cannot handle this problem well. Therefore, authors apply proximal operator to the problem. About proximal operator, I will read the paper[4] later.

And Forward-Backward Splitting method is a good choice to solve the non-differentiable and constrained large-scale optimization problem. It has 2 advantages: 1. it is easy to estimate optimal operator; 2. backward analysis has strong impact on convergence if the function is convex. It is noteworthy that Forward-Backward Splitting method usually works well for non-convex optimization problems, though there is no grantee for convergence if the function is non-convex.

## References
1. Hao Zhou, Jose M. Alvarez, Fatih Porikli: Less Is More: Towards Compact CNNs. In ECCV, 2016.
2. Denil, M., Shakibi, B., Dinh, L., Ranzato, M., Freitasa, N.D.: Predicting parameters in deep learning. In: NIPS (2013) 
3. Han, S., Mao, H., Dally, W.J.: Deep compression: Compressing deep neural network with pruning, trained quantization and huffman coding. In: ICLR (2016)
4. Maxwell D. Collins, Pushmeet Kohli: Memory Bounded Deep Convolutional Networks. In 2014.