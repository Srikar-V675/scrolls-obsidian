---
date: 2024-11-05 23:44
sources: "[[Tim Sort]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Binary Insertion Sort

## Summary
Binary Insertion Sort is an essential part of [[Tim Sort]] and that is the reason why I came across it while learning [[Tim Sort]].

As the name suggests it is a combination of [[Binary Search]] and `insertion sort`.

### Idea
Since we know [[Binary Search]] takes O(log n) time to execute. This Sorting algo takes that to advantage by using it to find the right index at which the new element should be so that `insertion sort` can be used to insert the element at that index and the following elements are pushed.

In `insertion sort` alone, the algorithm finds the right index by comparing each element which takes more time and expensive operations.

### Steps
1. If the elements are already in increasing order it will keep going forward until it finds an element that violates it.
2. Use binary search to find the right index at which the violating element should be present since we know the elements previous to violating element are sorted.
3. Now use `insertion sort` to insert the violating element at that index and push the following elements forward.

![[content/03-resources/Excalidraw/binary insertion sort.png]]

---
## Related Notes
[[Tim Sort]]
[[Binary Search]]

## References(links)
[The FASTEST sorting algorithm: Part 2 - Binary Insertion Sort - YouTube](https://www.youtube.com/watch?v=6DOhQyqAAvU)
