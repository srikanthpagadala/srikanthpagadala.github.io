---
layout: post
title: "Vehicle Detection and Tracking"
date: 2017-02-23
categories: ['Computer Vision', 'Robotics']
---

In this project, the goal is to write a software pipeline to detect vehicles in a video.  

## Results

The following videos show the final results of the vehicles being detected on two different tracks with varying difficulty:

Project Track                 |Challenge Track                                   
:----------------------------:|:-----------------------------:
[![Track 1](/img/project_track_dt.png)](https://youtu.be/x8kqF5M8idc) | [![Track 2](/img/challenge_track_dt.png)](https://youtu.be/MnQ2CQFppB4) 


The steps of this project are the following:

* Perform a Histogram of Oriented Gradients (HOG) feature extraction on a labeled training set of images and train a classifier Linear SVM classifier
* Apply a color transform and append binned color features, as well as histograms of color, to your HOG feature vector. 
* Normalize features and randomize a selection for training and testing.
* Implement a sliding-window technique and use trained classifier to search for vehicles in images.
* Run pipeline on a video stream and create a heat map of recurring detections frame by frame to reject outliers and follow detected vehicles.
* Estimate a bounding box for vehicles detected.

[Source Code](https://github.com/srikanthpagadala/udacity/tree/master/Self-Driving%20Car%20Engineer%20Nanodegree/VehicleDetectionTracking-P5){:target="_blank"}

[Report](https://github.com/srikanthpagadala/udacity/blob/master/Self-Driving%20Car%20Engineer%20Nanodegree/VehicleDetectionTracking-P5/README.md){:target="_blank"}



