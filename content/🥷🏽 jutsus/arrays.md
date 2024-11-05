---
date: 2024-11-05 23:33
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Arrays

### Summary

Arrays are a linear data structure, that can store a single type of datatype. It is a contagious datatype that allows for constant time retrieval.

### Common Terms

1. SubArray - It is a slice of an array. It has to follow the same order of elements, but it doesn't have to be the same length of original array. 
> [!example]
> For the array `[2, 3, 6, 1, 5, 4]`, `[3, 6, 1]` is a subarray while `[3, 1, 5]` is not a subarray.

2. SubSequence - It is an sequence that follows the order of elements from left to right but not strictly and it is not a slice of the array. 
> [!example]
> For the array `[2, 3, 6, 1, 5, 4]`, `[3, 1, 5]` is a subsequence but `[3, 5, 1]` is not a subsequence.


### Time Complexity

|       Operation       |   Big-O   | Note                                                                                                 |
|:---------------------:|:---------:|:---------------------------------------------------------------------------------------------------- |
|        Access         |   O(1)    |                                                                                                      |
|        Search         |   O(n)    |                                                                                                      |
| Search (sorted array) | O(log(n)) |                                                                                                      |
|        Insert         |   O(n)    | Insertion would require shifting all the subsequent elements to the right by one and that takes O(n) |
|  Insert (at the end)  |   O(1)    | Special case of insertion where no other element needs to be shifted                                 |
|        Remove         |   O(n)    | Removal would require shifting all the subsequent elements to the left by one and that takes O(n)    |
|  Remove (at the end)  |   O(1)    | Special case of removal where no other element needs to be shifted                                   |

### Techniques

[[Sliding-Window]]
[[Two-Pointers]]
Traversing from the right
[[Binary Search]] if array is sorted/partially sorted
Pre-computation - prefix sum, postfix sum etc.
Traversing array more than once - still O(N)
Queue/Dequeue
[[Stack]]

### Essential Qs
[2Sum](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Easy/6.%202Sum.md#L4)
[Best Time to Buy & Sell Stock](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Easy/8.%20Best%20Time%20to%20Buy%20%26%20Sell%20Stock.md#L4)
[Product of Array Except Self](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Medium/2.%20Product%20Except%20Self.md#L4)
[Maximum Subarray](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Medium/5.%20Maximum%20Subarray.md#L4)

### Recommended Qs
[Maximum Product Subarray](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Medium/6.%20Maximum%20Product%20Subarray.md#L4)
[Search in Rotated Sorted Array](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Medium/7.%20Search%20Rotated%20Array.md#L4)
[3Sum](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Medium/8.%203Sum.md#L4)
[Container with Most Water](https://github.com/Srikar-V675/DSA-Problems/blob/e67b5124b26c39cb0cc13f1c5b65e0f52f927021/Arrays%20%7C%20Strings/Medium/11.%20Container%20with%20Most%20Water.md)
[Sliding Window Maximum](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Hard/1.%20Sliding%20Window%20Maximum.md#L4)

### Related Notes
[[Quick Sort]]
[[Merge Sort]]
[[Binary Search]]
[[Two-Pointers]]
[[Sliding-Window]]

### References(links)
[Array cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/array/#introduction)

