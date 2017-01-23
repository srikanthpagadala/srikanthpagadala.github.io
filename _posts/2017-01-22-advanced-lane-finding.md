---
layout: post
title: "Advanced Lane Finding"
date: 2017-01-22
categories: ['Computer Vision', 'Robotics']
---

The goal of this project is to detect lane lines on videos through advance techniques such as color transforms, gradients, perspective transform and fitting polynomial.

## Results

The following videos show the final results of the lanes being detected on three different tracks with varying difficulty:

Project Track                 |Challenge Track                |Harder Challenge Track <sup>*</sup>                   
:----------------------------:|:-----------------------------:|:------------------------------:
[![Track 1](/img/project_track.png)](https://youtu.be/9OrWgTO0ZbY) | [![Track 2](/img/challenge_track.png)](https://youtu.be/2cPPiAE76mk) | [![Track 3](/img/harder_challenge_track.png)](https://youtu.be/L_QP8J84Jj8)


The steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.


[Source Code](https://github.com/srikanthpagadala/udacity/tree/master/Self-Driving%20Car%20Engineer%20Nanodegree/AdvancedLaneLines-P4){:target="_blank"}

[Report](https://github.com/srikanthpagadala/udacity/blob/master/Self-Driving%20Car%20Engineer%20Nanodegree/AdvancedLaneLines-P4/README.md){:target="_blank"}



