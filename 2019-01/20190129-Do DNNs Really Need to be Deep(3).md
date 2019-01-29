# Do DNNs Really Need to be Deep?

Regarding to reasons why models trained on prediction targets, or so-called soft targets, can be much more accurate than those trained on original datasets, authors explain: 1. teacher models can correct error labels that makes the student model able to be trained on more correct datasets; 2. processed by teacher models, complex data has become simpler so that it is much easier for the student model to learn; 3. learning from original dataset is more difficult than from prediction targets.

Also, experiments show that the student model's accuracy improves with as the accuracy of the teacher model increases. This means if better teacher models are available, we will be able to train more accurate shallow feed-forward NNs. In addition, SNNs trained to mimic deep models can perform as well as DNNs, which indicates that DNNs performing so surprisingly arises a part from a good match between careful deep architectures and current training procedures.


## References
1. Lei Jimmy Ba, Rich Caruana: Do Deep Nets Really Need to be Deep? In NIPS, 2014.