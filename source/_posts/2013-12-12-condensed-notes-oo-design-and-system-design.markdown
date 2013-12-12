---
layout: post
title: "Condensed Notes: OO Design and System Design"
date: 2013-12-12 12:13
comments: true
categories: 
---
# OO Design

## 4 Major Principles
- **Abstraction**: decomposing a complex system and hiding the complexity by defining the most semantically appropriate classes (states and behaviors)
- **Encapsulation**: hiding data implementation by restricting access to accessor (getter) and
mutator (setter)
- **Inheritance**: the “is a” relationship
- **Polymorphism**: same function name, different behaviors
  * ad hoc polymorphism (function overloading)
  * subtype polymorphism (function overwriting)

## Steps
1. Handle Ambiguity
1. Define the Core Objects
1. Analyze Relationships
1. Investigate Actions

## Design Pattern
- Singleton Class
- Factory Method


# System Design

## Design of a Data Query Service
Data storage:

- text files
- in XML or JSON format
- in a relational database
- in a distributed file system 

Interface
- let clients send query strings (regex, xpath, sql, hive)
- implement a web interface to support limited queries

## Issues with distributed systems
- smart division of data
- reduce machine jumps
- for search: use a bit vector or hashtable to mark visited nodes
- influence of server failure
- take advantage of cache