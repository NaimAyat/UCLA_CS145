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
