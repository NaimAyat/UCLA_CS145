# Lecture 12: Sequence Data: Sequential Pattern Mining
## Sequence Database
* A sequence database consists of sequences of ordered elements or events, recorded with or without a concrete notion of time
## Sequence Databases & Sequential Patterns
* Transaction databases vs. sequence databases
* Frequent patterns vs. (frequent) sequential patterns
* Applications of sequential pattern mining
## What Is Sequential Pattern Mining?
* Given a set of sequences, find the complete set of frequent subsequences
## Sequence
* Event / element
  * An non-empty set of items, e.g., e=(ab)
* Sequence
  * An ordered list of events, e.g., 𝑠𝑠 =< 𝑒𝑒1𝑒𝑒2 … 𝑒𝑒𝑙𝑙 >
* Length of a sequence
  * The number of instances of items in a sequence
  * The length of < (ef) (ab) (df) c b > is 8 (Not 5!)
## Sequential Pattern
* Support of a sequence 𝛼
  *  Number of sequences in the database that are supersequence of 𝛼
  * Support𝑠 (𝛼)
* 𝛼 is frequent if Support𝑠(𝛼) ≥ min_support
* A frequent sequence is called sequential pattern
  * l-pattern if the length of the sequence is l
## Challenges on Sequential Pattern Mining
* A huge number of possible sequential patterns are hidden in databases
* A mining algorithm should
  * find the complete set of patterns, when possible, satisfying the minimum support (frequency) threshold
  * be highly efficient, scalable, involving only a small number of database scans
  * be able to incorporate various kinds of userspecific constraints
## The Apriori Property of Sequential Patterns
* A basic property: Apriori
  * If a sequence S is not frequent
  * Then none of the super-sequences of S is frequent
  * E.g, <hb> is infrequent -> so do <hab> and <(ah)b>
## GSP—Generalized Sequential Pattern Mining
* GSP (Generalized Sequential Pattern) mining algorithm
  * proposed by Agrawal and Srikant, EDBT’96
* Outline of the method
• Initially, every item in DB is a candidate of length-1
  * for each level (i.e., sequences of length-k) do
    * scan database to collect support count for each candidate sequence
    * generate candidate length-(k+1) sequences from length-k frequent sequences using Apriori
  * repeat until no frequent sequence or no candidate can be found
* Major strength: Candidate pruning by Apriori
## Candidate Generate-and-test: Drawbacks
