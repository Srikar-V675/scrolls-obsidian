---
date: 2024-11-05 23:58
sources:
  - "[[hash functions]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Linear Probing

### Summary
Linear probing is a ==collision resolution tactic== used in [[hash tables]]. It is an open addressing tactic. If there is a collision then the ==algorithm searches for the next free bucket linearly==.

A collision occurs when the [[hash functions]] generates the same bucket for two keys. To tackle this we can use linear probing, when a collision occurs the algorithm searches for the next unoccupied bucket linearly. 

> If a unoccupied bucket is not found and we have reached the end then the ==probe cycles to the first slot== to search for the unoccupied slot.

![[Linear-Probing-Example.excalidraw.png]]
### Problems 
*Clustering:* occurs when we have lots of keys that ==belong to the same hash bucket== according to the [[hash functions]]. Because of this the slots after the actual bucket is filled with values.

Use *linear probing* when we have a ==well-defined [[hash functions]] and a big hash table== to accommodate collisions. 

Do not use *linear probing* if you have many keys that belong to the same hash bucket.

---
### Related Notes
[[hash tables]]
[[hash functions]]
[[Arrays]]
[[chaining]]

### References(links)
[Hash Table (Closed Addressing: Separate Chaining and Open Addressing: Linear Probing, Quadratic Probing, Double Hashing) - VisuAlgo](https://visualgo.net/en/hashtable)