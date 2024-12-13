---
date: 2024-11-06 00:12
sources:
  - "[[Searching & Sorting]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Tim Sort
---
## Summary
- Tim sort is a hybrid, stable sorting algorithm designed by Tim Peters in 2002, it combines merge and insertion sort to efficiently sort.

### Detailed Explanation

- Let's try to understand why the need for a new sorting algorithm was there?
- Before we try to get to the point, we need to know that in [[runtime to algo]] there is a catch i.e it denotes only the highest degree and ignores constants.
- While [[Merge Sort]], [[Quick Sort]], and Heap Sort are all sorting algos that execute in O(n.log n) time they have differed constants which can make one better than the other in certain situations.
- **Time Complexity:** O(C. n. log n + ....)
	- Where `C` is:
		- high for [[Quick Sort]] -> Cq = left, right, pivot... but it has `locality of reference`
		- low for [[Merge Sort]] but it needs O(n) extra auxiliary space
		- high for Heap Sort, even though it needs no extra space but it has no `locality of reference` because the compiler doesn't know which index it will next access

> [!info]
> Among sorting techniques that take `O(n^2` time, insertion sort is an algo that has:
> - (Ci. n^2) < (C. n.log n) for smaller input size usually between 32 to 64.
> - Hence Insertion sort is used in Tim Sort by taking this into account.

### Idea
- The idea of Tim Sort is to combine the power of `insertion sort` for small data and the merging of [[Merge Sort]].
- Let's take this progressively, I'll take examples or explain concepts from the basic overview of Tim sort to detailed overview.
- The basic idea of Tim sort is:
	- **Step-1:** split the data structure into equal size chunks of size 32 to 64. Chunks -> Runs
	- **Step-2:** chunks are sorted using `insertion sort` (as `insertion sor`t is fast for smaller sizes between 32 to 64)
	- **Step-3:** these sorted chunks are now recursively merged like in [[Merge Sort]].
- The advantage is that when using [[Merge Sort]] we are getting down the splits into size 2 or 1 but in the case of splitting them into equal chunks of 64 (example) we can reduce the tree depth by five levels because 64 = 2^6.

![[Tim-Sort-Basic-Example.excalidraw.png]]

- But this is still not fully efficient, so Tim Peters came up with a new idea where he will intelligently split the chunks into sizes between 32 to 64 instead of directly doing it which cause some localities to be missed.
- At the same time he came across the idea of splitting into chunks by sorting it by using [[Binary Insertion Sort]].

![[Tim-sort-example.excalidraw.png]]

- In this example, we have first divided the array into chunks by using [[Binary Insertion Sort]] and then recursively merged them with the [[Merge Sort]] logic.
- Why is this better than splitting into fixed chunk sizes because it decreases the number of chunks by combining subarrays that follow increasing or decreasing order making it easy to group chunks that have most elements in order. 
- And it makes sure to take advantage of [[Binary Insertion Sort]] which is optimal for the defined chunk size (32 - 64).
- This ultimately decreases the number of chunks to merge and also the tree depth.
- If we had split the array it equal chunks of size 3 then we would have got 4 but by using [[Binary Insertion Sort]] we got only 3.

### Time Complexity

| **Algorithm** | **Time Complexity** |             |             |
| ------------- | ------------------- | ----------- | ----------- |
|               | Best                | Average     | Worst       |
| [[Quick Sort]]    | Ω(n*log(n))         | θ(n*log(n)) | O(n^2)      |
| [[Merge Sort]]    | Ω(n*log(n))         | θ(n*log(n)) | O(n*log(n)) |
| Tim Sort      | Ω(n)                | θ(n*log(n)) | O(n*log(n)) |

---
## Key Terms
- **Locality of Reference:** It is a phenomenon where the compiler can cache the access to elements based on the pattern of accessing elements in the algo.

## Related Notes
- [[Searching & Sorting]]
- [[Merge Sort]]
- [[Arrays]]
- [[Strings]]
- [[Recursion]]
- [[Binary Insertion Sort]]

## References(links)
- [The FASTEST sorting algorithm: Part 1 - TimSort - YouTube](https://www.youtube.com/watch?v=emeME__917E)
- [The FASTEST sorting algorithm: Part 2 - Binary Insertion Sort - YouTube](https://www.youtube.com/watch?v=6DOhQyqAAvU)
- [Tim Sort - javatpoint](https://www.javatpoint.com/tim-sort)
- [Tim Sort. Introduction and Background | by Muskan Vaswan | Medium](https://muskanvaswan.medium.com/tim-sort-48bffd550a9b)
- [TimSort - Data Structures and Algorithms Tutorials - GeeksforGeeks](https://www.geeksforgeeks.org/timsort/)