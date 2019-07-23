# Unsupervised Learning

## What is unsupervised Learning? </br>
Unsupervised learning is where you only have input data (X) and no corresponding output variables. </br>
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-08%2009-51-27.png)

## What is clustering?</br>
It's an machine learning technique which segregate the various data points into different groups called clusters such that
entities in a particular group comparatively have more similar traits than entities in another group.

## Top 5 Clustering Algorithms to know

  - K-Means Clustering
  - Agglomerative Hierarchical Clustering
  - Mean-Shift Clustering
  - Density-Based Spatial Clustering of Applications with Noise (DBSCAN)
  - Expectation–Maximization (EM) Clustering using Gaussian Mixture Models (GMM)
  

## K- means Clustering ?
k-means clustering aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean.

![](https://github.com/theainerd/MLInterview/blob/master/images/1_KrcZK0xYgTa4qFrVr0fO2w.gif)

### K-Means Clustering Algorithm

![](https://github.com/theainerd/MLInterview/blob/master/images/kmeansclusteringalgo.png)

## Pros
* K-Means has the advantage that it’s pretty fast, as all we’re really doing is computing the distances between points and group centers; very few computations! It thus has a linear complexity O(n).

## Cons
* You have to select how many groups/classes there are.
* K-means also starts with a random choice of cluster centers and therefore it may yield different clustering results on different runs of the algorithm. Thus, the results may not be repeatable and lack consistency.

## Determining The Optimal Number Of Clusters: 3 Must Know Methods?
- Elbow method (within-cluster sum of square vs number of clusters) **We want it to be as small as possible**

![](https://github.com/theainerd/MLInterview/blob/master/images/inbox_2181887_42dfac7118608f18d67365a3c35a7aa6_Elbow%20method.png)

- Average silhouette method (average silhouette of observations (avg.sil) vs number of clusters) **high average silhouette width indicates a good clustering**

![](https://github.com/theainerd/MLInterview/blob/master/images/inbox_2181887_2db081ae1af423307f7ae558f76a2063_silhoutte.png)

- Gap statistic method The gap statistic compares the total intracluster variation for different values of k with their expected values under null reference distribution of the data i.e. a distribution with no obvious clustering.

![](https://github.com/theainerd/MLInterview/blob/master/images/inbox_2181887_373d4f8bda1be2b867c2f404dd335e85_unnamed-chunk-16-1.png)
## Hierarchical Clustering

It is a type of connectivity model clustering which is based on the fact that data points that are closer to each other are more similar than the data points lying far away in a data space.

As the name speaks for itself, the hierarchical clustering forms the hierarchy of the clusters that can be studied by visualising dendogram.

![](https://github.com/theainerd/MLInterview/blob/master/images/1_ET8kCcPpr893vNZFs8j4xg.gif)

## Pros

* Hierarchical clustering does not require us to specify the number of clusters and we can even select which number of clusters looks best since we are building a tree. 

## Cons
* Lower efficiency, as it has a time complexity of O(n³)

## Dimesionality Reduction Technique

Mainly there are two types of dimesion reduction technique:
1. Matrix Factorization(PCA)
2. Neighbour Graphs (UMAP, T-SNE)

### PCA (Principal Component Analysis)
* Principal Component Analysis (PCA) is a dimension reduction technique that projects
the data into a lower dimensional space
* PCA uses Singular Value Decomposition (SVD), which is a matrix factorization method
that decomposes a matrix into three smaller matrices (more details of SVD [here](https://en.wikipedia.org/wiki/Singular-value_decomposition))
* PCA finds top N principal components, which are dimensions along which the data vary
(spread out) the most. Intuitively, the more spread out the data along a specific dimension,
the more information is contained, thus the more important this dimension is for the
pattern recognition of the dataset
* PCA can be used as pre-step for data visualization: reducing high dimensional data
into 2D or 3D.
Note : PCA is interpretable dimension reduction.

### T-SNE(t-distributed stochastic neighbor embedding)

* It is a nonlinear dimensionality reduction technique well-suited for embedding high-dimensional data for visualization in a low-dimensional space of two or three dimensions.
* The t-SNE algorithm comprises two main stages.First, t-SNE constructs a probability distribution over pairs of high-dimensional objects in such a way that similar objects have a high probability of being picked, whilst dissimilar points have an extremely small probability of being picked. 
* Second, t-SNE defines a similar probability distribution over the points in the low-dimensional map, and it minimizes the Kullback–Leibler divergence between the two distributions with respect to the locations of the points in the map.


### UMAP(Uniform Manifold Approximation and Projection)

* UMAP (Uniform Manifold Approximation and Projection) is a novel manifold learning technique for dimension reduction
* The UMAP algorithm is competitive with t-SNE for visualization quality, and arguably preserves more of the global structure with superior run time performance. 
* UMAP’s topological foundations allow it to scale to signicantly larger dataset sizes than are feasible for t-SNE.
