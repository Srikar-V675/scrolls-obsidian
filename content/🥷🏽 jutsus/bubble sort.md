---
date: 2024-11-05 23:47
sources: "[[Searching & Sorting]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Bubble Sort

## Captures
It is one of the most common sorting techniques that is taught first when you are learning about sorting. It is also the most intuitive and simple way that comes to mind when you think of sorting. 

In bubble sort, we check the `i and i+1` element in an [[Arrays]] to see if it in the order (ascending or descending) and swap it if it is not in order. 

```
[5, 4, 1, 2, 3]
we swap 5 and 4 because there are not in ascending order. 
```

We need to repeat this process of checking neighbour elements for a maximum of the [[Arrays]] size.

Every time we finish one iteration the greatest element in the array (for ascending) will be put in its position which is the last index. So every iteration the array gets sorted from the end and hence we need `n` iterations if there are `n` elements to sort. 

You may not need `n` iterations for every [[Arrays]] because sometimes an [[Arrays]] is sorted partially and this helps the algorithm sort the whole [[Arrays]] way earlier. We can detect this by checking if there was any swap in the inner loop while checking neighbouring elements. If there was no swaps then that means that the [[Arrays]] is sorted. 

## Code
```python
def bubble(arr):
	for i in range(n):
		swapped = False # to check if arr is sorted early on.
		for j in range(n-i-1): # not consider the elements at the end that got sorted.
			if arr[j] > arr[j+1]:
				swapped = True
				arr[j], arr[j+1] = arr[j+1], arr[j]
		if not swapped:
			break # array is sorted early on.

arr = [5, 4, 1, 2, 3] # sorted: [1, 2, 3, 4, 5]
bubble(arr)
```

---
## Related Notes
[[Arrays]]
[[Searching & Sorting]]

## References(links)
gfg