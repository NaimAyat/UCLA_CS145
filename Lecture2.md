# Lecture 2
## Vector Data
* Matrix of n x p
  * n data objects / points
  * p attributes / dimensions
### Atrribute Type
* Numerical
  * Height, income
* Categorical / discrete
  * Sex, race
## Categorical Attribute Types
* Nominal: categories, states, or names of things
  * Hair color
  * Marital status, occupation, ID numbers, zip codes
* Binary
  * Nominal attribute with ouly two states (0/1)
  * Symmetric binary: both outcomes equally important (e.g. male/female)
  * Asymmetric binary: outcomes not equally important
    * e.g. medical test (positive vs negative)
    * Convention: assign 1 to most important outcome (e.g. positive)
* Ordinal
  * Values have meaningful order, but magnitude between successive values is not known
    * Grades, army rankings, shirt sizes
## Measuring Central Tendency
* Mean (algebraic measure) (sample vs. population):
  * Note: n is sample size and N is population size.
    * Weighted arithmetic mean:
    * Trimmed mean: chopping extreme values
* Median:
  * Middle value if odd number of values, average of the middle two otherwise
* Mode
  * Value that occurs most frequently in the data
  * Unimodal, bimidal, trimodal
  * Empirical formula: mean-mode = 3*(mean-median)
### Symmetric vs. Skewed Data
* Symmetric: mean = median = mode 
* Positively skewed (tail on the right): mode < median < mean
* Negatively skewed (tail on the left): mean < median < mode
## Measuring the Dispersion of Data
* Quartiles, outliers, and boxplots
  * Quartiles: Q1 (25th percentile), Q3 (75th percentile)
  * Inter-quartile range = Q3 - Q1
  * Five number summary: min, Q1, median, Q3, max
  * Outlier: higher/lower value than 1.5*IQR of Q3 or Q1
* Variance and standard deviation (sample: s, population: σ)
  * Variance: algebraic, scalable computation
  * Standard deviation is the square root of variance
## Histogram Analysis
* Differs from a bar chart in that it is the area of the bar that denotes the value, not the height as in bar charts, a crucial distinction when the categories are not of uniform width
## Linear Regression
* Any attributes to a continuous value: x -> y
  * {age; major; gender; race} -> GPA
  * {income; credit score; profession} -> loan
  * {college; major; GPA} -> future income
### 3-Step Process
1. Model Conststruction
   * Use *training data* to find the best parameter β, denoted as β̂
2. Model selection
   * Use *validation data* to select the best model
3. Model usage
   * Apply thte model to the unseen data (*test data*)
## Gradient Descent
* Minimize the cost function by moving down in the steepest direction
### Batch Gradient Descent
* Move in the direction of steepest descend
### Stochastic Gradient Descent
* When a new observation, i, comes in, update
weight immediately (extremely useful for largescale datasets)
## Model Selection Problem
* Model too simple: underfit the data; poor predictions; high bias; low variance
* Model too complex: overfit the data; poor predicitons; low bias; high variance
* Model just right: balance bias and variance to get good predicitons
## Bias and Variance
* Bias: E(f(x)) - f(x)
  * How far is the expectation of the estimator to the true value? The smaller the better
* Variance: how variant is the estimator? The smaller the better
* Mean square error: bias^2 + variance + noise
## Cross-Validation
* Partition the data into K folds
* Use K-1 fold as training, and 1 fold as testing
* Calculate the average accuracy best on K training-testing pairs
* Accuracy on validation/test dataset!
