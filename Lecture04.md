# Lecture 4: Vector Data: Decision Tree
## Tree-Based Models
* Use trees to partition the data into different regions and make predictions
* A path from root to a leaf node corresponds to a rule
## Brief Review of Entropy
* A measure of uncertainty (impurity) associated with a random variable
  * Higher entropy => higher uncertainty
  * Lower entropy => lower uncertainty
## Algorithm for Decision Tree Induction
* Basic algorithm (a greedy algorithm)
  * Tree is constructed in a top-down recursive divide-and-conquer manner
  * At start, all the training examples are at the root
  * Attributes are categorical (if continuous-valued, they are discretized in advance)
  * Examples are partitioned recursively based on selected attributes
  * Test attributes are selected on the basis of a heuristic or statistical measure (e.g., information gain)
* Conditions for stopping partitioning
  * All samples for a given node belong to the same class
  * There are no remaining attributes for further partitioning – majority voting is employed for classifying the leaf
  * There are no samples left – use majority voting in the parent partition
## Comparing Attribute Selection Measures
* Information gain:
  * biased towards multivalued attributes
* Gain ratio:
  * tends to prefer unbalanced splits in which one partition is much smaller than the others (why?)
* Gini index:
  * biased to multivalued attributes
## Overfitting and Tree Pruning
* Overfitting: An induced tree may overfit the training data
  * Too many branches, some may reflect anomalies due to noise or outliers
  * Poor accuracy for unseen samples
* Two approaches to avoid overfitting
  * Prepruning: Halt tree construction early ̵do not split a node if this would result in the goodness measure falling below a threshold
    * Difficult to choose an appropriate threshold
  * Postpruning: Remove branches from a “fully grown” tree—get a sequence of progressively pruned trees
    * Use validation dataset to decide which is the “best pruned tree”
## Regression Trees
* Target variable
  * From categorical variable to continuous variable
* Attribute selection criterion
  * Measure the purity of continuous target variable in each partition
* Leaf node
  * A simple model for that partition, e.g., average
