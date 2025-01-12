---
aliases:
  - leetcode 39
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[recursion]]"
difficulty: medium
companies:
  - Amazon
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[recursion]]

**DIFFICULTY:** medium

**COMPANIES:**
- amazon

# Problem Description

**Leetcode Link:** [Combination Sum - LeetCode](https://leetcode.com/problems/combination-sum/)

**Solution Link:** [NeetCode](https://neetcode.io/problems/combination-target-sum)

Given an array of **distinct** integers `candidates` and a target integer `target`, return _a list of all **unique combinations** of_ `candidates` _where the chosen numbers sum to_ `target`_._ You may return the combinations in **any order**.

The **same** number may be chosen from `candidates` an **unlimited number of times**. Two combinations are unique if the frequency of at least one of the chosen numbers is different.

The test cases are generated such that the number of unique combinations that sum up to `target` is less than `150` combinations for the given input.

**Example 1:**

**Input:** candidates = [2,3,6,7], target = 7
**Output:** [[2,2,3],[7]]
**Explanation:**
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.

**Example 2:**

**Input:** candidates = [2,3,5], target = 8
**Output:** [[2,2,2,2],[2,3,3],[3,5]]

**Example 3:**

**Input:** candidates = [2], target = 1
**Output:** []

# Approach
![[combination-sum-dt.excalidraw.svg]]

- **Sorting the Array**: Sorting ensures we process numbers in ascending order, avoid duplicates, and stop recursion early when the total exceeds the target.
- **For Loop for Choices**: The `for` loop runs from `start` to the end of the array. It ensures:
    - We explore each candidate from the current position onward, maintaining order.
    - We allow the same element to be reused by keeping the loop index unchanged (`dfs(i, ...)`).
- **Recursive Backtracking**:
    - Include the current number in the combination and recursively search for further possibilities.
    - Backtrack by removing the current number and let the `for` loop naturally move to the next candidate.
- **Base Cases**:
    - If the total matches the target, save the current combination.
    - If the total exceeds the target, stop further exploration.
- **Mistake in My Approach**: I overcomplicated the logic by manually deciding how to update the index (`i`). The `for` loop inherently handles the sequence correctly, and there’s no need for extra conditions. This problem is similar to generating combinations but allows starting from the same index for reuse.
- It is very similar to [[combinations]] where we go from `start+1` to end but in this case we go from `start` to end.

# Solution 

**Time Complexity:** 

**Space Complexity:**

```python
res = []
nums.sort()

def dfs(start, combi, total):
	if total == target:
		res.append(combi.copy())
		return

	for i in range(start, len(nums)):
		if total + nums[i] > target:
			return
		combi.append(nums[i])
		dfs(start, combi, total + nums[i])
		combi.pop()

dfs(0, [], 0)
return res
```