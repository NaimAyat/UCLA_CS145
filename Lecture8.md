# Lecture 8: Classification Evaluation and Practical Issues
## Model Evaluation and Selection
* Evaluation metrics: How can we measure accuracy? Other metrics to consider?
* Use validation test set of class-labeled tuples instead of training set when assessing accuracy
* Methods for estimating a classifier’s accuracy:
  * Holdout method, random subsampling
  * Cross-validation
### Holdout method
* Given data is randomly partitioned into two independent sets
  * Training set (e.g., 2/3) for model construction
  * Test set (e.g., 1/3) for accuracy estimation
* Random sampling: a variation of holdout
  * Repeat holdout k times, accuracy = avg. of the accuracies obtained
### Cross-validation (k-fold, where k = 10 is most popular)
* Randomly partition the data into k mutually exclusive subsets, each approximately equal size
* At i-th iteration, use Di as test set and others as training set
* Leave-one-out: k folds where k = # of tuples, for small sized data
* Stratified cross-validation: folds are stratified so that class dist. in each fold is approx. the same as that in the whole data
