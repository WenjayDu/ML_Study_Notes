# PocketFlow [<sup>[1]</sup>](#r1)

This open source framework is designed to automate processing model compression and acceleration. It integrates a set of compression algos and as we all know, these algos usually have involve a few hyper-params so that they may have a large impact on the compressed model. And unfortunately, obtaining proper values for hyper-params is quite difficult. Therefore, PocketFlow also has a hyper-param optimization module, which is aimed at search the optimal combination of hyper-params for the purpose of minimizing the loss of performance. 

Furthermore, the compressed model can be exported as a TensorFlow-Lite file so that it can be deployed on mobile devices.

PocketFlow is composed of mainly 2 categories of algo components, i.e. learners and hyper-param optimizers. BTW, a learner is a combination of some model compression algos and a few training techniques.

As shown below👇:

<img style="display:block; margin-left:auto; margin-right:auto; width: 700px;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190317205951.png?imageslim"/>

The compression steps are roughly as follows

 1. Input an original model into the framework, the learner will generate a candidate compressed model using a combination of some randomly chosen hyper-params. 
 2. The candidate model's accuracy and computation efficiency will be evaluated and used by hyper-param optimizer as feedback information to determine the next hyper-param combination, which will be utilized by the learner to generate a better candidate model.
 3. After several iterations, the best one of all candidate models will be output as the final compressed model.

Model compression algos supported by PocketFlow are listed below:

Name | Description 
-----|-------------
ChannelPrunedLearner | channel pruning with LASSO-based channel selection [<sup>[2]</sup>](#r2)
DisChnPrunedLearner | discrimination-aware channel pruning [<sup>[3]</sup>](#r3)
WeightSparseLearner | weight sparsification with dynamic pruning ratio schedule [<sup>[4]</sup>](#r4) 
UniformQuantLearner | weight quantization with uniform reconstruction levels [<sup>[5]</sup>](#r5)
NonUniformQuantLearner | weight quantization with non-uniform reconstruction levels [<sup>[6]</sup>](#r6)

All above algos can combine with fast fine-tuning, which directly get a compressed model from the original one by applying pruning masks or quantization functions. In addition, multi-GPU distributed training is also supported in this framework.

When it comes to hyper-param optimizers, there 3 implementations, respectively based on models including Gaussian Processes (GP) [<sup>[7]</sup>](#r7), Tree-structured Parzen Estimator (TPE) [<sup>[8]</sup>](#r8), and Determin-istic Deep Policy Gradients (DDPG) [<sup>[9]</sup>](#r9).

## References
<span id='r1'>1.</span> Jiaxiang Wu, Yao Zhang, Jinlong Hou, Wei Liu, Wenbing Huang : *PocketFlow: An Automated Framework for Compressing and Accelerating Deep Neural Networks*

<span id='r2'>2.</span> Yihui He, Xiangyu Zhang, and Jian Sun: *Channel pruning for accelerating very deep neural networks*. InIEEE International Conference on Computer Vision (ICCV), pages 1398–1406, Oct 2017. 

<span id='r3'>3.</span> Zhuangwei Zhuang, Mingkui Tan, Bohan Zhuang, Jing Liu, Jiezhang Cao, Qingyao Wu, Jun-zhou Huang, and Jinhui Zhu: *Discrimination-aware channel pruning for deep neural networks*. InAdvances in Neural Information Processing Systems (NIPS). 2018. 

<span id='r4'>4.</span> Michael Zhu and Suyog Gupta. To prune, or not to prune: *Exploring the efficacy of pruning for model compression.* CoRR, abs/1710.01878, 2017. 

<span id='r5'>5. </span> Benoit Jacob, Skirmantas Kligys, Bo Chen, Menglong Zhu,Matthew Tang, Andrew Howard, Hartwig Adam, and Dmitry Kalenichenko: *Quantization and training of neural networks for ef-ficient integer-arithmetic-only inference.* InIEEE Conference on Computer Vision and Pattern Recognition (CVPR), pages 2704–2713, June 2018. 

<span id='r6'>6.</span> Song Han, Huizi Mao, and William J. Dally. *Deep compression: Compressing deep neural network with pruning, trained quantization and huffman coding.* InInternational Conference on Learning Representations (ICLR), 2016. 

<span id='r7'>7.</span> J Močkus: *On bayesian methods for seeking the extremum.* InOptimization Techniques IFIP Technical Conference, pages 400–404, 1975. 

<span id='r8'>8.</span> J. Bergstra, D. Yamins, and D. D. Cox. *Making a science of model search: Hyperparameter optimization in hundreds of dimensions for vision architectures.* InInternational Conference on Machine Learning (ICML), pages 115–123, Jun 2013. 

<span id='r9'>9.</span> Timothy P Lillicrap, Jonathan J Hunt, Alexander Pritzel, Nicolas Heess, Tom Erez, Yuval Tassa, David Silver, and Daan Wierstra. *Continuous controlwith deep reinforcement learning*. InInternational Conference on Learning Representations (ICLR), 2016. 