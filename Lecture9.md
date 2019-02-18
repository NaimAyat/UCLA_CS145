# Lecture 9: Clustering Basics
## What is Cluster Analysis?
* Cluster: A collection of data objects
  * similar (or related) to one another within the same group
  * dissimilar (or unrelated) to the objects in other groups
*  Cluster analysis (or clustering, data segmentation, …)
  * Finding similarities between data according to the characteristics found in the data and grouping similar data objects into clusters
* Unsupervised learning: no predefined classes (i.e., learning by observations vs. learning by examples: supervised)
* Typical applications
  * as a stand-alone tool to get insight into data distribution
  * As a preprocessing step for other algorithms
## The K-Means Clustering Method
* Given k, the k-means algorithm is implemented in four steps:
* Step 0: Partition objects into k nonempty subsets
* Step 1: Compute seed points as the centroids of the clusters of the current partitioning (the centroid is the center, i.e., mean point, of the cluster)
* Step 2: Assign each object to the cluster with the nearest seed point
* Step 3: Go back to Step 1, stop when the assignment does not change
### Comments on the K-Means Method
* Strength: Efficient: O(tkn), where n is # objects, k is # clusters, and t is # iterations. Normally, k, t << n.
* Comment: Often terminates at a local optimal
* Weaknesses
  * Applicable only to objects in a continuous n-dimensional space
  * Using the k-modes method for categorical data
  * In comparison, k-medoids can be applied to a wide range of data
* Need to specify k, the number of clusters, in advance (there are ways to automatically determine the best k (see Hastie et al., 2009)
* Sensitive to noisy data and outliers
* Not suitable to discover clusters with non-convex shapes
## The K-Medoid Clustering Method
* K-Medoids Clustering: Find representative objects (medoids) in clusters
* PAM (Partitioning Around Medoids, Kaufmann & Rousseeuw 1987)
  * Starts from an initial set of medoids and iteratively replaces one of the medoids by one of the non-medoids if it improves the total distance of the resulting clustering
  * PAM works effectively for small data sets, but does not scale well for large data sets (due to the computational complexity)
## Hierarchical Clustering
* Use distance matrix as clustering criteria. This method does not require the number of clusters k as an input, but needs a termination condition 
### AGNES (Agglomerative Nesting)
* Implemented in statistical packages, e.g., Splus
* Use the single-link method and the dissimilarity matrix
* Merge nodes that have the least dissimilarity
* Go on in a non-descending fashion
* Eventually all nodes belong to the same cluster
### Pseudo Code
* Initialization: Place each data point into its own cluster and compute distance matrix between clusters
* Repeat:
  * Merge the two closest clusters
  * Update the distance matrix for the affected entries
  * Until: all the data are merged into a single cluster
## DBSCAN: Basic Concepts
* Two parameters:
  * Eps: Maximum radius of the neighborhood
  * MinPts: Minimum number of points in an Epsneighborhood of that point
* Directly density-reachable: A point p is directly densityreachable from a point q w.r.t. Eps, MinPts if 
### Density-Reachable and Density-Connected
* A point p is density-reachable from a point q w.r.t. Eps, MinPts if there is a chain of points p1 , …, pn, p1 = q, pn = p such that pi+1 is directly density-reachable from pi
* A point p is density-connected to a point q w.r.t. Eps, MinPts if there is a point o such that both, p and q are density-reachable from o w.r.t. Eps and MinPts
### DBSCAN: Density-Based Spatial Clustering of Applications with Noise
* Relies on a density-based notion of cluster: A cluster is defined as a maximal set of density-connected points
* Noise: object not contained in any cluster is noise
* Discovers clusters of arbitrary shape in spatial databases with noise
### DBSCAN Algorithm
```
mark all objects as unvisited;
do
  randomly select an unvisited object p;
  mark p as visited;
  if the neighborhood of p has at least MinPts objects:
    create a new cluster C and add p to C;
    let N be the set of objects in the neighborhood of p;
    for each point p' in N:
      if p' is unvisited:
        mark p' as visited;
        if the neighborhood of p' has at least MinPts points, add those points to N;
      if p' is not yet a member of any cluster, add p' to C;
    output C;
  else mark p as noise;
end when no object is unvisited
```
