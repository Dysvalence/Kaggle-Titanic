Kaggle-Titanic

Building a classifier on the Titanic survival dataset on Kaggle.

One-hot encoded some features, basic imputation, and normalization, followed by a deep NN using Keras+Theano.

Somewhat overkill compared to simpler models, but with more advanced imputation this may wind up being better.
A major limiting factor is the lack of validation data, I tried splitting off 91 of 891 at random but accuracy suffered a bit too much.

TODO:

-More advanced imputation on age; use name and cabin data

-Use pandas

-Transfer notes from the comments

-Clean up some of the sanity checks

-fix duplicate CSVs
