# Lecture 7: Vector Data: K Nearest Neighbor
## Lazy vs. Eager Learning
* Lazy learning (e.g., instance-based learning): Simply stores training data (or only minor processing) and waits until it is given a test tuple
* Eager learning (the above discussed methods): Given a set of training tuples, constructs a classification model before receiving new (e.g., test) data to classify
* Lazy: less time in training but more time in predicting
* Accuracy
  * Lazy method effectively uses a richer hypothesis space since it uses many local linear functions to form an implicit global approximation to the target function
  * Eager: must commit to a single hypothesis that covers the entire instance space
## Lazy Learner: Instance-Based Methods
* Instance-based learning:
* Store training examples and delay the processing (“lazy evaluation”) until a new instance must be classified
* Typical approaches
  * k-nearest neighbor approach
    * Instances represented as points in, e.g., a Euclidean space.
  * Locally weighted regression
    * Constructs local approximation
## The k-Nearest Neighbor Algorithm
* All instances correspond to points in the n-D space
* The nearest neighbor are defined in terms of a distance measure, dist(X1, X2)
* Target function could be discrete- or real- valued
* For discrete-valued, k-NN returns the most common value among the k training examples nearest to xq
* Vonoroi diagram: the decision surface induced by 1-NN for a typical set of training examples
## kNN Example
* X = (length, lightness)
* Classes = {salmon, bass, eel}
* Identify fish given its (length, lightness)
### kNN Algorithm
* Choose K
  * For a given new instance X_new, find K closest training points w.r.t. a distance measure
* Classify X_new = majority vote among the K points
## Discussion on the k-NN Algorithm
* k-NN for real-valued prediction for a given unknown tuple
  * Returns the mean values of the k nearest neighbors
* Distance-weighted nearest neighbor algorithm
  * Weight the contribution of each of the k neighbors according to their distance to the query xq
  * Give greater weight to closer neighbors
* Curse of dimensionality: distance between neighbors could be dominated by irrelevant attributes
* To overcome it, axes stretch or elimination of the least relevant attributes
## Selection of k for kNN
* The number of neighbors k
  * Small k: overfitting (high var., low bias)
  * Big k: bringing too many irrelevant points (high bias, low var.)
## Similarity and Dissimilarity
* Similarity
  * Numerical measure of how alike two data objects are
  * Value is higher when objects are more alike
  * Often falls in the range [0,1]
* Dissimilarity (e.g., distance)
  * Numerical measure of how different two data objects are
  * Lower when objects are more alike
  * Minimum dissimilarity is often 0
  * Upper limit varies
  * Proximity refers to a similarity or dissimilarity
## Data Matrix and Dissimilarity Matrix
* Data matrix
  * n data points with p dimensions
  * Two modes
* Dissimilarity matrix
  * n data points, but registers only the distance
  * A triangular matrix
  * Single mode
