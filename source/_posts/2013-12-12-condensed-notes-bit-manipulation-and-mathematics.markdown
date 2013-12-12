---
layout: post
title: "Condensed Notes: Bit Manipulation And Mathematics"
date: 2013-12-12 11:34
comments: true
categories: 
---

# Bit Manipulation
- Count number of 1s

> The operation ``c = c & (c - 1)`` will clear the least significant bit 1

```
for (int count=0; c!=0; c=c & (c-1)) { 
  count++;
}
```

- even bits ``x & 0xaaaaaaaa`` and odd bits ``x & 0x55555555``
- ``x ^ x == 0``
> - In an array, every number occurs twice except for one. Find out that single number.

- matrix problems

> matrix elimination: Given an MX N matrix in which each row and each column is sorted in ascendingorder, write a method to find an element.

# Algebra

- Greatest common factor and least common multiple
- Prime numbers
> divisibility

> checking for primality

> generate a list of primes

# Discrete Mathematics
- combination
- permutation mathematics
- Catalan numbers 
$$C_0 = 1 \quad \text{and} \quad C_{n+1}=\sum_{i=0}^n C_i\,C_{n-i}\quad\text{for }n\ge 0.$$
$$C_n = \frac{1}{n+1}{2n\choose n} = \frac{(2n)!}{(n+1)!\,n!} = \prod\limits_{k=2}^{n}\frac{n+k}{k} \qquad\mbox{ for }n\ge 0.$$

- C(n,m)=C(n-1,m-1)+C(n-1,m)
 

# Probability Theory

- Inclusion–exclusion principle
- Independence
- Bayes' theorem

# Geometry

- check whether a point is on a line
- Gift wrapping algorithm &  Graham's Scan Algorithm 
> Convex hull (convex envelope), dot product of coordinate vector 

- precision problem (CGAL)