# The Effect of Initialization and Architecture on NN Training

In this paper[1], authors study 2 common failure modes(related to problems preventing NN to achieve better-than-chance performance) in NN training and give suggestions to avoid them. Besides, they demonstrate that their theoretical results can predict when NNs are able to start training. Correct initialization and architecture enable deeper NN to be trained, while many pop initializations do not meet the standard proposed by authors. 

Firstly, let us take a look at 2 failure modes and authors' main contributions & conclusions(copied from the original, I think they are able to provide guidance):

> ---
> **2 Failure Modes:**
>
> **(FM1)**: The mean length scale in the final layer increases/decreases exponentially with the depth. 
> 
> **(FM2)**: The empirical variance of length scales across layers grows exponentially with the depth. 
> 
> ---
> **Contributions & Conclusions:** 
> 
> + **The mean and variance of activations in a neural network are both important in determining whether training begins.** If both failure modes FM1 and FM2 are avoided, then a deeper network need not take longer to start training than a shallower network. 
> + **FM1 is dependent on weight initialization.** Initializing weights with the correct variance (in fully connected and convolutional networks) and correctly weighting residual modules (in residual networks) prevents the mean size of activations from becoming exponentially large or small as a function of the depth, allowing training to start for deeper architectures. 
> + **For fully connected and convolutional networks, FM2 is dependent on architecture. Wider layers prevent FM2, again allowing training to start for deeper architectures.** In the case of constant-width networks, the width should grow approximately linearly with the depth to avoid FM2. 
> + **For residual networks, FM2 is largely independent of the architecture.** Provided that residual modules are weighted to avoid FM1, FM2 can never occur. This qualitative difference between fully connected and residual networks can help to explain the empirical success of the latter, allowing deep and relatively narrow networks to be trained more readily. 
> ---

About FM1, authors find that, with poor initializations, their training fails more frequently as the network depth increases. They prove the key to avoid FM1 in ResNets is rescale the contributions of single residual modules appropriately.

Regarding to FM2, authors say it seems that there are few people studying about it. They propose two possible explanations about it: 1. variances between activations at different layers are extremely big, hence some layers may have so small or big activations that they exceed computer precision. 2. the backpropagated SGD update for a weight in a given layer includes a factor that depends on the size of the previous layer. A small update cannot change this weight very much. But a very big update can make this weight re-randomized. So authors infer that "FM2 causes the stochasticity of parameter updates to outweigh the effect of the training loss". And they find the difference between fully connected NN and ResNets. For fully connected NN, even if FM1 does not exist, FM2 can still occur. However, regarding to ResNets, if FM1 does not occur, neither will FM2.


## References
1. Boris Hanin, David Rolnick: How to Start Training: The Effect of Initialization and Architecture. 2018.