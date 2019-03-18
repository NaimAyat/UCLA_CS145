# Lecture 14: Text Data: Naïve Bayes
## Bernoulli and Categorical Distribution
* Bernoulli distribution
  * Discrete distribution that takes two values {0,1}
  * E.g., toss a coin with head and tail
* Categorical distribution
  * Discrete distribution that takes more than two values
    * Also called generalized Bernoulli distribution, multinoulli distribution
    * E.g., get 1-6 from a dice with 1/6
## Classification: Choosing Hypotheses
* Maximum a posteriori (maximize the posterior):
  * Useful observation: it does not depend on the denominator P(X)
## Classification by Maximum A Posteriori
* Let D be a training set of tuples and their associated class labels, and each tuple is represented by an p-D attribute vector
  * x = (x1, x2, …, xp)
* Suppose there are m classes y ∈ {1, 2, …, m}
* Classification is to derive the maximum posteriori, i.e., the maximal P(y=j|x)
  * This can be derived from Bayes’ theorem
* Since p(x) is constant for all classes, only p(x|y)p(y) needs to be maximized
