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
* A huge set of candidate sequences generated.
  * Especially 2-item candidate sequence.
* Multiple Scans of database needed.
  * The length of each candidate grows by one at each database scan.
* Inefficient for mining long sequential patterns.
  * A long pattern grow up from short patterns
  * The number of short patterns is exponential to the length of mined patterns.
## Prefix and Suffix
* Assume a pre-specified order on items, e.g., alphabetical order
* <a>, <aa>, <a(ab)> and <a(abc)> are prefixes of sequence <a(abc)(ac)d(cf)>
  * Note <a(ac)> is not a prefix of <a(abc)(ac)d(cf)>
* Given sequence <a(abc)(ac)d(cf)>
  * (_bc) means: the last element in the prefix together with (bc) form one element
## Prefix-based Projection
* Given a sequence 𝛼, let 𝛼′ be subsequence
  * 𝛼′ is called a projection of 𝛼𝛼 w.r.t. prefix 𝛽, if only and only if
  * 𝛼′ has prefix 𝛽, and
  * 𝛼′ is the maximum subsequence of 𝛼 with prefix 𝛽
## Projected (Suffix) Database
* Let 𝛼 be a sequential pattern, 𝛼-projected database is the collection of suffixes of projections of sequences in the database w.r.t. prefix 𝛼
## Mining Sequential Patterns by Prefix Projections
* Step 1: find length-1 sequential patterns
  * <a>, <b>, <c>, <d>, <e>, <f>
* Step 2: divide search space. The complete set of seq. pat. can be partitioned into 6 subsets:
  * The ones having prefix <a>;
  * The ones having prefix <b>;
  *  …
  * The ones having prefix <f>
* Step 3: mine each subset recursively via corresponding projected databases
## Finding Seq. Patterns with Prefix <a>
* Only need to consider projections w.r.t. <a>
* Find all the length-2 seq. pat. Having prefix <a>: <aa>, <ab>, <(ab)>, <ac>, <ad>, <af>
## Efficiency of PrefixSpan
* No candidate sequence needs to be generated
* Projected databases keep shrinking
* Major cost of PrefixSpan: Constructing projected databases
  * Can be improved by pseudo-projections
