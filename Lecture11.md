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
## Benefits of the FP-tree Structure
* Completeness
  * Preserve complete information for frequent pattern mining
  * Never break a long pattern of any transaction
* Compactness
  * Reduce irrelevant info—infrequent items are gone
  * Items in frequency descending order: the more frequently occurring, the more likely to be shared
  * Never be larger than the original database (not count node-links and the count field)
## Advantages of the Pattern Growth Approach
* Divide-and-conquer:
  * Decompose both the mining task and DB according to the frequent patterns obtained so far
  * Lead to focused search of smaller databases
* Other factors
  * No candidate generation, no candidate test
  * Compressed database: FP-tree structure
  * No repeated scan of entire database
  * Basic ops: counting local freq items and building sub FP-tree, no pattern search and matching
## Correlation Analysis (Nominal Data)
* 𝜒2 = Chi-square test = sum((observed-expected)^2/expected)
* Independency test between two attributes
  * The larger the 𝜒2 value, the more likely the variables are related
* The cells that contribute the most to the 𝜒2 value are those whose actual count is very different from the expected count under independence assumption
* Correlation does not imply causality
  * # of hospitals and # of car-theft in a city are correlated
  * Both are causally linked to the third variable: population
## When Do We Need Chi-Square Test?
Considering two attributes A and B
* A: a nominal attribute with c distinct values,
  * E.g., Grades of Math
* B: a nominal attribute with r distinct values,
  * E.g., Grades of Science
* Question: Are A and B related?
## Are lift and χ2 Good Measures of Correlation?
* Lift and χ2 are affected by null-transaction
* E.g., number of transactions that do not contain milk nor coffee
