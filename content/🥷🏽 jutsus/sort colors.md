---
aliases:
  - leetcode 75
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[hash tables]]"
difficulty: medium
companies:
  - Facebook
  - Apple
  - Amazon
  - Zoho
  - Cisco
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[hash tables]]

**DIFFICULTY:** medium

**COMPANIES:**
- Facebook
- Apple
- Amazon
- Zoho
- Cisco

# Problem Description

**Leetcode Link:** 
```cardlink
url: https://leetcode.com/problems/sort-colors/description/
title: "Sort Colors - LeetCode"
description: "Can you solve this real interview question? Sort Colors - Given an array nums with n objects colored red, white, or blue, sort them in-place [https://en.wikipedia.org/wiki/In-place_algorithm] so that objects of the same color are adjacent, with the colors in the order red, white, and blue.We will use the integers 0, 1, and 2 to represent the color red, white, and blue, respectively.You must solve this problem without using the library's sort function. Example 1:Input: nums = [2,0,2,1,1,0]Output: [0,0,1,1,2,2]Example 2:Input: nums = [2,0,1]Output: [0,1,2] Constraints: * n == nums.length * 1 <= n <= 300 * nums[i] is either 0, 1, or 2. Follow up: Could you come up with a one-pass algorithm using only constant extra space?"
host: leetcode.com
image: https://leetcode.com/static/images/LeetCode_Sharing.png
```

**Solution Link:**  None

Given an array `nums` with `n` objects colored red, white, or blue, sort them **[in-place](https://en.wikipedia.org/wiki/In-place_algorithm)** so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

We will use the integers `0`, `1`, and `2` to represent the color red, white, and blue, respectively.

You must solve this problem without using the library's sort function.

**Example 1:**

**Input:** nums = [2,0,2,1,1,0]
**Output:** [0,0,1,1,2,2]

**Example 2:**

**Input:** nums = [2,0,1]
**Output:** [0,1,2]

# Approach
- It is a very simple approach, we know we have to sort 3 numbers -> `0, 1, 2`. And we only need to sort 3 numbers.
- We can take an approach where we can put the `zeros` and the `twos` at the right place which is at the ends of the [[arrays]] and automatically `ones` will be sorted. 
- We need three pointers for this solution, one pointer for the position of zero, one for the position of two and one for tracking the current number.
- We initialize three pointers:
    - `low` starts at the beginning of the array and tracks the position where the next `0` should go.
    - `high` starts at the end of the array and tracks the position where the next `2` should go.
    - `current` starts at the beginning of the array and iterates through the elements.
- The algorithm works as follows:
    1. If the `current` pointer encounters a `0`, we swap the element at `current` with the element at `low`, then increment both `low` and `current` pointers.
    2. If the `current` pointer encounters a `2`, we swap the element at `current` with the element at `high` and decrement the `high` pointer. Note that we do not increment the `current` pointer here because the element swapped from the `high` position needs to be processed.
    3. If the `current` pointer encounters a `1`, we simply move the `current` pointer to the next position.
- The process continues until the `current` pointer crosses the `high` pointer.
- This approach ensures all `0`s are pushed to the beginning, all `2`s are pushed to the end, and the `1`s remain in the middle without requiring any additional sorting step.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(1)$

```python
zero, one, two = 0, 0, len(nums)-1

while one <= two:
	if nums[one] == 0:
		nums[one], nums[zero] = nums[zero], nums[one]
		one += 1
		zero += 1
	elif nums[one] == 2:
		nums[one], nums[two] = nums[two], nums[one]
		two -= 1
	else:
		one += 1
```