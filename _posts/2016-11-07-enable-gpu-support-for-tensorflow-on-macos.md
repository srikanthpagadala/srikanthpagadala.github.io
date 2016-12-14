---
layout: post
title: "Enable GPU support for Tensorflow on Mac OS X"
date: 2016-11-07
categories: ['Setup & Environment']
---

As soon as I started working on relatively serious Deep Neural Networks such as [Handwritten Digit Recognition](/notes/2016/11/07/handwritten-digit-recognition-using-convolutional-neural-networks) or [Object Recognition in CIFAR-10](/notes/2016/11/07/object-recognition-in-cifar10-with-convolutional-neural-networks), I realized that my 3 year old MacBook's CPU is not enough. It took 9 hrs to complete Handwritten Digit Recognition project on my below laptop. 

<pre>
Model Name: MacBook Pro (Retina, Mid 2012)
Model Identifier: MacBookPro10,1
Processor Name:	Intel Core i7
Processor Speed: 2.7 GHz
Number of Processors: 1
Total Number of Cores: 4
L2 Cache (per Core): 256 KB
L3 Cache: 8 MB
Memory: 16 GB
OS Version: macOS Sierra, 10.12.1

Graphics Cards:
 Intel HD Graphics 4000
 NVIDIA GeForce GT 650M
</pre>

Obvious solution is to put GPUs of my laptop to use. 

