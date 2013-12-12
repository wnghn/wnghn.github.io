---
layout: post
title: "Condensed Notes: Data Structures"
date: 2013-10-23 14:44
comments: true
categories: 
---
# Linear Structures
##Phisical Implementations

|Compare    |Sequential List|Linked List|
|-----------|:-------------:|:---------:|
|random access  |+  |\- |
|space cost     |+  |\- |
|insert/delete  |\- |+  |
|flexible length|\- |+  |

### Sequential List (Array)
- sort
- binary search
- dynamic programming
>- longest increasing subsequence

### Linked List
- traverse two lists
>- merge sorted list
>- add two numbers

- fast runner/ slow runner in one List
>- Find the start of a loop
>- Find the element right in the middle
>- Judge Palindrome

## Abstract Data Structures

###Stack (LIFO)
The main operations include `push, pop, top`. There are two implementations, array-based stacks and linked stacks. In an array-based stack, the problems of overflow and underflow need to be considered due to the fixed array length. In the implementation of linked stacks, a pointer between two node points from top to bottom.

- calculate arithmetic expressions
>- convert infix expression to postfix expressioin
>- calculate value of postfix expression

- given all elements in pushing order, output all the push/pop possibilities
>- Valid parentheses

- substitute recursion (only recommended when recursion is very space-inefficient)
>- Hanoi Tower

> - Generate all valid parentheses
> - Simplify Unix File Path

###Queue (FIFO)
The main operations include `enqueue, dequeue`. Similar to stack, there are two implementations of a queue, array-based queues and linked queues.
A queues with fixed length can be viewed as a **circular queue**. A typical application is the buffer (data cache area) of emails, requests or messages.

- breadth first search

### String
The main operations are `append, concatenate, find, substring, compare`.

- Exact String Matching: Knuth-Morrit-Pratt (KMP)
- Approximate String Matching: Edit Distance (using DP)

### Skip List

### Hash Table
> - Longest Consecutive Sequence
> - Find out the line that passes through the most points

#Tree Structures
##Binary Tree
The main operations are `left,right`. A binary tree can be implemented using either binary linked list (left,right, =and perhaps parent) or array (only for complete binary trees).

- Depth First Traversal: preorder, inorder and postorder. Each of the order can be implemented with recurrsive OR iterative(stack) method. Note: To implement postorder iteratively, an extra state tag is needed for each tree node.
>- tree height
>- whether symmetric or not
>- whether balanced/complete/full/perfect or not

- Construct tree from preorder(or postorder) and inorder traversal
- Breadth First Traversal. Recursive OR iterative (queue)
- Implement a complete binary tree using array

### Binary Search Tree (BST)
In a BST, the values of node elements are increasing if they are traversed in preorder. A BST can be used to build a tree index.
- search/insert node
- delete node

### Minimum/Maximum Heap
In a minimum heap, the value of every node is no greater than either of its direct children.
- insert (sift up)
- removeMin (sift down)
- delete (sift up + sift down)

### Huffman Tree
Huffman coding is an algorithm for lossless data compression. Each datum (word) is encoded by its prefix code in the huffman tree.
- construction of huffman tree (using maximum frequency heap)
- encoding/decoding

### Red Black Tree

## General Trees & Forests
Common operations for a general tree are `LeftMostChild, rightSibling, childrenSet`. There are three ways to implement a general tree:

1. linked list
    1. store the pointers of all children for each node (in an array or linked list)
    2. maintain two pointers for each node, one to its left most child and the other to its right sibling
    3. maintain a pointer to the parent of a node
2. sequential list
    1. root first traversal order, with a pointer to the right sibling in each node
    2. root first traversal order, with a boolean tag for the existence of sibling in each node
    3. breath first traversal order, with a pointer to the left most child and a boolean tag for sibling in each node
    4. root last traversal order, with the degree of each node

Here are some useful algorithms.

- transform a general tree/forest into a binary Tree
- root first traversal (preorder), root last traversal (inorder), breadth first traversal
>- find previous sibling, find parent
>- delete a tree

### Disjoint-Set Forests
In a disjoint-set forest, each tree represents one set. This structure is usuallly implemented in the 1.3 way. A typical application of it is checking equivalence classes. The algorithms adopted for the disjoint-set problem are:

- union (two trees). The union follows **weighted union rule**
- find (parent) using **path compression**

### Prefix Tree (Trie)
A prefix tree is an ordered tree structure where each top-down path is a string. All the descendants of a node have a common prefix.
>- storing a predictive text or autocomplete dictionary

|Compare    |Prefix Tree|BST|Hash Table|
|-----------|:---------:|:--:|:---------:|
|fuzzy match|+ | | \- |
|alphabetical order|+ | |\- |
|look up time| \- | |+ |

### B Tree, B+ Tree
B(B+) Trees are used for indices.


#Graph Structures
There are three wasys to implement a graph: objects(vertices and edges), adjacency matrix and adjacency lists.

|Compare    |Objects|Matrix|Adjacency Lists|
|-----------|:---------:|:--:|:---------:|
|OO Programming|+ | \- | \- |
|dense graphs| \-| + |\- |
|sparse graphs| + |\- | + |

- Graph Traversal
>- connectivity (number of components)

    - BFS (queue)
    >- shortest path in an unweighted graph
    >- topological sort in an acyclic graph (only push elements with indegree 0)

    - DFS (stack)

- Dijkstra (Greedy, single source), Floyd (3-layer iterations, all sources)
>- shortest path in a non-negative weighted graph

- Prim (Greedy, for sparse graphs), Kruskal (class union, for dense graphs)
>- Minimum Spanning Tree (MST)