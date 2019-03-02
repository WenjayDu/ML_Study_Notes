# Subgradient Methods

There are several general approaches can be used to speed up the subgradient method. They are

* Localization methods

such as cutting-plane and ellipsoid methods also require the evaluation of one subgradient per iteration, but require more computation to carry out the update.

Different from the subgradient method, some of them have real (non-heuristic) stopping criteria. 

* Bundle methods

In bundle methods, the update direction is determined by the combination of some bundles of previous subgradients, which can help estimate the steepest descent direction. 

* Heavy ball method / Conjugate gradients methods

They use an update direction that is a combination of the current negative subgradient and the last search direction.

These algos all have state, however, the basic subgradient method is stateless.

## References
1. Stephen Boyd, Almir Mutapcic: Subgradient Methods. Notes for EE364b, Stanford University, Winter 2006-07.