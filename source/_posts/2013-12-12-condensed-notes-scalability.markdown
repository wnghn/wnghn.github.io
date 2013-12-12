---
layout: post
title: "Condensed Notes: Scalability"
date: 2013-12-12 16:16
comments: true
categories: 
---

# Memory Limit with a Single Machine
- replacement selection sorting
> Given memory m, generate a sorted file of size 2m in average.

- external merge sort (2-way, k-way merge with winner tree)

- block search with index table

# Scalability with a Distributed System

## Steps to Solve Scalability Problem
1. solve it when there is no memory limits 
1. Split the data set
  - by order of appearance, for time series
  - by hash value, for independent entries
  - by actual value, for geographically grouped entries
  - arbitrarily, then maintain a lookup table
1. Solve the problem on each machine, then merge the result

## Issues
- load balancing among machines

