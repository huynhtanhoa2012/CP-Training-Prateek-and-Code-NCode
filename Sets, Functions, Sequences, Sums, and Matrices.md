# Sets, Functions, Sequences, Sums and Matrices

## Sets
Sets are used to group objects together. Often, but not always, the objects in a set have similar properties.


>We write `a ∈ A` to denote that `a` is an element of the set `A`. The notation `a /∈ A` denotes that `a` is not an element of the set `A`

Examples:
* The set V of all vowels in the English alphabet can be written as V = {a, e, i, o, u}.
* The set O of odd positive integers less than 10 can be expressed by O = {1, 3, 5, 7, 9}

> O = {x ∈ Z+ | x is odd and x < 10 }

* N = {0, 1, 2, 3, . . .}, the set of **natural numbers**
* Z = {. . . , −2, −1, 0, 1, 2, . . .}, the set of **integers**
* Z+ = {1, 2, 3, . . .}, the set of **positive integers**
* Q = {p/q | p ∈ Z, q ∈ Z, and q = 0}, the set of **rational numbers**
* R, the set of **real numbers**
* R+, the set of **positive real numbers**
* C, the set of **complex numbers**

> Two sets are equal if and only if they have the same elements. Therefore, if A and B are sets,then A and B are equal if and only if ∀x(x ∈ A ↔ x ∈ B). We write A = B if A and B are equal sets.

Example:
* The sets `{1, 3, 5}`and `{3, 5, 1}` are equal, because they have the same elements

### Power Sets
Given a set S, the power set of S is the set of all subsets of the set S. The power set of S is
denoted by P(S).

> The power set P({0, 1, 2}) is the set of all subsets of {0, 1, 2}. Hence:

> P({0, 1, 2}) = {∅, {0}, {1}, {2}, {0, 1}, {0, 2}, {1, 2}, {0, 1, 2}}.

### Set Operations

#### Union:
Let A and B be sets. The union of the sets A and B, denoted by `A ∪ B`, is the set that contains those elements that are either in A or in B, or in both.
> A ∪ B = {x | x ∈ A ∨ x ∈ B}.

Example: 
> A = {1, 3, 5} ∪ B = {1, 2, 3} = {1, 2, 3, 5}. 

<img src="Photos/union.png" width="200">

#### Intersection
The intersection of the sets A and B, denoted by `A ∩ B`, is the set containing those elements in both A and B.
> A ∩ B = {x | x ∈ A ∧ x ∈ B}

Example:
> {1, 3, 5} ∩ {1, 2, 3} = {1, 3}.

<img src="Photos/intersection.png" width="200">

#### Disjoint
Two sets are called disjoint if their intersection is the empty set.

> Let A = {1, 3, 5, 7, 9} and B = {2, 4, 6, 8, 10}. Because A ∩ B = ∅ 

#### Difference
The difference of A and B, denoted by A − B, is the set containing those elements **that are in A but not in B**. 

> A − B = {x | x ∈ A ∧ x / ∈ B}.

> An element x belongs to the difference of A and B if and only if x ∈ A and x / ∈ 

Example:
> {1, 3, 5} − {1, 2, 3} = {5}

#### Universal set
Let U be the universal set. The complement of the set A, denoted by A, is the complement
of A with respect to U. Therefore, the complement of the set A is U − 

> negation -A = {x ∈ U | x / ∈ A}.

Example: 
> Let A = {a, e, i, o, u} . Then negation -A = {b, c, d, f, g, h, j, k, l, m, n, p, q, r, s, t, v, w, x, y, z}.

## Sequences and Summations

### Sequences 
Sequences are ordered lists of elements.

A sequence is a function from a subset of the set of integers (usually either the set {0, 1, 2, . . .} or the set {1, 2, 3, . . .}) to a set S. 
* A **geometric** progression: a, ar, ar^2, . . . , ar^n, . . .
* An **arithmetic** progression: a, a + d, a + 2d, . . . , a + nd, . . .

### Recurrence Relations
A recurrence relation for the sequence `{an}` is an equation that expresses an in terms of one or more of the previous terms of the sequence, namely, `a0, a1, . . . , an−1`, for all integers n with `n ≥ n0`, where `n0` is a nonnegative integer

Example:
> Assume `{an}` is the recurrence relation `an = a(n−1) + 3` for `n = 1, 2, 3, . . . `

> `a1 = a0 + 3 = 2 + 3 = 5`. It then follows that a2 = 5 + 3 = 8 and a3 = 8 + 3 = 11. 

### Fibonacci sequence
> The Fibonacci sequence, f0, f1, f2, . . . , is defined by the initial conditions f0 = 0, f1 = 1, and the recurrence relation

> fn = f(n−1) + f(n−2)  for n = 2, 3, 4, . . . .

### Special Integer Sequences
Find formulae for the sequences with the following first five terms: 
* (a) 1, 1/2, 1/4, 1/8, 1/16
* (b) 1, 3, 5, 7, 9 
* (c) 1, −1, 1, −1, 1

> (a) an = 1/2^n, n = 0, 1, 2, . . .

> (b) an = 2n + 1, n = 0, 1, 2, . . . 

> (c) an = (−1)n, n = 0, 1, 2 . . .

## Summations
> a(m), a(m+1), ..., a(n)

<img src="Photos/summation.png" width="300">
<img src="Photos/sumExample.png" width="300">
<img src="Photos/UsefulFormula.png" width="300">