---
date: 2024-11-05 23:48
sources: "[[hash functions]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Chaining

### Summary
Chaining is a ==collision resolution tactic== used in [[hash tables]]. It is a ==closed addressing tactic==. Unlike [[linear probing]] which utilises the other buckets if there is a collision, chaining ==implements a [[Linked List]] at the collision bucket to store the collisions==.

When there is a collision with the bucket computed by the [[hash functions]], this method uses a [[Linked List]] at the collision bucket to store the collision values.

![[content/03-resources/Excalidraw/Chaining-Example.excalidraw.png]]

### Problems 
*Linear Search Time:* if most of the values belong to a single bucket then the ==search for a value becomes equal to or close to linear time==, which defeats the reason of having a [[hash tables]]

Use *chaining* when we have a ==well-defined [[hash functions]] that distributes the values uniformly== making the search time average out to constant time. 

---
### Related Notes
[[hash tables]]
[[hash functions]]
[[linear probing]]
[[Arrays]]
[[Linked List]]

### References(links)
[Hash Table (Closed Addressing: Separate Chaining and Open Addressing: Linear Probing, Quadratic Probing, Double Hashing) - VisuAlgo](https://visualgo.net/en/hashtable)