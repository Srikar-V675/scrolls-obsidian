---
date: 2024-11-05 23:45
sources: "[[arrays]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Binary Search

## Summary
Search sorted array

At every step the search space becomes half making it efficient for searching in sorted array

This Algo can be used not only for searching sorted [[Arrays]] but also whenever a binary decision has to be made to shrink search space.

### Complexity
**Time Complexity:** O(log n)

**Space Complexity:** O(1)

### Vanilla Binary Search
Original implementation of binary search

```python
from typing import List

def binary_search(arr: List[int], target: int) -> int:
	left, right = 0, len(arr) - 1
	while left <= right:
		mid = (left + right) // 2
		if arr[mid] > target:
			right = mid - 1
		elif arr[mid] < target:
			left = mid + 1
		else:
			return mid+1
	return -1 

arr: List[int] = [23, 45, 46, 67, 88]
target = int(input("Enter target: "))
print("Index: ", binary_search(arr, target))
```


### Mod Binary Search
It is a binary search that can be used for mods with different conditions rather than a simple search.

```python
def binary_search(arr: List[int], target: int) -> int:
	left, right = 0, len(arr) - 1
	index = -1 
	while left <= right:
		mid = (left + right) // 2
		if feasible(mid):
			index = mid
			right = mid - 1
		else:
			left = mid + 1
	return index
```

## Questions
Can binary search be modified for different use cases that involve binary decisions? A: Yes

## Related Notes
[[Arrays]]

## References(links)
[Vanilla Binary Search](https://algo.monster/problems/binary_search_intro)
[First True in a Sorted Boolean Array](https://algo.monster/problems/binary_search_boundary)
