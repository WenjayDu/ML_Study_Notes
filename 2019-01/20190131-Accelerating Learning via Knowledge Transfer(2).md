# Accelerating Learning via Knowledge Transfer

The 2 effective Net2Net strategies are based on function-preserving initialization, which initializes the student NN to represent same function as the teacher NN. This is repeatedly emphasized by the authors. Compared with other approaches to growing the NN, function-preserving initialization has many merits:

```
1. The new and larger NN is able to perform as well as the original NN immediately, without experiencing a stage of low performance.
2. As long as every local step is an improvement, any change made to the NN after the initialization will cause improvement.
3. Optimizing all params is always safe, without any layer receiving harmful gradients and having to be frozen.
```

The first function-preserving transformation is `Net2WiderNet` transformation, which allow a layer to be replaced with a wider one. Using the Net2WiderNet operator to create a student network with the same function as the teacher, then replicating many randomly chosen units in one layer and some noise will be added to break symmetry after replication, and sure many layers are widen just like this, rather than just one.


## References
1. Tianqi Chen, Ian Goodfellow, Jonathon Shlens: Net2Net: Accelerating Learning via Knowledge Transfer. In ICLR, 2016.