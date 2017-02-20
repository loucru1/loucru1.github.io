---
layout: post
title:  "The Curse of Dimensionality"
date:   2017-02-19 01:01:01 -0400
excerpt_separator: <!--more-->
categories: data-science machine-learning ml
comments: true
---
One of the limitations of the k- nearest neighbor algorithms is that it performs worse as the number of dimensions in the data grows. This is caused by a phenomenon which data scientists call The Curse of Dimensionality. My goal of this post is to give some intuition on the implications on k nearest neighbors.

<!--more-->

# The Setup
First, let's set up the example. Let's say we have an n-dimensional uniformly distributed data set, D. And within this dataset, every point falls within an n-dimensional hypercube, H (black). That is, H is defined as the bounding hypercube of the dataset. Inside this hypercube, let's define a smaller hypercube, H’ (red), that is the smallest bounding box of the k nearest neighbors of a test point, p (blue). We can define this smaller hypercube to have edge length, l.  

{% include image.html
  img="assets/curse_of_dim.png"
  title="Curse of Dimensionality Example"
  caption="Figure 1: A demonstration of the setup where D=3."
%}

# The Curse
Now that we have the example set up, let's see if we can understand the implications of the curse of dimensionality. Imagine that we start with the inner bounding box with L = 0, and grow it slowly to contain the first k neighbors of p. Clearly, the volume of this hypercube is L^d in d dimension. However, because that data is uniformly distributed, we can also say that the volume of the H’ is approximately k/n. That is, L^d = k/n. (If this relationship doesn’t seem clear, I would advise revisiting uniform distributions. Also, it may also be easier understand when considering the one-dimensional case.)
This relationship has large implications. Namely, if we take the d-root from both sides we get that l = (k/n)^(1/d). This says that as d gets larger, the edge of the inner bounding box gets closer to the edge length of H. Below are some examples:


So why is this so bad? Well, let's consider the case where D = 1000. Here the length of the smallest bounding box of the k nearest neighbors is .9954. And since we know that the data points come from a uniform distribution, we can assume that all k points within the inner hypercube are close to the edges. This means that the k “nearest “neighbors” are not actually near at all. In fact, they are barely closer than the other k-n points. Now, since we know that almost all n points are approximately the same distance from the test point, using distance as a metric for similarity becomes fallible. However, the semantics of the k nearest neighbor algorithm assumes that distance is a good metric for similarity, thus reducing its effectiveness on high dimensional data.

# Wrap Up
When doing machine learning it’s very important to understand the model you are using. There is no perfect model for every problem so it’s critical to be conscious of their benefits and drawbacks. For K nearest neighbors, its limitation is the curse of dimensionality because as the dimensions of the data set grow, distance becomes less of a valuable metric to measure similarity.
