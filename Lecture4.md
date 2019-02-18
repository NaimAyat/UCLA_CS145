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
## Computing Information-Gain for Continuous-Valued Attributes
