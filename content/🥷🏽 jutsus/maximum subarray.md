---
aliases:
  - leetcode 53
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
difficulty: medium
companies: 
publish: true
---

**DSA-PATTERNS:** [[arrays]]

**DIFFICULTY:** medium

**COMPANIES:**
- 

# Problem Description

**Leetcode Link:** [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/description/)

Given an integer array nums, find the 
subarray
 with the largest sum, and return its sum.

Example 1:
```
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: The subarray [4,-1,2,1] has the largest sum 6.
```

Example 2:
```
Input: nums = [1]
Output: 1
Explanation: The subarray [1] has the largest sum 1.
```

Example 3:
```
Input: nums = [5,4,-1,7,8]
Output: 23
Explanation: The subarray [5,4,-1,7,8] has the largest sum 23.
```

# Approach

As we need the maximum sum subarray we can think of `currentSum = -1` being non-desirable, as it would just decrease the sum value. 

Hence we need to make currentSum = 0 as soon as it becomes -ve but before it becomes 0 we need to check for max. Since if the array contains only -ve values then it maximum sum would be negative to make sure we store the -ve max sum too we need to change currentSum to 0 after the max check.

# Solution

**Time Complexity:** O(N)
**Space Complexity:** O(1)

```python
currentSum = 0
maxSum = float('-inf') # because of maximum negative sum being possible.
for num in nums:
    currentSum += num
    if currentSum > maxSum:
        maxSum = currentSum
    if currentSum < 0:
        currentSum = 0
return maxSum
```