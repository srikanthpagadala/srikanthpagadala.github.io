---
layout: post
title: "Check-Point Deep Learning Models in Keras"
date: 2016-11-10
categories: ['Neural Networks']
---

Deep learning models can take hours, days or even weeks to train.

If the run is stopped unexpectedly, you can lose a lot of work.

Let us find out how you can check-point your deep learning models during training in Python using the Keras library.

## Checkpointing Neural Network Models

Application checkpointing is a fault tolerance technique for long running processes.

It is an approach where a snapshot of the state of the system is taken in case of system failure. If there is a problem, not all is lost. The checkpoint may be used directly, or used as the starting point for a new run, picking up where it left off.

When training deep learning models, the checkpoint is the weights of the model. These weights can be used to make predictions as is, or used as the basis for ongoing training.

The Keras library provides a checkpointing capability by a callback API.

The ModelCheckpoint callback class allows you to define where to checkpoint the model weights, how the file should named and under what circumstances to make a checkpoint of the model.

The API allows you to specify which metric to monitor, such as loss or accuracy on the training or validation dataset. You can specify whether to look for an improvement in maximizing or minimizing the score. Finally, the filename that you use to store the weights can include variables like the epoch number or metric.

The ModelCheckpoint can then be passed to the training process when calling the fit() function on the model.

Note, you may need to install the h5py library to output network weights in HDF5 format.

[Source Code](https://github.com/srikanthpagadala/neural-network-projects/tree/master/Check-Point%20Deep%20Learning%20Models%20in%20Keras){:target="_blank"}

[Report](http://htmlpreview.github.io/?https://github.com/srikanthpagadala/neural-network-projects/blob/master/Check-Point%20Deep%20Learning%20Models%20in%20Keras/report.html){:target="_blank"}

Next: [Display Deep Learning Model Training History in Keras](/notes/2016/11/10/display-deep-learning-model-training-history-in-keras)
