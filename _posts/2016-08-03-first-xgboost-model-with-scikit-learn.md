---
layout: post
title: "First XGBoost Model with scikit-learn"
date: 2016-08-03
categories: ['Machine Learning']
---

XGBoost is an implementation of gradient boosted decision trees designed for speed and performance that is dominating  machine learning competitions.

For up-to-date instructions for installing XGBoost for Python [see](http://xgboost.readthedocs.io/en/latest/build.html#building-on-osx).

For reference, you can review the XGBoost Python [API](http://xgboost.readthedocs.io/en/latest/python/python_api.html) reference.

We are going to use the Pima Indians onset of diabetes [dataset](https://archive.ics.uci.edu/ml/datasets/Pima+Indians+Diabetes). 

This dataset is comprised of 8 input variables that describe medical details of patients and one output variable to indicate whether the patient will have an onset of diabetes within 5 years.

This is a good dataset for a first XGBoost model because all of the input variables are numeric and the problem is a simple binary classification problem. It is not necessarily a good problem for the XGBoost algorithm because it is a relatively small dataset and an easy problem to model.

[Source Code](https://github.com/srikanthpagadala/machine-learning-projects/tree/master/First%20XGBoost%20Model%20with%20scikit-learn){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/machine-learning-projects/blob/master/First%20XGBoost%20Model%20with%20scikit-learn/report.html){:target="_blank"}

Next: [Data Preparation for Gradient Boosting with XGBoost](/notes/2016/08/04/data-preparation-for-gradient-boosting-with-xgboost)
