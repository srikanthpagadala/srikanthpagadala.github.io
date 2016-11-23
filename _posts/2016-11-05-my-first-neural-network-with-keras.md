---
layout: post
title: "My first Neural Network with Keras"
date: 2016-11-05
categories: ['Neural Networks']
---

[Keras](https://keras.io/) makes working with Neural Networks consistent with sklearn API. 

Steps involved are:

- Load Data
- Define Model
- Compile Model
- Fit Model
- Make Predictions
- Evaluate Model

I have used the Pima Indians onset of diabetes [dataset](http://archive.ics.uci.edu/ml/datasets/Pima+Indians+Diabetes). This is a standard machine learning dataset from the UCI Machine Learning repository. It describes patient medical record data for Pima Indians and whether they had an onset of diabetes within five years.

As such, it is a binary classification problem (onset of diabetes as 1 or not as 0). All of the input variables that describe each patient are numerical. This makes it easy to use directly with neural networks that expect numerical input and output values, and ideal for our first neural network in Keras.

[Source Code](https://github.com/srikanthpagadala/neural-network-projects/tree/master/My%20first%20Neural%20Network%20with%20Keras){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/neural-network-projects/blob/master/My%20first%20Neural%20Network%20with%20Keras/report.html){:target="_blank"}

Next: [Multi-Class Classification with Keras](/notes/2016/11/06/multi-class-classification-keras)


