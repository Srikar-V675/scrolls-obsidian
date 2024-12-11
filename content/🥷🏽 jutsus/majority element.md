---
aliases:
  - leetcode 169
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
difficulty: easy
companies:
  - Facebook
  - Apple
publish: true
---

**DSA-PATTERNS:** [[arrays]]

**DIFFICULTY:** easy

**COMPANIES:**
- Facebook
- Apple

# Problem Description

**Leetcode Link:** [Majority Element - LeetCode](https://leetcode.com/problems/majority-element/description/)

**Solution Link:** None

Given an array `nums` of size `n`, return _the majority element_.

The majority element is the element that appears more than `⌊n / 2⌋` times. You may assume that the majority element always exists in the array.

**Example 1:**

**Input:** nums = [3,2,3]
**Output:** 3

**Example 2:**

**Input:** nums = [2,2,1,1,1,2,2]
**Output:** 2

# Approach
- You keep a count for a majority element(at first is the first number).
- If you find same number then increment if not decrement, if the count becomes 0 then the new majority element is the current element.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(1)$

```python
c = 1
m = nums[0]

for n in nums:
	if count == 0:
		m = nums[i]
	if n == m:
		count += 1
	else:
		count -= 1
return m
```