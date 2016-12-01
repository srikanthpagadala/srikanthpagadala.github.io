---
layout: post
title: "Deep Learning on Apache Spark"
date: 2016-11-20
categories: ['Setup & Environment']
---

Deep learning is computationally intensive, so on very large datasets, speed matters. You can tackle the problem with faster hardware (usually GPUs), optimized code and some form of parallelism.

Data parallelism shards large datasets and hands those pieces to separate neural networks, say, each on its own core. We can rely on Apache Spark for this, training models in parallel and iteratively averages the parameters they produce in a central model. 

*post to be completed soon.. ran into few issues..stay tuned*

