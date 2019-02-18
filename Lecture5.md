# Lecture 5: Vector Data: Support Vector Machine
## Linear Classifier
* A separating hyperplane can be written as a linear combination of attributes
## SVM - When Data is Linearly Separable
* There are infinite lines (hyperplanes) separating the two classes but we want to find the best one (the one that minimizes classification error on unseen data)
*  SVM searches for the hyperplane with the largest margin, i.e., maximum marginal hyperplane (MMH)
## SVM—Linearly Separable
* Any training tuples that fall on hyperplanes H1 or H2 (i.e., the sides defining the margin) are support vectors
## Soft Margin Classification 
* If the training data is not linearly separable, slack variables ξi can be added to allow misclassification of difficult or noisy examples
* Allow some errors
  * Let some points be moved to where they belong, at a cost
## Non-linear SVMs
* Datasets that are not linearly separable
* Map to a higher-dimensional space
