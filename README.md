# Project 2 - Ames Housing Data and Kaggle Challenge #

**********

## Problem Statement ##

Demonstrate use of different linear regression techniques analysing Ames, IA housing data set. With necessary assumptions being made, analyze various linear regression methods performance, identify the best performing model and evaluate its performance. While working on project participate in group challenge at __[Kaggle](https://www.kaggle.com)__ testing the model performance on a testing data sets with unknown target values. 

**********
## Project Files ##

The project consists of two separate Jupyter Notebooks listed in the order of their workflow sequence and available at the __[code](http://localhost:8889/tree/code)__ folder in the Project repository:

1. __[Data Cleaning and Feature Engineering](http://localhost:8888/notebooks/code/Data%20Cleaning%20and%20Feature%20Engineering.ipynb)__
2. __[EDA and Modeling](http://localhost:8888/notebooks/code/EDA%20and%20Modeling.ipynb)__

Datasets used for the Project and generated through the Project are available at the __[datasets](http://localhost:8889/tree/datasets)__ folder in the Projects repository.


**********
## Data Dictionary ##

__[Data description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)__ is available on the Internet. 

**********
## Executive Summary ##

Analyzing the initial dataset with 70+ categories for each of nearly 3000 sales I decided to explre, clean and pre-process the training and testing datasets together for the coherence purposes and future modeling convenience. Having excluded certain categories as having little practical information, repeating information from other categories and being insignificant for house sale price formation, I started analyzing the remaining data for correlation with sales price. I picked for future analysis a list of possible predictors ('extended predictors list') defined as categories having a correlation with sale price of more than 0.2 by absolute value. 

Through column-by-column analysis I came to uniting some columns, engineering new ones and dropping some of extended predictors list elements, highly correlated with the remaining ones. As a result, I received a list of future predictors used for linear regression predictive models ('filtered predictors list').

I used simple Multilinear Regression Model (MLR) on both filtered predictors list, evaluated the results by using R2 -score (Root Mean Square Error) criteria, and received quite fair results. Then I decided to compare the result with using the extended predictors list (highly muti-correlated between each other), as well as experimented with polynomial features, power transformations of model imputs,  Ridge, Lasso and ElasticNet regression models (with and without hyperparameters tuning).


**********
## Conclusions and Recommendations ##

### Conclusions: ###

- Model with the highest R2 score of 0.8862282042918339 is a Lasso regression model fitted with a multitude of original predictors each having an absolute correlation with the target value of no less than 0.2
- When evaluating this model using train-test-split procedure we received a R2 score of 0.8919182595384318 for the training set and a R2 score of 0.8633694221761542 for a testing set, which indicates a well-balanced model and gives a hope the model will work well on unknown data
- Still, Kaggle predictions on a set of unknown data have a quite high RMSE which most probably results from two things:
    - Initial assumptions while possible predictors analysis/choice
    - Quite high level of multicollinearity between chosen predictors
    
### Recommendations: ###

Since this is a learning project, and the results achieved make some sense and are quite easily interpretable and explainable, this model can be improved by using other combination of predictors, as well as we still have an option of increasing their number - which is quite an endless process by its nature and definition.


**********
## Source Documentation ##

Images used in Project Presentation are sourced at __[Wikimedia Commons](https://commons.wikimedia.org/wiki/Main_Page)__ and are copyright-free.
