---
layout: post
title: "Using Learning Rate Schedules for Deep Learning Models with Keras"
date: 2016-11-11
categories: ['Neural Networks']
---

Training a neural network or large deep learning model is a difficult optimization task.

The classical algorithm to train neural networks is called stochastic gradient descent. It has been well established that you can achieve increased performance and faster training on some problems by using a learning rate that changes during training.

Let us learn how you can use different learning rate schedules for your neural network models using the Keras deep learning library. 

- How to configure and evaluate a time-based learning rate schedule?
- How to configure and evaluate a drop-based learning rate schedule?

## Learning Rate Schedule For Training Models


Adapting the learning rate for your stochastic gradient descent optimization procedure can increase performance and reduce training time.

Sometimes this is called learning rate annealing or adaptive learning rates. Here we will call this approach a learning rate schedule, were the default schedule is to use a constant learning rate to update network weights for each training epoch.

The simplest and perhaps most used adaptation of learning rate during training are techniques that reduce the learning rate over time. These have the benefit of making large changes at the beginning of the training procedure when larger learning rate values are used, and decreasing the learning rate such that a smaller rate and therefore smaller training updates are made to weights later in the training procedure.

This has the effect of quickly learning good weights early and fine tuning them later.

Two popular and easy to use learning rate schedules are as follows:

- Decrease the learning rate gradually based on the epoch.
- Decrease the learning rate using punctuated large drops at specific epochs.


[Source Code](https://github.com/srikanthpagadala/neural-network-projects/tree/master/Using%20Learning%20Rate%20Schedules%20for%20Deep%20Learning%20Models%20with%20Keras){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/neural-network-projects/blob/master/Using%20Learning%20Rate%20Schedules%20for%20Deep%20Learning%20Models%20with%20Keras/report.html){:target="_blank"}

Next: [What is Recurrent Neural Networks?](/notes/2016/11/12/what-is-recurrent-neural-networks)
