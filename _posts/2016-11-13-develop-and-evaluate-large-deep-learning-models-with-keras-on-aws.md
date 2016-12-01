---
layout: post
title: "Develop and Evaluate Large Deep Learning Models with Keras on AWS"
date: 2016-11-13
categories: ['Setup & Environment']
---

Large deep learning models require a lot of compute time to run. You can run them on your CPU but it can take hours or days to get a result. If you have access to a GPU on your desktop, you can drastically speed up the training time of your deep learning models.

In this post, you will discover how you can get access to GPUs to speed up the training of your deep learning models by using the Amazon Web Service (AWS) infrastructure. For less than a dollar per hour and often a lot cheaper you can use this service from your workstation or laptop.

### OS - Ubuntu

I highly recommend sticking with latest version of Ubuntu Linux as OS for Neural Networks with Keras. I ran into lot of issues with Red Hat when pushing limits of MultiThreaded and Multiprocess programs.

### EC2 Instance Types

- **Compute Optimized:** Type: c3.8xlarge. vCPU: 32. Memory: 60GB
- **GPU Instances:** Type: g2.2xlarge. vCPU: 8. Memory: 15GB

As of this writing, Google Cloud Platform does not offer on-demand GPU instances. So Amazon is only reliable viable option. Unfortunately, on AWS not everybody has access by default to launch GPU instances. You may have to put in a request with AWS customer support to get access. If you don't have the access, AWS console will prompt you to fill in a form when you try to launch a GPU instance.

### Software Installation

1. Install Anaconda per instructions [here](https://docs.continuum.io/anaconda/install#linux-install)
2. Installation instructions for [Theano](http://deeplearning.net/software/theano/install_ubuntu.html#install-ubuntu)
3. Installation instructions for [TensorFlow](https://www.tensorflow.org/versions/r0.12/get_started/os_setup.html#anaconda-installation)

### Configure Theano

Update your configuration of Theano (the Keras backend) to always use the GPU.

```
vi ~/.theanorc
```

Copy and paste the following configuration and save the file:

```
[global]
device = gpu
floatX = float32
optimizer_including = cudnn
allow_gc = False

[lib]
cnmem=.95
```

### Configure TensorFlow

TensorFlow will automatically switch to using GPU if it detects one provided all the appropriate NVIDIA cuda drivers are correctly installed. There is nothing to configure.

### Docker installation

For Tensorflow I highly recommend using Docker images. It will save a lot of time in setup. Since you are paying for instances per minute, I like not to waste time in setup. This benefit is more evident when using Tensorflow with GPU. Docker based installation instructions are [here](https://www.tensorflow.org/versions/r0.12/get_started/os_setup.html#docker-installation).

### Running Jupyter remotely

By default the notebook server only listens on the localhost/127.0.0.1 network interface. If you want to connect to the notebook from another computers, or over the internet, you need to configure the notebook server to listen on all network interfaces and not open the browser. You will often also want to disable the automatic launching of the web browser.

```
jupyter notebook --ip=* --no-browser
```
### Docker cleanup

Delete all containers

```
docker rm $(docker ps -a -q)
```

Delete all images

```
docker rmi $(docker images -q)
```


Next: [Deep Learning on Apache Spark](/notes/2016/11/20/deep-learning-on-apache-spark)
