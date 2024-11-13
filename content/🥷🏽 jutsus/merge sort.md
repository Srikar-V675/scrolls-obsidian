---
date: 2024-11-06 00:02
sources:
  - "[[arrays]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Merge Sort

## Summary
A Divide & Conquer approach to sorting.

Split the array into 2 halves at every step until they are single elements

Merge the split halves by sorting them.

The splitting takes O(log n) time while the merge takes O(n) time hence time complexity is O(n.log n)

### Complexity
**Time Complexity:** O(n. log n)
Worst, Avg, Best are the same.

**Space Complexity:** O(n) -> because of the auxiliary space used.

![[Merge-Sort-Example.excalidraw.png]]

### Code
```python
from typing import List

def merge(arr: List[int], low: int, mid: int, high: int):
	temp = []
	i = low
	j = mid + 1
	while i <= mid and j <= high:
		if arr[i] <= arr[j]:
			temp.append(arr[i])
			i += 1
		else:
			temp.append(arr[j])
			j += 1
	while i <= mid:
		temp.append(arr[i])
		i += 1
	while j <= high:
		temp.append(arr[j])
		j += 1
	for i in range(low, high+1):
		arr[i] = temp[i - low]


def mergeSort(arr: List[int], low: int, high: int):
	if low < high:
		mid = (low + high) // 2
		mergeSort(arr, low, mid)
		mergeSort(arr, mid+1, high)
		merge(arr, low, mid, high)


arr: List[int] = [54, 29, 93, 17, 77, 31]
print(arr)
mergeSort(arr, 0, len(arr) - 1)
print(arr)
```

---
## Questions
Why is merge sort not better than [[Quick Sort |quick sort]] when merge sort has better time complexity in average? Answer: [[Quick Sort vs Merge Sort]]

## Key Terms
**Auxiliary Space:** extra [[Stack]] space used when recursion takes place.

## Related Notes
[[Arrays]]
[[Quick Sort]]
