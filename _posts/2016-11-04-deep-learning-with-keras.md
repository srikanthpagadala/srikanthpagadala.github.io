---
layout: post
title: "Deep Learning with Keras"
date: 2016-11-04
categories: ['Neural Networks']
---

### What is Keras?

Two of the top numerical platforms in Python that provide the basis for Deep Learning research and development are [Theano](http://deeplearning.net/software/theano/) and [TensorFlow](https://www.tensorflow.org/).

Both are very powerful libraries, but both can be difficult to use directly for creating deep learning models.

[Keras](https://keras.io/) Python library provides a clean and convenient way to create a range of deep learning models on top of Theano or TensorFlow.

### Installing Keras

Follow the installation [instructions](https://keras.io/#installation) on Keras website

### Deep Learning with Keras

Programming API of Keras is similar to sklearn. The focus of Keras is the idea of a model.

The main type of model is called a Sequence which is a linear stack of layers.

You create a sequence and add layers to it in the order that you wish for the computation to be performed.

Once defined, you compile the model which makes use of the underlying framework to optimize the computation to be performed by your model. In this you can specify the loss function and the optimizer to be used.

Once compiled, the model must be fit to data. This can be done one batch of data at a time or by firing off the entire model training regime. This is where all the compute happens.

Once trained, you can use your model to make predictions on new data. 

Next: [Life-Cycle for Neural Network Models in Keras](/notes/2016/11/05/life-cycle-for-neural-network-models-in-keras)

