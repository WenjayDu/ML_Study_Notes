# Less is more: Towards compact CNNs

Authors use tensor low rank constraints and group sparse constraints together to implement the actual strategy.

ReLU was defined as ReLU(x)=max(0,x) which is non-differentiable at 0. Therefore, this makes it difficult to analyze the local minimum of sparse constrained CNNs. So authors modify the definition of ReLU:

```
	 	/ = x, if x>e
ReLU(x){
		\ = 0, if x≤e
```
>where e is chosen such that for any real number x that a computer can represent, if x>0, then x>e; if x≤0, then x<e. The non-differentiable point of ReLU function is now at e which will never appear in practice. 

>Under this definition, ReLU function is differentiable and continuous at point 0, the gradient of ReLU(x) at 0 is now 0.

In experiments, ReLU is proved to be able to remove more neurons not matter sparse constraints are added or not. Additionally, although momentum, which can be seen as a memory of the gradient computed in previous iterations, can accelerate the speed of convergence of SGD, authors find that it tend to keep the number of neurons away from decreasing. Therefore, authors set a neuron's momentum to 0 if it reaches 0.

## References
1. Hao Zhou, Jose M. Alvarez, Fatih Porikli: Less Is More: Towards Compact CNNs. In ECCV, 2016.
