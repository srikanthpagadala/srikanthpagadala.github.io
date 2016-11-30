---
layout: post
title: "Object Recognition in CIFAR-10 with Convolutional Neural Networks"
date: 2016-11-07
categories: ['Neural Networks']
---

A difficult problem where traditional neural networks fall down is called object recognition. It is where a model is able to identify the objects in images.

Let us learn how to develop and evaluate deep learning models for object recognition in Keras. 

By the end you will know:

- About the CIFAR-10 object recognition dataset and how to load and use it in Keras.
- How to create a simple Convolutional Neural Network for object recognition?
- How to lift performance by creating deeper Convolutional Neural Networks?

## The CIFAR-10 Problem Description

The problem of automatically identifying objects in photographs is difficult because of the near infinite number of permutations of objects, positions, lighting and so on. It’s a really hard problem.

This is a well studied problem in computer vision and more recently an important demonstration of the capability of deep learning. A standard computer vision and deep learning dataset for this problem was developed by the Canadian Institute for Advanced Research (CIFAR).

The CIFAR-10 dataset consists of 60,000 photos divided into 10 classes (hence the name CIFAR-10). Classes include common objects such as airplanes, automobiles, birds, cats and so on. The dataset is split in a standard way, where 50,000 images are used for training a model and the remaining 10,000 for evaluating its performance.

The photos are in color with red, green and blue components, but are small measuring 32 by 32 pixel squares.

State of the art results are achieved using very large Convolutional Neural networks. Model performance is reported in classification accuracy, with very good performance above 90% with human performance on the problem at 94% and state-of-the-art results at 96% at the time of writing.

[Source Code](https://github.com/srikanthpagadala/neural-network-projects/tree/master/Object%20Recognition%20in%20CIFAR-10%20with%20Convolutional%20Neural%20Networks){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/neural-network-projects/blob/master/Object%20Recognition%20in%20CIFAR-10%20with%20Convolutional%20Neural%20Networks/report.html){:target="_blank"}

Next: [Predict Sentiment From Movie Reviews](/notes/2016/11/09/predict-sentiment-from-movie-reviews)

