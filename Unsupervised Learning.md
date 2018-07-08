# Unsupervised Learning

## What is unsupervised Learning? </br>
Unsupervised learning is where you only have input data (X) and no corresponding output variables. </br>
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-08%2009-51-27.png)

## What is clustering?</br>
It's an machine learning technique which segregate the various data points into different groups called clusters such that
entities in a particular group comparatively have more similar traits than entities in another group.

## Top 5 Clustering Algorithms to know

  - K-Means Clustering
  - Mean-Shift Clustering
  - Density-Based Spatial Clustering of Applications with Noise (DBSCAN)
  - Expectation–Maximization (EM) Clustering using Gaussian Mixture Models (GMM)
  - Agglomerative Hierarchical Clustering

## K- means Clustering ?
k-means clustering aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean.

## Determining The Optimal Number Of Clusters: 3 Must Know Methods?
- Elbow method
- Average silhouette method
- Gap statistic method

## Hierarchical Clustering

It is a type of connectivity model clustering which is based on the fact that data points that are closer to each other are more similar than the data points lying far away in a data space.

As the name speaks for itself, the hierarchical clustering forms the hierarchy of the clusters that can be studied by visualising dendogram.

## Principal Component Analysis
* Principal Component Analysis (PCA) is a dimension reduction technique that projects
the data into a lower dimensional space
* PCA uses Singular Value Decomposition (SVD), which is a matrix factorization method
that decomposes a matrix into three smaller matrices (more details of SVD [here](https://en.wikipedia.org/wiki/Singular-value_decomposition))
* PCA finds top N principal components, which are dimensions along which the data vary
(spread out) the most. Intuitively, the more spread out the data along a specific dimension,
the more information is contained, thus the more important this dimension is for the
pattern recognition of the dataset
* PCA can be used as pre-step for data visualization: reducing high dimensional data
into 2D or 3D. An alternative dimensionality reduction technique is [t-SNE](https://lvdmaaten.github.io/tsne/)
