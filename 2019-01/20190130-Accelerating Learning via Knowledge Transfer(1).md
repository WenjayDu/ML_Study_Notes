# Accelerating Learning via Knowledge Transfer

In this paper, authors propose a technique called Net2Net that is able to transfer knowledge from a previous NN to a more complex(deeper & wider) new NN to accelerate the training process. Different from pre-training presented previously, this technique is based on the concept of function-preserving transformation. 

In practical use, training workflows are very complicated. And one traditional training method is that train multiple models on one dataset, and training for each model is based on the previous model to improve itself. However, this data-driven design method takes too much time, especially when objects are large models, mainly because the big number of training times and time spent on evaluating the improvement of every change. 

In feature prediction, authors refer to the approach that a student learning from a teacher like the FitNets strategy. The next paper I will read is about FitNet, called *FitNets: Hints for Thin Deep Nets*[2].

Compared with traditional methods, Net2Net enable the new model to learn knowledge from the previous best model. One more ambitious thing is that Net2Net can make lifelong learning system work more smoothly rather than spending weeks or months on retraining models on latest dataset.


## References
1. Tianqi Chen, Ian Goodfellow, Jonathon Shlens: Net2Net: Accelerating Learning via Knowledge Transfer. In ICLR, 2016. 
2. Adriana Romero, Nicolas Ballas, Samira Ebrahimi Kahou, Antoine Chassang, Carlo Gatta, Yoshua Bengio: FitNets: Hints for Thin Deep Nets. In ICLR, 2015.