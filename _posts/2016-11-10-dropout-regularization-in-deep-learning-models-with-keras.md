---
layout: post
title: "Dropout Regularization in Deep Learning Models with Keras"
date: 2016-11-10
categories: ['Neural Networks']
---

A simple and powerful regularization technique for neural networks and deep learning models is dropout.

Here you will discover the dropout regularization technique and how to apply it to your models in Python with Keras.

- How the dropout regularization technique works?
- How to use dropout on your input layers?
- How to use dropout on your hidden layers?
- How to tune the dropout level on your problem?

## Dropout Regularization For Neural Networks

Dropout is a regularization technique for neural network models. It is a technique where randomly selected neurons are ignored during training. They are “dropped-out” randomly. This means that their contribution to the activation of downstream neurons is temporally removed on the forward pass and any weight updates are not applied to the neuron on the backward pass.

As a neural network learns, neuron weights settle into their context within the network. Weights of neurons are tuned for specific features providing some specialization. Neighboring neurons become to rely on this specialization, which if taken too far can result in a fragile model too specialized to the training data. This reliant on context for a neuron during training is referred to complex co-adaptations.

You can imagine that if neurons are randomly dropped out of the network during training, that other neurons will have to step in and handle the representation required to make predictions for the missing neurons. This is believed to result in multiple independent internal representations being learned by the network.

The effect is that the network becomes less sensitive to the specific weights of neurons. This in turn results in a network that is capable of better generalization and is less likely to overfit the training data.

[Source Code](https://github.com/srikanthpagadala/neural-network-projects/tree/master/Dropout%20Regularization%20in%20Deep%20Learning%20Models%20with%20Keras){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/neural-network-projects/blob/master/Dropout%20Regularization%20in%20Deep%20Learning%20Models%20with%20Keras/report.html){:target="_blank"}

Next: [Save and Load Keras Deep Learning Models](/notes/2016/11/10/save-and-load-keras-models)
