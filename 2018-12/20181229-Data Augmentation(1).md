# Data Augmetation

ML algorithms' performance is positively related to the amount of data, however, in some fields such as medical industry, data from patients is heavily protected. Hence, development of ML algorithms in medical industry is hindered beacause of little available training data.

Little training data makes models can not generalize well test datasets. This problem is called overfitting. There are some methods to reduce overfitting. 1. Add norm regularization to weights(authors say this is the samplest); 2. Add dropout layers which can randomly remove some neural units or disconnect some connections; 3. Apply batch normalizaiton to layers; 4. Use pre-trained weights of a similar NN and then tune parameters of the NN under training(this is called "transfer learning"); 5. the last one referred is that use data augmentation, "such as cropping, rotating, and flipping input images".

In this paper, authors use GANs to augment data. As they say, GANs are not only good at this, but also very good at performing transfer learning. 

To be continue……


## References
1. Luis Perez, Jason Wang: The Effectiveness of Data Augmentation in Image Classification using Deep Learning. 2017.