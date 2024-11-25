---
aliases: leetcode 238
tags:
  - dsa-problem
  - dsa
dsa-patterns: 
- "[[arrays]]"
difficulty: medium
companies: 
- Amazon
- Apple
- Airbnb
- LinkedIn
- Twitter 
- Facebook
- microsoft
- tiktok 
- asana
publish: true
---

**DSA-PATTERNS:** [[arrays]]

**DIFFICULTY:** medium

**COMPANIES:**
- Amazon
- Apple
- Airbnb
- LinkedIn
- Twitter 
- Facebook
- microsoft
- tiktok 
- asana

# Problem Definition

Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].

The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

You must write an algorithm that runs in `O(n)` time and `without` using the `division` operation.

**Follow up**: Can you solve the problem in O(1) extra space complexity? (The `output array does not count as extra space` for space complexity analysis.)
 

Example 1:

```
Input: nums = [1,2,3,4]
Output: [24,12,8,6]
```

Example 2:

```
Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]
```

# Approach

## Brute Force

Brute approach would be to calculate the product except self at every index, which would make time complexity be O(N^2) and space complexity would be O(1) as the output array is not considered.

**Time Complexity:** O(N^2)
**Space Complexity:** O(1)

## Better

We can break down the product at each index to be the product of element before(prefix) and after(postfix). Now we can store the prefix and postfix of the elements in two different arrays.

The product at each index `i` without self would be: `prefix[i-1] * postfix[i+1]`. `i+1` and `i-1` would not exist for the last and first element respectively so we need not consider them.

**Time Complexity:** O(N)
**Space Complexity:** O(N+N)

## Optimal

![Image](DSA-Problems/Arrays%20Strings/Medium/image.png)

Optimal approach would be to store the prefix of the element in the output array and then multiple with the postfix of the element also in the output.

> **NOTE:** 
> To store in output we are not going to store prefix/postfix of the element in the same index rather than previous index as we stored before.

**Example:** [1, 2, 3, 4]

**Step-1:** Store the prefix's in the output array.

![alt text](DSA-Problems/Arrays%20Strings/Medium/image-1.png)

**Step-2:** Compute postfix and multiple with the prefix in output array.

![alt text](DSA-Problems/Arrays%20Strings/Medium/image-2.png)


# Code

**Time Complexity:** O(N)

**Space Complexity:** O(1)

```python
from typing import List

def productExceptSelf(nums: List[int]) -> List[int]:
    result = [1] * len(nums)
    prefix = 1
    for i in range(len(nums)):
        result[i] = prefix
        prefix *= nums[i]
    postfix = 1
    for i in range(len(nums) - 1, -1, -1):
        result[i] *= postfix
        postfix *= nums[i]  
    return result
```