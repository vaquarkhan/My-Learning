## Sets 
A *set* is an unordered colleciton of distinct objects. The objects in a set are *elements* or *members*.

Fields like the Natural numbers, Integers or Real numbers are all sets defined like {0,1,2, ...}.

#### Operations
- Union. A ∪ B = {x : x in A or x in B}
- Intersection. A ∩ B = {x : x in A and x in B}
- Difference. A \ B = {x : x in A and ¬ in B}
- Can be extended to multiple sets (like large sum notation ∑)
- Cardinality |A| is the *size* of A, number of elements.
- Subset. A ⊆ B = { for all x in A, x in B}

Two sets are disjoint if they share no elements, or whose intersection is the empty set ø. A family of sets is pairwise disjoint if for any two sets A and B are disjoint.

#### Notation
For sets A and B, A x B is a cartesian product, with the identity |A x B| = |A||B| (actually like a product of sets). Can be extended to say B^A to mean the set of all functions that map from A->B: { f: A -> B }

So the total number of possible functions is |B| possibilities |A| times for each element `a` in A. So `|B^A| = |B|^|A|`

R^2 is the two dimensional space (from linear algebra), or the set of all tuples of real numbers. This can be re-written as `R^{0,1}`. That is, the set of functions that map `0` or `1` to two Real numbers respectively. (3.14, -5) could be represented as f(0) = 3.14, f(1) = -5, f in R^2.

##### Set of All Subsets
**The power set** of A is the set of all subsets, denoted by `2^A`. It can be thought of as `{0,1}^A`, the set of all functions that map an element a in A to either 1 or 0. That is, for every element `a` in A, we can either include it or exclude it, giving us 2 possiblities per element and 2^|A| subsets in total. Useful as a filter: f(a) = { 1 if a is allowed by f, 0 if not } where `2^A` is the set of all subsets of A. This also works nicely with cardinality: |2^A| = 2^|A| 
