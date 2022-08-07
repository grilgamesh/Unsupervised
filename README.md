# Investigating Myopia

## Supervised learning

The data are split into test and train data, and target column separated off. Values are scaled to simplify them for logisitic regression but not for random forest as this is unnecessary. Both models are ran and their overall accuracy scores on the test data are compared.

### Conclusion

Both methods came down with a similar accuracy score: 89.0% for Logistic Regression and 87.1% for the Random Forest. This represents a fairly high confidence rate of predicting Myopia in both cases, but not certainty.

However, The random forest entirely over-fitted the training data, realising 100% accurary. Since it could not replicate this in testing, this is a disadvantage.

The logistic regression model actually performed (negligably) less well on the training data, with 88.8% accuracy. This shows how it had generalised very well from it's training.

Overall,while the two models performed very similarly for this data, I would therefore use the Logistic Regression model, while it was slightly better than the random forest method overall, it did not over-fit the training data, and is therefore more trustworthy.

## Unsupervised learning

Data is read in from csv format to a dataframe, previewed, and then the Myopic column is dropped so as to not bias the data set. The data is then scaled.

A PCA model is initialised and set to reduce the dimensions of the data whilst preserving 90% of the variance. This has the effect of reducing the data from 14 columns to 10.

This reduced data is then fed into the tSNE algorithm, which demonstrates there are now five distinct clusters in the two-dimensional data, which can be seen on a scatter plot.

Then a K-means model is created, and we experimentally find that the elbow point is at k=5 (confirming what we saw in the scatter plot). We then look again at the scatter plot, but coloured by cluster number.

Whilst these clusters are interesting features of the data, they do not appear to correlate with whether a person is myopic, but seem to point to some other under-lying feature of the data that we were not aware of.

## Artificial Neural Network
