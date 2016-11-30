---
layout: post
title: "Save and Load Keras Deep Learning Models"
date: 2016-11-10
categories: ['Neural Networks']
---

Given that deep learning models can take hours, days and even weeks to train, it is important to know how to save and load them from disk.

Keras separates the concerns of saving your model architecture and saving your model weights.

Model weights are saved to [HDF5 format](http://www.h5py.org/). This is a grid format that is ideal for storing multi-dimensional arrays of numbers.

The model structure can be described and saved using two different formats: JSON and YAML.

Here we are going to save and load your model to file:

- Save Model to JSON.
- Save Model to YAML.

Each example will also save and load your model weights to HDF5 formatted files.

The examples will use the same simple network trained on the Pima Indians onset of diabetes binary classification dataset. This is a small [dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/pima-indians-diabetes/pima-indians-diabetes.data) that contains all numerical data and is easy to work with.

[Source Code](https://github.com/srikanthpagadala/neural-network-projects/tree/master/Save%20and%20Load%20Keras%20Deep%20Learning%20Models){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/neural-network-projects/blob/master/Save%20and%20Load%20Keras%20Deep%20Learning%20Models/report.html){:target="_blank"}

Next: [Using Learning Rate Schedules for Deep Learning Models with Keras](/notes/2016/11/11/using-learning-rate-schedules-for-deep-learning-models-with-keras)
