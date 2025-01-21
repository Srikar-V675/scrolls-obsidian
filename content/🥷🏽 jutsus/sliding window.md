---
date: 2024-11-06 00:08
tags:
  - zettel
  - dsa
status: literature
publish: true
---
**SOURCE:** [[arrays]]

**LINKS:**
- [Subarray Sum - Fixed](https://algo.monster/problems/subarray_sum_fixed)
- [AlgoMonster: The Structured Path to Success on LeetCode Data Structure & Algorithm Interviews](https://algo.monster/templates)

Variant of same direction [[two-pointers]] problems. Function performs on the entire interval rather than just the two positions. Keep track of the value of the window and slide the window along the array.

### Steps
- Compute the initial result of the window.
- Slide the window along the array either by increasing right or left or both.
- Recompute the result and check if optimal conditions is met.
- Else continue

### Problems
- Substring
- Subarray
- max/longest sequence
- subsequence

### Template

**Fixed Window:**
```python
def sliding_window(input, window_size):
	ans = 0
	for i in range(window_size):
		ans = compute ans
	optimal_ans = ans
	for right in range(window_size, len(input)):
		left = right - window_size
		remove input[left] from window(ans)
		add input[right] from window(ans)
		optimal_ans = optimal(ans, optimal_ans)
	return optimal_ans
```
