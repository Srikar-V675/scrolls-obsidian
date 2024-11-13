---
aliases:
  - leetcode 1
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[hash tables]]"
difficulty: easy
companies:
  - FAANG
  - Uber
  - Twitter
  - Adobe
  - Atlassian
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[hash tables]]
**DIFFICULTY:** easy
**COMPANIES:** 
- FAANG
- Uber
- Twitter
- Adobe
- Atlassian

# Problem Definition
**Link:** [Leetcode](https://leetcode.com/problems/two-sum/description/)

Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

Example 1:

    Input: nums = [2,7,11,15], target = 9
    Output: [0,1]
    Explanation: Because nums + nums[1] == 9, we return [0, 1].

Example 2:

    Input: nums = [3,2,4], target = 6
    Output: [1,2]

Example 3:

    Input: nums = [3,3], target = 6
    Output: [0,1]

Constraints:

    2 <= nums.length <= 10^4
    -10^9 <= nums[i] <= 10^9
    -10^9 <= target <= 10^9
    Only one valid answer exists.

# Approach

The goal is to identify two numbers in the array that sum up to the specified target. Initially, I overlooked a crucial constraint stating that "only one valid answer exists," which is essential for guiding our approach.

## Brute Force

The simplest method involves using a nested loop to check every possible pair of numbers in the array. This brute force solution has a time complexity of $$O(n^2)$$, which can be inefficient for larger datasets.

## Improved Approach

A more efficient solution utilizes a hashmap to store elements as key-value pairs in the format `element : index`. By iterating through the array once more, we can check if each element's complement (i.e., `target - current element`) exists in the hashmap. 

Initially, I was concerned about handling duplicates. However, since the problem guarantees only one valid answer, if one of the duplicates were part of the solution, the other must also be its duplicate.

This method operates in two passes:
- **Pass 1:** Populate the hashmap with elements.
- **Pass 2:** Search for pairs that meet the criteria.

## Optimal Solution

This approach can be further optimized to complete in a single pass. We first check if the complement of the current element exists in the hashmap. If it does, we return the indices immediately. If not, we add the current element to the hashmap and continue searching.

# Code

**Time Complexity:** $$O(N)$$

**Space Complexity:** $$O(N)$$

```python
def twoSum(nums: List[int], target: int) -> List[int]:
    map = {}
    if nums[0] + nums[1] == target:
        return [0, 1]
    for i, num in enumerate(nums):
        second = target - num
        if second in map:
            return [i, map[second]]
        map[num] = i
```