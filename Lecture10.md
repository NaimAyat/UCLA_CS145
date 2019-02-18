# Lecture 10: Mixture Models
## Hard Clustering vs. Soft Clustering
* Hard clustering
  * Every object i is assigned to one cluster j, e.g., k-means
* Soft clustering
  * Every object i is assigned with a probability to different clusters
## Mixture Model-Based Clustering
* A set C of k probabilistic clusters C1, …,Ck
## The EM (Expectation Maximization) Algorithm
* A framework to approach maximum likelihood or maximum a posteriori estimates of parameters in statistical models.
* E-step assigns objects to clusters according to the current soft clustering or parameters of probabilistic clusters
* M-step finds the new clustering or parameters that maximize the expected likelihood, with respect to conditional distribution
## Gaussian Mixture Model
* Generative model
  * For each object:
    * Pick its cluster
    * Sample a value from the selected distribution
## Advantages and Disadvantages of GMM
* Strengths
  * Mixture models are more general than partitioning: different densities and sizes of clusters
  * Clusters can be characterized by a small number of parameters
  * The results may satisfy the statistical assumptions of the generative models
* Weakness
  * Converge to local optimal (overcome: run multi-times w. random initialization)
  * Computationally expensive if the number of distributions is large
  * Hard to estimate the number of clusters
  * Can only deal with spherical clusters
