---
aliases:
  - leetcode 15
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[two-pointers]]"
  - "[[searching & sorting]]"
difficulty: medium
companies:
  - Facebook
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[two-pointers]], [[searching & sorting]]

**DIFFICULTY:** medium

**COMPANIES:**
- facebook

# Problem Description

**Leetcode Link:** [3Sum](https://leetcode.com/problems/3sum/submissions/1366345932/)
**Solution Link:** [3Sum Neetcode](https://www.youtube.com/watch?v=jzZsG8n2R9A)

Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0.

Notice that the solution set must not contain duplicate triplets.

Example 1:
```
Input: nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]
Explanation: 
nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.
nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.
nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.
The distinct triplets are [-1,0,1] and [-1,-1,2].
Notice that the order of the output and the order of the triplets does not matter.
```

Example 2:
```
Input: nums = [0,1,1]
Output: []
Explanation: The only possible triplet does not sum up to 0.
```

Example 3:
```
Input: nums = [0,0,0]
Output: [[0,0,0]]
Explanation: The only possible triplet sums up to 0.
```

# Approach

Honestly, this is not an easy problem. I'll outline my initial solutions and then explain the optimal approach. 

**First Solution:**
- I used a hashmap to store element:index pairs. Fixing one element as the first in the triplet reduces it to a 2Sum problem.
- I created a hashmap and ran an outer loop from the first to the last element while checking for pairs in an inner loop from i+1i+1 to the last element.
- To append triplets to the result list, I ensured they were sorted and checked for duplicates before adding them.
- This solution passed `309/313` test cases but resulted in a time limit exceeded error.

**Second Solution:**
- After reviewing discussions, I found useful tips:
    1. Sort the given array in non-decreasing order.
    2. Loop through the array from index 00 to n−1n−1.
    3. For each iteration, set the target as −nums[i]−nums[i].
    4. Set two pointers: j=i+1j=i+1 and k=n−1k=n−1.
    5. While j<kj<k, check if nums[j]+nums[k]\==target
    6. If true, add the triplet {nums[i], nums[j], nums[k]} to the result and move jj right and kk left.
    7. If false, adjust either jj or kk based on their sum relative to the target.
    8. To avoid duplicates, skip iterations where nums[i]\==nums[i−1] and also skip when updating jj or kk.
    
- I implemented this but overlooked checking for duplicates when updating jj and kk, resulting in passing `311/313` test cases with a time limit exceeded error.

**Optimal Solution:**
- The key improvement was ensuring that I skipped duplicate elements while updating pointers j and k.

# Solution

**Time Complexity:** $O(n^2)$
**Space Complexity:** $O(1)$

```python
res = []
nums.sort()
for i, x in enumerate(nums):
    if i > 0 and nums[i] == nums[i-1]:
        continue
    l = i + 1
    r = len(nums) - 1
    while l < r:
        sum = x + nums[l] + nums[r]
        if sum < 0:
            l += 1
        elif sum > 0:
            r -= 1
        else:
            res.append([x, nums[l], nums[r]])
            l += 1
            while nums[l] == nums[l-1] and l < r:
                l += 1
return res
```