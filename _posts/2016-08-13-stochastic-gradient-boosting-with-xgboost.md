---
layout: post
title: "Stochastic Gradient Boosting with XGBoost"
date: 2016-08-13
categories: ['Machine Learning']
---

A simple technique for ensembling decision trees involves training trees on subsamples of the training dataset.

Subsets of the rows in the training data can be taken to train individual trees called bagging. When subsets of rows of the training data are also taken when calculating each split point, this is called random forest.

These techniques can also be used in the gradient tree boosting model in a technique called stochastic gradient boosting.

Here you will discover stochastic gradient boosting and how to tune the sampling parameters using XGBoost with scikit-learn in Python.

By the end you will know:

- The rationale behind training trees on subsamples of data and how this can be used in gradient boosting.
- How to tune row-based subsampling in XGBoost using scikit-learn?
- How to tune column-based subsampling by both tree and split-point in XGBoost?

[Source Code](https://github.com/srikanthpagadala/machine-learning-projects/tree/master/Stochastic%20Gradient%20Boosting%20with%20XGBoost%20){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/machine-learning-projects/blob/master/Stochastic%20Gradient%20Boosting%20with%20XGBoost%20/report.html){:target="_blank"}

