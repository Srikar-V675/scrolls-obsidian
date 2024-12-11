---
aliases:
  - leetcode 525
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[hash tables]]"
  - prefix-sum
difficulty: medium
companies:
  - Amazon
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[hash tables]], prefix-sum

**DIFFICULTY:** medium

**COMPANIES:** 
- Amazon

# Problem Description

**Leetcode Link:** [Contiguous Array - LeetCode](https://leetcode.com/problems/contiguous-array/description/)

**Solution Link:** [Contiguous Array - Leetcode 525 - Python - YouTube](https://youtu.be/agB1LyObUNE?si=PZ39bSbH8Aj9eYBo)

Given a binary array `nums`, return _the maximum length of a contiguous subarray with an equal number of_ `0` _and_ `1`.

**Example 1:**

**Input:** nums = [0,1]
**Output:** 2
**Explanation:** [0, 1] is the longest contiguous subarray with an equal number of 0 and 1.

**Example 2:**

**Input:** nums = [0,1,0]
**Output:** 2
**Explanation:** [0, 1] (or [1, 0]) is a longest contiguous subarray with equal number of 0 and 1.

# Approach
- **Initial Idea**: Considered using either the **sliding window** or **two-pointers** approach:
    - Challenge: No clear way to determine how to move the window or pointers effectively for this problem.
- **Next Thought**: Count the number of `ones` and `zeros` in the array:
    - If there’s a difference, subtract the absolute value of the difference to find the correct subarray.
    - Issue: This approach works only for specific cases and not universally.
- **Inspiration**: The idea of using the difference to identify the correct subarray led to a refined solution.
- **Final Correct Approach**:
    - Use a **hash table** to store the first occurrence of each difference (index).
    - Traverse the array while keeping a running count of `ones` and `zeros`:
        - Calculate the difference at each step.
        - If the difference already exists in the hash table:
            - Determine the length of the subarray by subtracting the index of its first occurrence.
    - This ensures no potential solutions are overlooked.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(N)$

```python
one, zero = 0, 0 
res = 0
diff_map = {}

for i, n in enumerate(nums):
	if n == 0:
		zero += 1
	else:
		one += 1
	diff = one - zero
	if diff not in diff_map:
		diff_map[diff] = i
	if one == zero:
		res = one + zero
	else:
		idx = diff_map[diff]
		res = max(res, i - idx)
return res
```
