---
layout: post
title: "What is deep learning?"
date: 2016-11-03
categories: ['Neural Networks']
---

Deep Learning is a subfield of machine learning concerned with algorithms inspired by the structure and function of the brain called artificial neural networks.

Deep Learning networks are distinguished from the more commonplace single-hidden-layer neural networks by their depth; that is, the number of node layers through which data passes in a multistep process of pattern recognition.

Traditional machine learning relies on shallow nets, composed of one input and one output layer, and at most one hidden layer in between. More than three layers (including input and output) qualifies as "deep" learning. So deep is a strictly defined, technical term that means more than one hidden layer.

In Deep Learning networks, each layer of nodes trains on a distinct set of features based on the previous layer’s output. The further you advance into the neural net, the more complex the features your nodes can recognize, since they aggregate and recombine features from the previous layer. 

This is known as feature hierarchy, and it is a hierarchy of increasing complexity and abstraction. It makes deep-learning networks capable of handling very large, high-dimensional data sets with billions of parameters that pass through nonlinear functions.

Above all, these nets are capable of discovering latent structures within unlabeled, unstructured data, which is the vast majority of data in the world. For me following figure captures the intuition well.

![Deep Neural Network](/img/deep_nn.png)

### Deep Learning Textbook

[Deep Learning](http://www.deeplearningbook.org/) by top deep learning scientists Ian Goodfellow, Yoshua Bengio and Aaron Courville is the staple text to read in the field.

Next: [Deep Learning with Keras](/notes/2016/11/04/deep-learning-with-keras)

