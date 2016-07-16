Kaggle-Titanic

Building a classifier on the Titanic survival dataset on Kaggle.

One-hot encoded some features, basic imputation, and normalization, followed by a deep NN using Keras+Theano.

Age is now imputed using a NN regression, and honorific title data has been extracted from names.

Somewhat overkill compared to simpler models, but with more advanced imputation this may wind up being better.
A major limiting factor is the lack of validation data, I tried splitting off 91 of 891 at random but accuracy suffered a bit too much.


TODO:
-Use cabin data and more name data
-Clean up some of the sanity checks
-Use a better regression for age
-Add comments to the pandas rewrite
