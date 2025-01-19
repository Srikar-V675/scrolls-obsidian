---
aliases:
  - leetcode 560
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[hash tables]]"
  - prefix-sum
difficulty: medium
companies:
  - Facebook
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[hash tables]], prefix-sum

**DIFFICULTY:** medium

**COMPANIES:**
- facebook

# Problem Description

**Leetcode Link:** [Subarray Sum Equals K - LeetCode](https://leetcode.com/problems/subarray-sum-equals-k/description/)

**Solution Link:** [Subarray Sum Equals K - Prefix Sums - Leetcode 560 - Python - YouTube](https://www.youtube.com/watch?v=fFVZt-6sgyo)

Given an array of integers `nums` and an integer `k`, return _the total number of subarrays whose sum equals to_ `k`.

A subarray is a contiguous **non-empty** sequence of elements within an array.

**Example 1:**

```
Input: nums = [1,1,1], k = 2
Output: 2
```

**Example 2:**

```
Input: nums = [1,2,3], k = 3
Output: 2
```

# Approach
- I have done this before so it was easy for me. 
- From the patterns we can recognise how we can go ahead with this problem.
- We need a [[hash tables]] to solve this problem and why? because we need a way of storing the prefix sums and their counts.
- why do we need prefix-sum? because of the fact that if the `curSum - k` has occurred somewhere before in the array then that means we have a solution and if we know that count then we have the exact number of solutions we have.
- To make it understandable run the below solution code for the input:
```
nums = [0, 0, 0, 0, 0]
k = 2
output = 15
```

- if you do the dry run for the above input you will realise why we also need the counts of the prefix-sum occurrences.
- and in the code you can see that we have initialized the [[hash tables]] with a default value i.e `{ 0: 1 }` this will helpful for when we actually find the solution that is sum of k directly from start.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(N)$

```python
hashmap = { 0: 1 }
res = 0
prefix = 0

for num in nums:
	prefix += num 
	diff = prefix - k
	res += hashmap.get(diff, 0)
	hashmap[prefix] = 1 + hashmap.get(prefix, 0)

return res
```