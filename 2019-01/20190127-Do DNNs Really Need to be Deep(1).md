# Do DNNs Really Need to be Deep?

Authors give an example that a shallow NN and a deep NN both trained on a big dataset, and of course, the shallow one has a low accuracy on test dataset. Then authors raise a question that why the deep one has a higher accuracy? They give the below options： 👇

```
a) the deep net has more parameters;
b) the deep net can learn more complex functions given the same number of parameters; 
c) the deep net has better bias and learns more interesting/useful functions (e.g., because the deep net is deeper it learns hierarchical representations [5]); 
d) nets without convolution can’t easily learn what nets with convolution can learn; 
e) current learning algorithms and regularization methods work better with deep architectures than shallow architectures[8]; 
f) all or some of the above; 
g) none of the above? 
```

There have been many researches on this question. These studies show that DNNs are more complex than shallow ones and much more parameters enable DNNs to own much stronger expressive abilities.

While in this paper, authors prove that shallow nets can be the same accurate as DNNs. Certainly, the way they used to train shallow nets is different from the normal. Their method is to use the shallow net to mimic the DNN and it is like the method of distilling knowledge from NNs. The shallow nets are trained on the data called logit output before softmax layer by the DNNs, rather than output by the softmax layer. The reason is the same with that why train the smaller model with soft targets instead of hard ones in knowledge distillation: there is much more valuable information beneficial to training shallow NNs in these logits.

Furthermore, authors think the process that the shallow net learns from the complex net is compression, mainly because the mimic model is finally able to perform like the deep model, but much smaller. 

Usually, training shallow NNs with logits and enabling them to learn knowledge fully take several weeks, but authors found that adding a linear layer between input and non-linear hidden layer can speed up the training process considerably.


## References
1. Lei Jimmy Ba, Rich Caruana: Do Deep Nets Really Need to be Deep? In NIPS, 2014.