# Subgradient Methods

There are many types of step size rules for choice, additionally, all these choices have a similarity that they don't depend on data generated during training, that means they are all determined before training.


In the case of constant step size and length, the subgradient method is guaranteed to find a sub-optimal point in a limited number of steps, i.e.

<img style="display:block; margin-left:auto; margin-right:auto; width:300px;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190318111415.png?imageslim"/>

*f<sup>\*</sup>* is the optimal value of the problem. *ε* is the function of the step size param *h*, and decreases with it. When *ε* is small enough, the algo can converge to the optimal.

The subgradient method is usually used without stopping criterion, because it can make the subgradient method take too much time to converge.

The biggest demerit of the subgradient method is too slow. However, as authors say, it is a algo with just a few lines of code and has a convergence proof that is also just a few line long, so what else do you expect from it? Except simplicity, the subgradient method also has another big advantage, robustness, which is very obvious in the stochastic subgradient method.


The optimal step size can be determined when *f<sup>⋆</sup>* is known. The formula is 

<img style="display:block; margin-left:auto; margin-right:auto; width:300px;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190321212400.png?imageslim"/>


## References
1. Stephen Boyd, Almir Mutapcic: Subgradient Methods. Notes for EE364b, Stanford University, Winter 2006-07.