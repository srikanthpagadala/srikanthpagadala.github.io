---
layout: post
title: "Display Deep Learning Model Training History in Keras"
date: 2016-11-10
categories: ['Neural Networks']
---

You can learn a lot about neural networks and deep learning models by observing their performance over time during training.

Here you will discover how you can review and visualize the performance of deep learning models over time during training in Python with Keras.

## Access Model Training History in Keras

Keras provides the capability to register callbacks when training a deep learning model.

One of the default callbacks that is registered when training all deep learning models is the History callback. It records training metrics for each epoch. This includes the loss and the accuracy (for classification problems) as well as the loss and accuracy for the validation dataset, if one is set.

The history object is returned from calls to the fit() function used to train the model. Metrics are stored in a dictionary in the history member of the object returned.


[Source Code](https://github.com/srikanthpagadala/neural-network-projects/tree/master/Display%20Deep%20Learning%20Model%20Training%20History%20in%20Keras){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/neural-network-projects/blob/master/Display%20Deep%20Learning%20Model%20Training%20History%20in%20Keras/report.html){:target="_blank"}

Next: [Dropout Regularization in Deep Learning Models with Keras](/notes/2016/11/10/dropout-regularization-in-deep-learning-models-with-keras)
