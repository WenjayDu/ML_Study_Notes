# Subgradient Methods

Subgradient methods are good choices to minimize the non-differentiable functions. Subgradient methods have 3 obvious differences with ordinary gradient methods: 

> 1. the subgradient method applies directly to non-differentiable functions.
>
> 2. the step length are pre-specified ahead of time in most cases, that is different from the one in ordinary gradient methods, chosen by a linear search and adaptively computed.
> 
> 3. the ordinary gradient method is a descent method, but in the subgradient method, the function value can increase.

The subgradient method can be extended to handle problems with constraints.

Although in unconstrained cases subgradient methods that are first-order methods whose performance will be affected by problem scaling are much slower than interior-point methods and Newton's method, which are both second-order methods, subgradient methods have their own merits -- they can be applied to a much wider variety of problems and occupy smaller memory footprint.

Since the subgradient method is not a descent method, it is easy to keep track the minimal function value -- compare the value of current step with the best point found before, just like

<img style="display:block; margin-left:auto; margin-right:auto; width:300px;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190317095449.png?imageslim"/>

<sup>(k)</sup> is the *k*th iterate.

Then we can get the minimize, and the formula can be written as follows

<img style="display:block; margin-left:auto; margin-right:auto; width:300px;" src="https://cdn.safeandsound.cn/ML_Study_Notes/image/20190317095507.png?imageslim"/>


## References
1. Stephen Boyd, Almir Mutapcic: Subgradient Methods. Notes for EE364b, Stanford University, Winter 2006-07.