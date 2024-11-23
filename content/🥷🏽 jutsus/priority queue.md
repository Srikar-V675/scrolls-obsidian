---
date: 2024-11-07 18:19
sources: "[[heaps]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Priority Queue

A special type of [[queue]] where the higher number(or priority) element is dequeued first giving this [[queue]] a unique rule. Essentially when a new element is added the element is made sure to be moved to the right place in the queue order, while the opposite occurs for removal too(top of [[queue]] should always be highest priority element)

The data stored in [[priority queue]] or [[heaps]] essentially -> `(key, value)` where the key is the priority and the value is the actual data. Since in python `(1, 10)` is considered less than `(2, 0)` this works well for [[heaps implementation]].

[[heap as priority queue]]

---
## Related Notes
[[queue]]
[[heap as priority queue]]

## References(links)
[Heapify All The Things With Heap Sort | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/heapify-all-the-things-with-heap-sort-55ee1c93af82)