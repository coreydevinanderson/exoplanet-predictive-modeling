# machine-learning-challenge
Machine learning exercises

### This repository contains predictive models in Python for classifying Exoplanets based on data from the NASA Kepler space telescope.

I used the "kepoi_disposition" as the target. After removing all "CANDIDATE" rows, there were two levels: CONFIRMED (positive) & FALSE POSITIVE (negative).
See "exoplanet_cleaning.ipynb" for a detailed breakdown of how the data were processed prior to export for analyais. 

After cleaning, I built two models using scikit learn and keras:

1. Logistic Regression with LASSO.

2. A deep neural network.

* The results for the logistic regression are curious: high AUC score (0.9982) but low accuracy (0.6523), suggesting good performance in predicting CONFIRMED planets in the test set, but with a high false negative rate.
* The Deep Neural Network did much better, overall: AUC = 0.9964 & accuracy = 0.9523.

It should be noted that many of the features had frequency distributions with severe right skew, and that the logit analysis performed relatively worse because of potential non-linear relationships among the target and predictors. Further work should examine the effects of right-skew and or outliers on the performance of the logit model.

For the logist model, the preferred LASSO regularization hyperparameter was quite large (C = 5), suggesting that there might be a lot of features of small effect that are important in identifying expoplanets.


---

Data were obtained from:

https://www.kaggle.com/nasa/kepler-exoplanet-search-results

Contents:

Source-
exoplanet_data.csv

Data cleaning-
exoplanet_cleaning.ipynb

Cleaned data-
exoplanet_data_cleaned.csv

Logit model-
exo_logit.ipynb

Deep Neural Network-
exo_deep_nn.ipynb
bestModel_exoplanet_dnn_CDA.h5
