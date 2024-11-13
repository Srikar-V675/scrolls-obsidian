---
date: 2024-11-06 00:05
sources:
  - "[[arrays]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Quick Sort

## Summary
Divide and Conquer Algorithm

Quick sort is averagely O(n log n) but not always as the worst case is O(n^2) but [[Merge Sort]] is always O(n log n) so it is slightly better.

### Complexity
**Time**
**Worst Case:** O(n^2)
**Best and Average Case:** O(n log n)
**Space**
O(log n)

## General Steps
Choose pivot element (first, last or random)

Store elements less than pivot in left subarray and vice versa

Call quicksort recursively on left subarray

Call quicksort recursively on right subarray

## Code Steps

Step-1: `Choose` pivot element
Step-2: `Initialise` pointers `i` at start of array and `j` at end of array.
Step-3: `i` index increments until it finds an element that is greater than `pivot`
Step-4: `j` index decrements until it finds an element that is less than `pivot`
Step-5: if `i < j` then `swap(arr[i], arr[j])`
	Put the greater number to the right of pivot and the lesser number to the left of pivot.
Step-6: if `j > i` it indicates that all elements smaller than pivot are to the left and vice verse.
	`swap(arr[pivot], arr[j])`
Step-7: `Split` the array by `pivot` into `left` and `right subarrays`.
Step-8: `Repeat` Steps 1 to 7 for left subarray.
Step-9: `Repeat` Steps 1 to 7 for right subarray.

## Code

```python
from typing import List

def quickSort(arr: List[int], left: int, right: int):
	if left < right:
		partition = findPartition(arr, left, right)
		quickSort(arr, left, partition-1)
		quickSort(arr, partition+1, right)


def findPartition(arr: List[int], left: int, right: int) -> int:
	pivot = left
	i = left
	j = right
	while i < j:
		while i <= j and arr[i] <= arr[pivot]:
			i += 1
		while i <= j and arr[j] >= arr[pivot]:
			j -= 1
		if i < j:
			arr[i], arr[j] = arr[j], arr[i]
	arr[pivot], arr[j] = arr[j], arr[pivot]
	return j

arr: List[int] = [54, 29, 93, 17, 77, 31]
quickSort(arr, 0, 5)
print(arr)
```


![[Quick Sort Example.png]]


> [!important]
> `i <= j` must be used inside the while loop because we need to `stop the iteration` as soon as `i and j cross each other` and `not go on` until the condition is satisfied.

## Questions
Which is better merge or quick sort? A: [[Quick Sort vs Merge Sort]]

## Related Notes
[[Arrays]]
[[Merge Sort]]
