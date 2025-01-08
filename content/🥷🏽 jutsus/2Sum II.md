---
aliases:
  - leetcode 167
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[two-pointers]]"
difficulty: medium
companies:
  - Amazon
  - Apple
  - Facebook
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[two-pointers]]

**DIFFICULTY:** medium

**COMPANIES:**
- amazon
- apple
- facebook

# Problem Description

**Leetcode Link:** [2Sum II](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)

Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 <= numbers.length.

Return the indices of the two numbers, index1 and index2, added by one as an integer array [index1, index2] of length 2.

The tests are generated such that there is exactly one solution. You may not use the same element twice.

Your solution must use only constant extra space.

Example 1:
```
Input: numbers = [2,7,11,15], target = 9
Output: [1,2]
Explanation: The sum of 2 and 7 is 9. Therefore, index1 = 1, index2 = 2. We return [1, 2].
```

Example 2:
```
Input: numbers = [2,3,4], target = 6
Output: [1,3]
Explanation: The sum of 2 and 4 is 6. Therefore index1 = 1, index2 = 3. We return [1, 3].
```

Example 3:
```
Input: numbers = [-1,0], target = -1
Output: [1,2]
Explanation: The sum of -1 and 0 is -1. Therefore index1 = 1, index2 = 2. We return [1, 2].
```

# Approach 

I solved this after solving 3Sum, it was easy but I should have done the other way round i.e 2Sum II first and then 3Sum that way solving 3Sum could've been easier.

Since in this problem the array is sorted you just have to use a `2-pointer` approach where you increase or decrease the pointer based on the sum of these two elements at the pointers.

And also since they have also told that there is exactly only one solution for all problems you don't have some other cases to check.

All you have to do is:
- Increment left pointer if curSum is less than target
- Decrement right pointer if curSum is greater than target
- Else return the solution because sum = target.

# Solution

**Time Complexity:** $O(N)$
**Space Complexity:** $1$

```python
l = 0
r = len(nums) - 1
while l < r:
    curSum = nums[l] + nums[r]
    if curSum < target:
        l += 1
    elif curSum > target:
        r -= 1
    else:
        return [l+1, r+1]
```