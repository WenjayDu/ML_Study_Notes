# Discrimination-aware Channel Pruning

At each stage of Discrimination-aware channel pruning, authors first construct the additional loss ***L***<sup>p</sup><sub>S</sub> and put them at the layer ***L***<sub>p</sub>, then learn the model params and fine-tune the model at the same time with both additional loss and final loss, this will make params updated. After fine-tuning with ***L***<sup>p</sup><sub>S</sub> and ***L***<sub>f</sub>, the discriminative power of layers l ∈ { ***L***<sub>p-1</sub>, ..., ***L***<sub>p</sub>} can be significantly improved.


To optimizing discriminative-aware channel pruning, authors design a greedy algo to select channel and optimize params in a iterative way. The selection method consists of 2 steps. First, select the most important channels of input feature maps. At each iteration, compute gradients and use them to determine the 𝒜 (see the algo in the original paper for details), which is the index set of selected channels. Second, apply SGD to handle the problem w.r.t. 𝒜.


Authors’ main contributions can be divided into two aspects. One is they propose the discriminative-aware channel pruning method for compressing deep networks. The other is they formulate the channel selection problem and present a greed alog to solve the optimization problem.


## References
1. Zhuangwei Zhuang, Mingkui Tan, Bohan Zhuang, Jing Liu, Jiezhang Cao, Qingyao Wu, Jun-zhou Huang, and Jinhui Zhu: *Discrimination-aware channel pruning for deep neural networks*. InAdvances in Neural Information Processing Systems (NIPS). 2018.