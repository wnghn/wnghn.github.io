---
layout: post
title: "Condensed Notes: Algorithms"
date: 2013-12-12 16:19
comments: true
categories: 
---

# Sort
* internal sort
  - insert sort (stable), bubble sort(stable), selection sort(ustable)
  - shell sort(unstable)
  - quick sort(unstable), merge sort(stable), heap sort(unstable)
  - bucket sort(stable, linear runtime for linear range), radix sort(stable)
* external sort
  - winner's tree

> - merge intervals

# Search
- Binary Search
- Top K Element (Quick Selection)
> - Median of Two Sorted Arrays

- BFS

# Simple recursive algorithms
Solve problems that can be solved by a simple iteration.
- Tail Call Optimization

# Backtracking algorithms (DFS)

## Target: any single solution

1. Tests to see if a solution has been found, and if so, return it
1. For each choice
  * make the choice
  * recur
  * if the recursion finds a solution, return it
  * unset the choice 
1. return failure if no choice remains

## Target: all possible solutions

1. Tests to see if a solution has been found, and if so, add it to the solution set
1. For each choice
  * make the choice
  * recur
  * unset the choice 

> - 8 Queens
> - word in a char matrix
> - permutation
> - distinct paths in a directed graph (break a long string into words and print all solutions) 
> - find all unique combinations in a set of numbers where the candidate numbers sums to a target value
> - Letter Combinations of a Phone Number

#  Divide and conquer algorithms
1. Divide the problem into smaller subproblems of the same type, and solve these subproblems recursively
1. Combine the solutions to the subproblems into a solution to the original problem

Solve problems that are composed of nonoverlapping subproblems

> - Quick Sort
>- Merge Sort

# Dynamic programming algorithms
Requirement: an induction equation

- overlapping subproblems
- optimal substructure

Steps:

- Top-down (recurrsion with memorization)
- Bottom-up 

> - Pascal's triangle.
> - How many possible unique paths are there from the top left corner of a grid to the bottom right corner?
> - The path with the minmum sum in a m x n grid
> - whether a long string is breakable into valid words

# Greedy algorithms

> - Suppose you want to count out a certain amount of money, using the fewest possible bills and coins
> - which two vertical lines compose a container with the maximum volume?
> - 2 sum

# Branch and bound algorithms
> - Wildcard Matching

# Brute force algorithms
Optimizations:
- Heuristic: A “rule of thumb” that helps you decide which possibilities to look at first
- Elimination

# Randomized algorithms

# Trick: Replace Recursion by Iteration

Original Post: [Way to go from recursion to iteration](http://stackoverflow.com/questions/159590/way-to-go-from-recursion-to-iteration)

Replacing the program stack by one of your own:
```
Stack<Object> stack;
stack.push(first_object);
while( !stack.isEmpty() ) {
   // Do something
   my_object = stack.pop();

  // Push other objects on the stack.

}
```
if you have more than one recursive call inside and you want to preserve the order of the calls, you have to add them in the reverse order to the stack:
```
foo(first);
foo(second);
```
has to be replaced by
```
stack.push(second);
stack.push(first);
```