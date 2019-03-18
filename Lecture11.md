# Lecture 11: Set Data: Frequent Pattern Mining
## Set Data
* A data point corresponds to a set of items
## What Is Frequent Pattern Analysis?
* Frequent pattern: a pattern (a set of items, subsequences, substructures, etc.) that occurs frequently in a data set
* Motivation: Finding inherent regularities in data
## Basic Concepts: Frequent Patterns
* itemset: A set of one or more items
* k-itemset X = {x1, …, xk}: A set of k items
* (absolute) support, or, support count of X: Frequency or occurrence of an itemset X
* (relative) support, s, is the fraction of transactions that contains X (i.e., the probability that a transaction contains X)
* An itemset X is frequent if X’s support is no less than a minsup threshold
## Basic Concepts: Association Rules
* Find all the rules X -> Y with minimum support and confidence
  * support, s, probability that a transaction contains X ∪ Y
  * confidence, c, conditional probability that a transaction having X also contains Y
## Closed Patterns and Max-Patterns
* A long pattern contains a combinatorial number of sub-patterns
* In general, {a1, …, an} contains 2n – 1 subpatterns
## Computational Complexity of Frequent Itemset Mining
* How many itemsets are potentially to be generated in the worst case?
  * The number of frequent itemsets to be generated is sensitive to the minsup threshold
  * When minsup is low, there exist potentially an exponential number of frequent itemsets
## Scalable Frequent Itemset Mining Methods
* Apriori: A Candidate Generation-and-Test Approach
* FPGrowth: A Frequent Pattern-Growth Approach
## The Apriori Property and Scalable Mining Methods
* The Apriori property of frequent patterns
  * Any nonempty subsets of a frequent itemset must be frequent
  * E.g., If {beer, diaper, nuts} is frequent, so is {beer, diaper}
  * i.e., every transaction having {beer, diaper, nuts} also contains {beer, diaper} 
## Apriori: A Candidate Generation & Test Approach
* Apriori pruning principle: If there is any itemset which is infrequent, its superset should not be generated/tested
* Method:
  * Initially, scan DB once to get frequent 1-itemset
  * Generate length k candidate itemsets from length k-1 frequent itemsets
  * Test the candidates against DB
  * Terminate when no frequent or candidate set can be generated
## Further Improvement of the Apriori Method
* Major computational challenges
  * Multiple scans of transaction database
  * Huge number of candidates
  * Tedious workload of support counting for candidates
* Improving Apriori: general ideas
  * Reduce passes of transaction database scans
  * Shrink number of candidates
  * Facilitate support counting of candidates
## Pattern-Growth Approach: Mining Frequent Patterns Without Candidate Generation
* Bottlenecks of the Apriori approach
  * Breadth-first (i.e., level-wise) search
  * Scan DB multiple times
  * Candidate generation and test
  * Often generates a huge number of candidates
* The FPGrowth Approach 
  * Depth-first search
  * Avoid explicit candidate generation
## FP-Growth Algorithm Sketch
* Construct FP-tree (frequent pattern-tree)
  * Compress the DB into a tree
* Recursively mine FP-tree by FP-Growth
  * Construct conditional pattern base from FPtree
  * Construct conditional FP-tree from conditional pattern base
  * Until the tree has a single path or empty
