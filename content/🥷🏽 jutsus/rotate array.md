---
aliases:
  - leetcode 189
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
difficulty: medium
companies:
  - Google
publish: true
---

**DSA-PATTERNS:** [[arrays]]

**DIFFICULTY:** medium

**COMPANIES:**
- Google

# Problem Description

**Leetcode Link:** [Rotate Array - LeetCode](https://leetcode.com/problems/rotate-array/description/)

**Solution Link:** None

Given an integer array `nums`, rotate the array to the right by `k` steps, where `k` is non-negative.

**Example 1:**

**Input:** nums = [1,2,3,4,5,6,7], k = 3
**Output:** [5,6,7,1,2,3,4]
**Explanation:**
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]

**Example 2:**

**Input:** nums = [-1,-100,3,99], k = 2
**Output:** [3,99,-1,-100]
**Explanation:** 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]

# Approach
- It is simple you need to reverse the whole array first and then reverse the first k elements and then the after k elements.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(1)$

```python
k = k % len(nums)
nums.reverse()
nums[:k] = reversed(nums[:k])
nums[k:] = reversed(nums[k:])
```