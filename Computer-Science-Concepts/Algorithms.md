# Dynamic Programming -- [source](https://people.eecs.berkeley.edu/~vazirani/algorithms/chap6.pdf)
- in directed acyclic graphs can be *linearized*: ordered in an array
- if we want to minimize distance in a weighted graph, and both A and B point to C, then `dist(C) = min{dist(A) + AC, dist(B) + BC}`
- solving a collection of subproblems, `{dist(u) : u in V}` from left to right
- dynamic programming is breaking a problem into solving subproblems, and using previous subproblems to solve later subproblems
- longest increasing subsequence problem (not necessarily consecutive) can be solved using DP
  - construct a graph, with directed edges between each node whenever possible, forming a dag
  - now find longest path in dag, and track previous node and backtrack for the actual subsequence
- edit distance: the cost of the best possible alignment between two strings
  - minimum edits (insertion, deletion, replacement)
  - our subproblem will be finding the edit distance between a prefix of s1 and s2

## Subset sum problem
- NP complete problem; is there a subset whose sum is 0?
