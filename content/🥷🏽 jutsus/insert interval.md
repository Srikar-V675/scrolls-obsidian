---
aliases:
  - leetcode 57
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[intervals]]"
difficulty: medium
companies:
  - Microsoft
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[intervals]]

**DIFFICULTY:** medium

**COMPANIES:**
- microsoft

# Problem Description

**Leetcode Link:** [Insert Interval - LeetCode](https://leetcode.com/problems/insert-interval/description/)

**Solution Link:** [Insert Interval - Leetcode 57 - Python - YouTube](https://www.youtube.com/watch?v=A8NUOmlwOlM) 

You are given an array of non-overlapping intervals `intervals` where `intervals[i] = [starti, endi]` represent the start and the end of the `ith` interval and `intervals` is sorted in ascending order by `starti`. You are also given an interval `newInterval = [start, end]` that represents the start and end of another interval.

Insert `newInterval` into `intervals` such that `intervals` is still sorted in ascending order by `starti` and `intervals` still does not have any overlapping intervals (merge overlapping intervals if necessary).

Return `intervals` _after the insertion_.

**Note** that you don't need to modify `intervals` in-place. You can make a new array and return it.

**Example 1:**

**Input:** intervals = [[1,3],[6,9]], newInterval = [2,5]
**Output:** [[1,5],[6,9]]

**Example 2:**

**Input:** intervals = [[1,2],[3,5],[6,7],[8,10],[12,16]], newInterval = [4,8]
**Output:** [[1,2],[3,10],[12,16]]
**Explanation:** Because the new interval [4,8] overlaps with [3,5],[6,7],[8,10].

# Approach
- My mistake was to think in only one case and that was they can overlap or not, I didn't think of the fact that we need to insert at the right place even if it is not overlapping and also overlooked the fact that the intervals are sorted and not overlapping.
- There are 3 cases:
	1. newInterval is not overlapping and is before one of the intervals - this means that we need to append this newInterval to the `res` and other intervals because there can be no potential overlaps.
	2. newInterval is not overlapping but is after one of the intervals - this means that w can append the current interval to `res` but since there are still intervals left that means there is a potential chance of overlapping
	3. overlapping is present - this means we can update the newInterval after merging but can't add to the `res` yet because there can be other intervals that are overlapping with the merged newInterval.
- We need to iterate over the whole intervals array and check the above 3 cases, if by any chance we encounter the case-1 we can return the `res + intervals[i:]`.
- And we need to add the newInterval at the end of the `res` because we can notice that we have never explicitly appended it to the `res`.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(N)$

```python
res = []

for i, interval in enumerate(intervals):
	if newInterval[1] < interval[0]:
		res.append(newInterval)
		return res + intervals[i:]
	elif interval[1] < newInterval[0]:
		res.append(interval)
	else:
		newInterval = [min(interval[0], newInterval[0]), max(interval[1], newInterval[1])]

res.append(newInterval)
return res
```