---
date: 2024-11-05 23:54
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Hash Tables

## Summary
It is a ==data structure that maps keys to values and enabling O(1) lookup== by the key. It allows us to search for an item in an array in O(1) time which usually takes ==O(N) time for unsorted== array and ==O(log N) time for a sorted== array.

## Detailed Explanation
#### Scenario: 
Let's say we have a library of books and I want to search for a book, a traditional way would essentially be searching through all the books in library or if the books are sorted then we look in the right half and narrow it down. But isn't this super inconvenient, imagine having 1000 books and using these traditional ways to search for a book. The need for a data structure that allows us to access or search a book directly is needed -> O(1) access.

#### Solution:
A `hashmap` data structure that can help us do this. 

A hashmap has two main parts:
> *[[Arrays]]* - used to store the data aka books
   *[[hash functions | Hash Function]]* - used to create a mapping that decides where our data is


**What makes a good hash table?**
> Easy to compute hash function
> Avoid collisions
> Should use all input data and must return the same value for a given input

#### Collision Resolution Tactics
We know we can't avoid collisions but we can efficiently handle them. We have 2 main types:

**Open Addressing** - When an element has to be inserted, it examines the bucket for the input values, if that bucket is occupied then it uses some kind of ==probe sequence to find the next unoccupied slot in the table==.
>  [[linear probing]]

**Closed Addressing** - Implements a ==new data structure where if there is a collision then that data structure is extended== at that bucket (i.e Linked List).
> [[chaining]]


### Time Complexity

|Operation|Big-O|Note|
|---|---|---|
|Access|N/A|Accessing not possible as the hash code is not known|
|Search|O(1)*||
|Insert|O(1)*||
|Remove|O(1)*||
_* This is the average case, but in interviews we only care about the average case for hash tables._

### Sample questions

^68cede

Describe an implementation of a least-used cache, and big-O notation of it.

A question involving an API's integration with hash map where the buckets of hash map are made up of linked lists.

### Essential Qs
[2Sum](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Easy/6.%202Sum.md#L4)
[Ransom Note](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Easy/11.%20Ransom%20Note.md#L4)

---
### Tasks
- [ ] Research the [[#^68cede  |Sample Questions]] more 

### Key Terms
*Hash function:* The algorithm that decides the hash bucket of a input value
*Hash bucket:* The index of a hash table that holds the value of a key
*Collision:* When two input values given to a hash function result in the same hash bucket

### Related Notes
[[Arrays]]
[[Strings]]
[[hash functions]]
[[linear probing]]
[[chaining]]
[[Linked List]]

### References(links)
[Hash table cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/hash-table/#introduction)
[Taking Hash Tables Off The Shelf. Truth time: learning about theoretical… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/taking-hash-tables-off-the-shelf-139cbf4752f0)