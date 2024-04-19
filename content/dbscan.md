---
layout: default
title: DBSCAN
nav_order: 8
---


# DBSCAN - Density Based Spatial Clustering of Applications with Noise 

In the workshop colab file, we saw K-means clutseign algorithm and correponsing code in Python to make it work. 

However, in some case K-means fail to cpature the underlying pattern to create clusters. Refer to figure below:

![DBSCAN & K-means](https://miro.medium.com/max/1339/0*xu3GYMsWu9QiKNOo.png)

In first case, with concentric cricles, K-means clustered the points based on the distance, however the distance here is not the key. They key here is the density of pattern. DBSCAN will be able to capture that. Thus, it is very important to do a primilary analysis of the data before choosing the right clustering algorithm. 

DBSCAN is based on the idea that a cluster in data space is contiguous region of high point density, seperated from other such clusters by contihuous regions of low point density. It finds core samples of high density and expands clusters from them.

It majorly uses two parameters:

1. min_smaples: The number of samples in a neighbourhood for a point to be considered as a core point. 

2. eps: The maximum distance between two samples for one to be considered as in the neighborhood of the other. 


Let's look at it's implementation: 

```
from sklearn.cluster import DBSCAN

clustering = DBSCAN(eps=3, min_samples=2).fit(data)

labels = clustering.labels_

```