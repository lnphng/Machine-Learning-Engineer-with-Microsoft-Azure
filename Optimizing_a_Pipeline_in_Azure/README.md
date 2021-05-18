# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
- construct a pipeline from scikit-learn, using the Azure ML SDK to import data from a URL. 
- use Python SDK to configure a Hyperdrive run for the scikit-learn pipeline, to find the optimal hyperparameters and then to gain a best Scikit-learn model. 
- use the same dataset for an AutoML run to find an optimal model and set of hyperparameters.
- The best Scikit-learn model model is then compared to an Azure AutoML run.

## Summary
The dataset contains data about bank customer data which will be used for a banking marketing project.
Here we want to classify if the customer should be at Yes or No category.
![image](https://user-images.githubusercontent.com/59962526/118719651-0612d700-b829-11eb-8d72-e52a77cf7f5b.png)

## Scikit-learn Pipeline
- Because here is about a binary classification problem so Logistic Regression was chosen to solve this problem.
- As seen from the chart above, we solve this problem with a python script `train.py` which was designed as following:
    - importing the dataset from a url into Azure with `TabularDatasetFactory`
    - cleaning the dataset
    - after preprocessing, using `train_test_split` to split the data into training data and testing data
    - `accuracy` is the metric used to evaluate the model
- the script `train.py` was used in Azure through a SKLearn estimator
- the `hyperdrive_run` was used with `hyperdrive_config` to get the best `accuracy`
