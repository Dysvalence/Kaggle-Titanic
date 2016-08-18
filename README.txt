Kaggle-Titanic

This script imports the Kaggle Titanic dataset in .csv form, extracts a new feature from name data, imputates missing
values using an autoencoder initialized neural network set for regression. Lastly it builds an autoencoder initalized
deep neural network to determine if an individual in the test set is likely to have survived. Keras is used for all NNs.

Originally I randomly partitioned off 91 of 891 examples for validation testing, however, training accuracy was severely 
affected and test accuracy was very erratic depending on which 91 were chosen, i.e. insufficent data. As my primary goals 
were to practice using Pandas and neural networks, I did not look at other ways to deal with this. However, I ran the 
autoencoder on the entire dataset during training, including the test set. This obviously risks overfitting the test set,
but I wanted to see if it would help, as that would suggest that mixing unlabeled and labeled data in such a fashion may 
be useful. 

There is also a massive bug- monitoring training via the verbosity setting on Keras results in Jupyter bugs. The latest
update fixed the crashing, but now the latency is horrendous. To work around this, multiple models with increasing epochs
are run to easily pick the best one, at the cost of a significant increase in complexity. When autoencoder initialized 
layers are used, I accidentally set it to shallow copy, and as such it is trained by every model that touches it. For some
reason this helps by a few percent, and fixing it makes it worse, even with more epochs during the AE initialization. This
may help counter the vanishing gradient problem in a manner reminiscent of deep belief networks, but further research on 
larger, and more varied data sets with more test runs are necessary.

I feel the need to include the disclaimer that hammering everything with complex models and large deep nets
may not always be optimal, and that this script is a little haphazard in that regard. Compared to some other public SVM 
and random forest based models on the leaderboard, this is exceptionally slow even with GPU acceleration. Time permitting,
I want to explore combining these methods together in a committee/ensemble, as that has ranked well on the leaderboard.

