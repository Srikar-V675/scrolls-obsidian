---
date: 2024-11-06 00:07
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Searching & Sorting

## Summary
- `Sorting` is the process of rearranging elements either in ascending or descending order in a data structure. 
- `Searching` is the process of looking in a data structure if what we want is present and at what index.

Most sorting algorithms take O(N^2) time complexity and there are some optimised algorithms that take O(n log n). These algorithms are the ones that are used as default sorting algorithms in most programming languages.

A typical search for an element in a data structure would take O(n) time as we are looking into all the elements in the data structure. But an optimal way to do it would be to sort the values first and do a [[Binary Search]] which typically uses O(log n) time by intelligently choosing the right half to search in.

> [!tip]
> Bonus points if you can name the language's default sorting algorithm. <br>
> **Python:** [[Tim Sort]]

### Time complexity

|Algorithm|Time|Space|
|---|---|---|
|Bubble sort|O(n2)|O(1)|
|Insertion sort|O(n2)|O(1)|
|Selection sort|O(n2)|O(1)|
|Quicksort|O(nlog(n))|O(log(n))|
|Mergesort|O(nlog(n))|O(n)|
|Heapsort|O(nlog(n))|O(1)|
|Counting sort|O(n + k)|O(k)|
|Radix sort|O(nk)|O(n + k)|

| Algorithm     | Big-O     |
| ------------- | --------- |
| [[Binary Search]] | O(log(n)) |

### Essential Qs
- [[Binary Search]]
- [Search in Rotated Sorted Array](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Medium/7.%20Search%20Rotated%20Array.md#L4)

## Tasks
- [ ] Learn Heap Sort
- [ ] Learn Counting Sort
- [ ] Learn Radix Sort

---
## Questions
- Which one is better for implementation purposes?

## Key Terms
- **[[Stability of Sorting Algorithms]]:** It determines if the algorithm maintains the original ordering of elements even after sorting.
- **Internal vs External:** Sorting algorithms that use the `RAM` are called internal sorting algorithms and those that use the `disk` are called external sorting algorithms.
- **Comparison vs Non-Comparison:** The name says it all.

## Related Notes
- [[Arrays]]
- [[Strings]]
- [[Quick Sort]]
- [[Merge Sort]]
- [[Quick Sort vs Merge Sort]]
- [[Binary Search]]
- [[Recursion]]

## References(links)
- [Sorting and searching cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/sorting-searching/)
- [Sorting Out The Basics Behind Sorting Algorithms | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/sorting-out-the-basics-behind-sorting-algorithms-b0a032873add)
