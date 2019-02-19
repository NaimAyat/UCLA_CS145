# Classification
## Logistic Regression
* Predicts whether something is true or false, not continuous data
* "S" curve goes from 0 to 1
* Maximum likelihood: calculate the likelihood of observing each data point
## [Decision Trees](https://www.youtube.com/watch?v=eKD5gxPPeY0)
* [Calculate entropy, choose the one with the highest entropy](https://www.youtube.com/watch?v=AmCV4g7_-QM)
* [Information gain](https://www.youtube.com/watch?v=nodQ2s0CUbI)
## [KNN](https://www.youtube.com/watch?v=UqYde-LULfs)
* Given N training vectors, identify the k nearest neighbors of c
## [SVM](https://www.youtube.com/watch?v=1NxnPkZM9bc)
* Goal: design a hyperplane that classifies all training vectors into two classes (linearly separate)
* Best choice is the hyperplane that leaves the maximum margin between both classes
## [Neural Network](https://www.youtube.com/watch?v=aircAruvnKk)
# Clustering
## [K-means clustering](https://www.youtube.com/watch?v=_aWzGGNrcic)
* Input: K, set of points x1, ..., xn
* Place centroids c1 ... ck at random locations
* Repeat until convergence
  * For each point xi
    * Find the nearest centroid cj
    * Assign the point xi to cluster j
  * For each cluster j
    * Assign new centroid cj = mean of all points xi assigned to cluster j in previous step
* Convergence means that all points in a cluster are actually the ones closest to it
## [Hierarchical clustering](https://www.youtube.com/watch?v=GVz6Y8r5AkY&list=PLBv09BD7ez_7qIbBhyQDr-LAKWUeycZtx)
* Select number of clusters k
  * How coarse or fine-grained is the structure of your data?
* Instead of picking k - find a hierarchy of structure
  * Top levels - coarse effects, low levels - fine-grained
    * Topmost culster - contains every point in the dataset
    * Bottom level - set of n singleton clusters, one per data point
  * Strategies
    * Top-down: start with all items in one cluster, split recursively
    * Bottom-up: start with singletons, merge by some criterion
## [DBSCAN](https://www.youtube.com/watch?v=5E097ZLE9Sg)
* Input: set of points
* Neighborhood N: sets cutoff radius for similarity
* MinPoints: defines the value for which a neighborhood is considered dense
* Phase one: points are determined to be one of these three:
  * Core points: any point that has at least MinPoints in its neighborhood
  * Border points: non-core point that has at least one core in its neighborhood
  * Noise points: neither core or border
* Phase two:
  * Pick an unassigned core point and perform DFS from that point
  * Recursively apply the search to each core point in the neighborhood
  * Repeat until all core points are assigned to a cluster
* Benefits
  * Can find any number of clusters
  * Resists noise/outliers
  * Can find clusters of any shape or size
* Drawback
  * Sensitive to selection of N and MinPoints
