# Arya.ai Assignment - Data Scientist
### This repository contains a jupyter notebook file and a readme file that explains each step performed in the notebook for the completion of the assignment.

## Problem statement
Binary Classification problem - To do an exploratory analysis of the dataset provided, decide on feature selection, preprocessing before training a model to classify as class '0' or class '1'.

## Data
1. training_set.csv - To be used as training and validation set - 3910 records, 57 features, 1 output
2. test_set.csv (without Ground Truth) - 691 records, 57 features

## Solution
- Data visualisation and EDA may be excellent complimentary tools for the feature selection process and can be used in the following ways:
  1. Univariate Analysis: Histograms and bar charts make it easier to see the distribution and variance of each variable.
  2. Correlation Analysis: The use of a heatmap makes it easier to find explanatory factors that are highly associated and reduces collinearity.
  3. Bivariate Analysis: Box plots and grouped bar charts make it easier to see how the explanatory factors and the response variable are related.

(to get a better understanding of the data, eda can be performed before data transformation)

- Feature selection is done to find the optimal set of features for building practical models of the phenomena being studied. Two methods are widely used for feature selection:
  1. Filter methods
  2. Wrapper methods

- In this, the filter method is used because they evaluate the feature importance based on statistical tests such as Chi-Square, ANOVA, etc. In order to develop a feature selection model, SelectKBest() method is used and particular information on which scoring algorithms to use, and how many variables to use are passed to the method to find the best parameters. The full feature selection process with following steps:
  1. Importing Libraries
  2. Design a feature selection model based on two parameters: variable counts (ranging from 1 to all features) and score function (chi-square, anova, and mutual information are used here).
  3. Train a Logistic Regression model with selected features
  4. Find the accuracy score on the validation set
### Select the best features based on the accuracy score on different score functions.

## Data preprocessing
Before being fed into a classification model, it is advised to normalize the data. Normalization is done using sklearn library. After normalization, the whole training dataset is divided into train and validation split using test_train_split by a factor of 4:1.

## Classification model
A simple Logistic regression model is used for the problem as it provides very good result in case of binary classification. Though other models like KNN, SVM, and Neural networks can also be considered but they will require further tuning as compared to Logistic Regression.
The Logistic regression model is trained on the train set and validated/tested on the validation set. Accuracy score, Confusion matrix, and classification report are used to check the performance of the model on the validation set.

## Test
The test data provided in the file is loaded and a copy of it is created. The copy is then selected as for the prediction process involving following steps:
  1. Features selected for feature selection and EDA process are used and other columns are dropped from the copy of the test data
  2. Normalization is done on the features
  3. Model prediction are calculated and the result is then concatenated on the original test data.
