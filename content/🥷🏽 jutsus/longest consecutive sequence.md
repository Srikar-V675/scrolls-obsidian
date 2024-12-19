---
aliases:
  - leetcode 128
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[hash tables]]"
difficulty: medium
companies:
  - Google
  - Amazon
  - Microsoft
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[hash tables]]

**DIFFICULTY:** medium

**COMPANIES:**
- Google
- Amazon
- Microsoft

# Problem Description

**Leetcode Link:**

```cardlink
url: https://leetcode.com/problems/longest-consecutive-sequence/description/
title: "Longest Consecutive Sequence - LeetCode"
description: "Can you solve this real interview question? Longest Consecutive Sequence - Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence.You must write an algorithm that runs in O(n) time. Example 1:Input: nums = [100,4,200,1,3,2]Output: 4Explanation: The longest consecutive elements sequence is [1, 2, 3, 4]. Therefore its length is 4.Example 2:Input: nums = [0,3,7,2,5,8,4,6,0,1]Output: 9 Constraints: * 0 <= nums.length <= 105 * -109 <= nums[i] <= 109"
host: leetcode.com
image: https://leetcode.com/static/images/LeetCode_Sharing.png
```

**Solution Link:** None

Given an unsorted array of integers `nums`, return _the length of the longest consecutive elements sequence._

You must write an algorithm that runs in `O(n)` time.

**Example 1:**

**Input:** nums = [100,4,200,1,3,2]
**Output:** 4
**Explanation:** The longest consecutive elements sequence is `[1, 2, 3, 4]`. Therefore its length is 4.

**Example 2:**

**Input:** nums = [0,3,7,2,5,8,4,6,0,1]
**Output:** 9

# Approach
- The problem asks us to find the length of the longest sequence of numbers that are consecutive, meaning each number in the sequence differs by 1 from the next (e.g., `1, 2, 3` or `100, 101`). The count of each number doesn’t matter, only their presence.
- To solve this efficiently, we use a **hash table** (like a set in Python) to quickly check if a number exists in the array. This gives us O(1)O(1)O(1) lookup time.
- Here's the key idea:
    1. For each number in the array, check if the number **before it** (current number - 1) exists in the array. If it does, skip this number because it means the current number is part of an existing sequence and not the start of a new one.
    2. If the number doesn’t have a smaller number before it, it’s the **start of a sequence**. From here, check how many consecutive numbers (current + 1, current + 2, etc.) exist in the array and count them.
    3. Keep track of the maximum length of such sequences as you go through the array.
- Why does this work? By only starting sequences from the smallest number in each chain, we avoid unnecessary checks for numbers in the middle of a sequence.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(N)$

```python
nums_map = collections.Counter(nums)
res = 0

for num in nums:
	if num-1 not in nums_map:
		count = 1
		while num+count in nums_map:
			count += 1
		res = max(res, count)
return res
```