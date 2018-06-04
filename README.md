# Model Stacker Pipeline

## Overview

It is generally observed that the cumulative power of a bunch of models stacked together has a better predictive power than the idividual models. A particular model can outperform another model on some particular data points if not all the data points. Thus taking into account a set of models has a better chance of predicting the final results as an average. A stacker model is trained considering the final predictions of each base model as the training set. Then the prediction is done by applying the base models on the test set and considering the resulting predictions as the test data for the stacker model.   

## Selection of base models

It is not always useful to consider all the base models that are examined. Usually the best performing and least correlated base models are selected. We used 10 single models to individually predict the results. 

The correlations and performances of the single models were explored using the corr-coeff notebook. 

5 best performing and least correlated models ("elasticnet","et","lgb","rf" and "xgb") were selected and stacked together (using stacking.ipnyb notebook) to make the final prediction.

## Repository structure

data: contains the training and the test sets

model: contains the single base models 

corr-coeff: explores the correlations and performances of the base models

submission: stores the submission data for the individual base models

The stacking.ipynb performs the stacking


## Training

The base models were trained individually. A XGBoost regressor model was used as the stacker model. Other models were also considered. The stacker model was tested for overfitting using a cross validation scheme.