As of this writting, official [instructions](https://www.tensorflow.org/versions/r0.12/get_started/os_setup.html#prepare-environment-for-mac-os-x) for setting up GPU environment for Tensorflow on Mac OS X are bit dated. Hence this blog post. Let us get started.

## Update: Official Tensorflow [instructions](https://www.tensorflow.org/get_started/os_setup#optional-setup-gpu-for-mac) are upto date now. Please follow official instructions. It easy to install binary package for tensorflow-gpu for mac. Below instructions are still good, if you want to install from sources.

## Prerequisites

Make sure to update your homebrew formulas


```bash
brew update
```

Coreutils for Mac OS X.

```bash
brew install coreutils swig 
```

Install Bazel

```bash
brew install bazel
```

Cuda Libraries for macosx. You can install cuda from homebrew using cask.

```bash
brew cask install cuda
```

Make sure that the installed cuda version is 8.0 (latest, as of this writing) you can check the version with

```bash
brew cask info cuda
```

```
cuda: 8.0.55
https://developer.nvidia.com/cuda-zone
/usr/local/Caskroom/cuda/8.0.55 (23 files, 1.3G)
From: https://github.com/caskroom/homebrew-cask/blob/master/Casks/cuda.rb
==> Name
Nvidia CUDA
==> Artifacts
```

You need NVIDIA's Cuda Neural Network library libCudnn. You have to register and download it from the [website](https://developer.nvidia.com/cudnn).

Download the file: cudnn-8.0-osx-x64-v5.1-tgz
 
Once downloaded you need to manually copy the files over the /usr/local/cuda/ directory

```bash
tar xzvf ~/Downloads/cudnn-8.0-osx-x64-v5.1-tgz
sudo mv -v cuda/lib/libcudnn* /usr/local/cuda/lib
sudo mv -v cuda/include/cudnn.h /usr/local/cuda/include
```

add in your ~/.bash_profile the reference to /usr/local/cuda/lib. You will need it to run the python scripts.

```bash
export DYLD_LIBRARY_PATH=/usr/local/cuda/lib:$DYLD_LIBRARY_PATH
```

Now let's make sure that we are able to compile cuda programs. If you have the latest Xcode Installed (8.2 as the time of this post) nvcc will not work and will give an error like:

```bash
nvcc fatal : The version ('70300') of the host compiler ('Apple clang') is not supported
```

In order to fix this you need to:

1. download Xcode 7.2.1 from the apple developer [website](https://developer.apple.com/download/more/)
2. create a new directory /Applications/XCode7.2.1/
3. copy the entire XCode.App inside /Applications/XCode7.2.1
4. run sudo xcode-select -s /Applications/XCode7.2.1/Xcode.app/

You should be able to compile the deviceQuery utility found inside the cuda sdk repository. Let's compile the deviceQuery utility to figure out the CUDA_CAPABILITY supported by our graphics card.

```bash
cd /usr/local/cuda/samples
sudo make -C 1_Utilities/deviceQuery
```

And now we run it:

```bash
cd /usr/local/cuda/samples/
./bin/x86_64/darwin/release/deviceQuery
```

The output will look like:

```bash
./bin/x86_64/darwin/release/deviceQuery Starting...

 CUDA Device Query (Runtime API) version (CUDART static linking)

Detected 1 CUDA Capable device(s)

Device 0: "GeForce GT 650M"
  CUDA Driver Version / Runtime Version          8.0 / 8.0
  CUDA Capability Major/Minor version number:    3.0
  Total amount of global memory:                 1024 MBytes (1073414144 bytes)
  ( 2) Multiprocessors, (192) CUDA Cores/MP:     384 CUDA Cores
  GPU Max Clock rate:                            900 MHz (0.90 GHz)
  Memory Clock rate:                             2508 Mhz
  Memory Bus Width:                              128-bit
  L2 Cache Size:                                 262144 bytes
  Maximum Texture Dimension Size (x,y,z)         1D=(65536), 2D=(65536, 65536), 3D=(4096, 4096, 4096)
  Maximum Layered 1D Texture Size, (num) layers  1D=(16384), 2048 layers
  Maximum Layered 2D Texture Size, (num) layers  2D=(16384, 16384), 2048 layers
  Total amount of constant memory:               65536 bytes
  Total amount of shared memory per block:       49152 bytes
  Total number of registers available per block: 65536
  Warp size:                                     32
  Maximum number of threads per multiprocessor:  2048
  Maximum number of threads per block:           1024
  Max dimension size of a thread block (x,y,z): (1024, 1024, 64)
  Max dimension size of a grid size    (x,y,z): (2147483647, 65535, 65535)
  Maximum memory pitch:                          2147483647 bytes
  Texture alignment:                             512 bytes
  Concurrent copy and kernel execution:          Yes with 1 copy engine(s)
  Run time limit on kernels:                     Yes
  Integrated GPU sharing Host Memory:            No
  Support host page-locked memory mapping:       Yes
  Alignment requirement for Surfaces:            Yes
  Device has ECC support:                        Disabled
  Device supports Unified Addressing (UVA):      Yes
  Device PCI Domain ID / Bus ID / location ID:   0 / 1 / 0
  Compute Mode:
     < Default (multiple host threads can use ::cudaSetDevice() with device simultaneously) >

deviceQuery, CUDA Driver = CUDART, CUDA Driver Version = 8.0, CUDA Runtime Version = 8.0, NumDevs = 1, Device0 = GeForce GT 650M
Result = PASS
```

Here you can confirm that the driver is set to 8.0 and you can find also the cuda capability of your GPU, CUDA Capability Major/Minor version number: 3.0 in my case, so we can set this property when we configure tensorflow.

## Checkout tensorflow

```bash
git clone --recurse-submodules https://github.com/tensorflow/tensorflow
cd tensorflow
git checkout master
```

Then we need to configure it.

I use Anaconda for the python distribution. Notice that you need to set the right TF_CUDA_COMPUTE_CAPABILITES value from the previous deviceQuery operation.

```bash
PYTHON_BIN_PATH=$HOME/anaconda/bin/python CUDA_TOOLKIT_PATH="/usr/local/cuda" CUDNN_INSTALL_PATH="/usr/local/cuda" TF_UNOFFICIAL_SETTING=1 TF_NEED_CUDA=1 TF_CUDA_COMPUTE_CAPABILITIES="3.0" TF_CUDNN_VERSION="5" TF_CUDA_VERSION="8.0" TF_CUDA_VERSION_TOOLKIT=8.0 ./configure
```

Now we are ready to build tensorflow pip package. This may take a while.

```bash
bazel build -c opt --config=cuda //tensorflow/tools/pip_package:build_pip_package
bazel-bin/tensorflow/tools/pip_package/build_pip_package /tmp/tensorflow_pkg
pip install --upgrade --ignore-installed  /tmp/tensorflow_pkg/tensorflow-*.whl
```
**Problem 1 - Missing Files**

If needed create symlinks for missing files:

```
sudo ln -s libcudnn.5.dylib libcudnn.5
sudo ln -s libcudnn.5.dylib libcudnn.dylib
sudo ln -s libcudnn.5.dylib libcudnn5.dylib
```

**Problem 2 - Library not loaded: @rpath/libcudart.**

file "touch" solution described [here](https://github.com/tensorflow/tensorflow/issues/4187) worked for me.

Now move to another directory and run a test script:

```
import tensorflow as tf

# Creates a graph.
a = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[2, 3], name='a')
b = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[3, 2], name='b')
c = tf.matmul(a, b)

# Creates a session with log_device_placement set to True.
sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))

# Runs the op.
print sess.run(c)
```

You should see output like this. You can see that Tensorflow has automatically started using GPU.

```
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcublas.8.0.dylib locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcudnn.5.dylib locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcufft.8.0.dylib locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcuda.1.dylib locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcurand.8.0.dylib locally
I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:901] OS X does not support NUMA - returning NUMA node zero
I tensorflow/core/common_runtime/gpu/gpu_device.cc:885] Found device 0 with properties: 
name: GeForce GT 650M
major: 3 minor: 0 memoryClockRate (GHz) 0.9
pciBusID 0000:01:00.0
Total memory: 1023.69MiB
Free memory: 688.47MiB
I tensorflow/core/common_runtime/gpu/gpu_device.cc:906] DMA: 0 
I tensorflow/core/common_runtime/gpu/gpu_device.cc:916] 0:   Y 
I tensorflow/core/common_runtime/gpu/gpu_device.cc:975] Creating TensorFlow device (/gpu:0) -> (device: 0, name: GeForce GT 650M, pci bus id: 0000:01:00.0)
Device mapping:
/job:localhost/replica:0/task:0/gpu:0 -> device: 0, name: GeForce GT 650M, pci bus id: 0000:01:00.0
I tensorflow/core/common_runtime/direct_session.cc:255] Device mapping:
/job:localhost/replica:0/task:0/gpu:0 -> device: 0, name: GeForce GT 650M, pci bus id: 0000:01:00.0

MatMul: (MatMul): /job:localhost/replica:0/task:0/gpu:0
I tensorflow/core/common_runtime/simple_placer.cc:827] MatMul: (MatMul)/job:localhost/replica:0/task:0/gpu:0
b: (Const): /job:localhost/replica:0/task:0/gpu:0
I tensorflow/core/common_runtime/simple_placer.cc:827] b: (Const)/job:localhost/replica:0/task:0/gpu:0
a: (Const): /job:localhost/replica:0/task:0/gpu:0
I tensorflow/core/common_runtime/simple_placer.cc:827] a: (Const)/job:localhost/replica:0/task:0/gpu:0
[[ 22.  28.]
 [ 49.  64.]]
```

**Problem 1 - Segmentation fault**

If you get a segmentation fault 11 when you perform "import tensorflow as tf" here's a [link](https://github.com/tensorflow/tensorflow/issues/2278) to the fix.

```
sudo ln -s /usr/local/cuda/lib/libcuda.dylib /usr/local/cuda/lib/libcuda.1.dylib
```

You can read more about using GPUs, in tensorflow in the official GPU [article](https://www.tensorflow.org/versions/master/how_tos/using_gpu/index.html).

## Credit

This post is adaptation of original post [here](https://gist.github.com/Mistobaan/dd32287eeb6859c6668d), which is bit dated as of this writing.

## Result

After this change, preliminary tests revealed that my Handwritten Digit Recognition project would still take 3-4 hrs. So my joy of getting GPU setup to work was very short lived. I decided to bring in big guns - move to the AWS cloud.

Next: [Develop and Evaluate Large Deep Learning Models with Keras on AWS](/notes/2016/11/13/develop-and-evaluate-large-deep-learning-models-with-keras-on-aws)




