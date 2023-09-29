# Bulldozer-price-prediction

This is a project from a Kaggle competition.

> How well can we predict the future sale price of a bulldozer, given its characteristics and previous examples of how much similar bulldozers have been sold for?

The data is downloaded from the Kaggle Bluebook for Bulldozers competition: https://www.kaggle.com/c/bluebook-for-bulldozers/overview

There are 3 main datasets:

* Train.csv is the training set, which contains data through the end of 2011.
* Valid.csv is the validation set, which contains data from January 1, 2012 - April 30, 2012 You make predictions on this set throughout the majority of the competition. Your score on this set is used to create the public leaderboard.
* Test.csv is the test set, which won't be released until the last week of the competition. It contains data from May 1, 2012 - November 2012. Your score on the test set determines your final rank for the competition.

The evaluation metric for this competition is the RMSLE (root mean squared log error) between the actual and predicted auction prices.

For more on the evaluation of this project check:
https://www.kaggle.com/competitions/bluebook-for-bulldozers/overview/evaluation

**Note:** the goal for most regression evaluation metrics is to minimize the error. For example, our goal for this project will be to build a machine learning model which minimises RMSLE.

Kaggle provides a data dictionary detailing all of the features of the dataset. You can view this data dictionary in the data folder (data/bluebook-for-bulldozers/Data Dictionary.xlsx)

## How to run the project.

1. Download the documents in the repository or do a git pull.
2. Exctract the files from the bluebook-for-bulldozers.zip inside the data folder.
3. Create a Python environment.
4. Run the end-to-end-bulldozer-price-regression notebook.
5. Optional, run the project-organized notebook.

## Conclusions.
In the end-to-end-bulldozer-price-regression notebook we obtain a 0.24 RMSLE in the validation, in comparison to the project-organized notebook, where we obtain a 0.47 RMSLE in the validation.

We have this huge difference because in the first notebook we made the preprocessing of the training and validation data before splitting the dataset, which is the wrong way to do it.

It is necessary to split the training and validation data before doing the preprocessing in order to not mix past and future data.

So in the project-organized notebook we split training and validation first and then we preprocess, fixing this mistake, at the end we obtain a model that gives more realistic results (0.47 RMSLE) and we can continue doing research and experimentation to improve our results.