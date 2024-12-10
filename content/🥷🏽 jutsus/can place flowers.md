---
aliases:
  - leetcode 605
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
difficulty: easy
companies:
  - Google
publish: true
---

**DSA-PATTERNS:** [[arrays]]
**DIFFICULTY:** easy
**COMPANIES:** 
- Google

# Problem Description

**Leetcode Link:** [Can Place Flowers](https://leetcode.com/problems/can-place-flowers/description/)

**Solution Link:**  [ChatGPT - Code Optimization Advice](https://chatgpt.com/share/67587d92-7dec-8013-a612-e225293161eb)

# Approach
- The goal is to place `1`s in the flowerbed without violating the rule that no two `1`s can be adjacent.
- As you move from left to right through the flowerbed, check the current element and the next element:
    - If the current element is `0` and the next element is also `0`, place a `1` in the current position.
        - After placing the `1`, skip to two positions ahead because the next position is now invalid for placement.
    - If the next element is `1`, skip to three positions ahead because the next valid spot will be after three positions.
- If the current element is already `1`, skip two positions ahead because no adjacent positions can be used for placement.
- When you reach the last element:
    - If the last element is `0`, there’s no need to check further.
    - You know it’s a valid spot because the only way you’ve arrived at it is by skipping over invalid spots earlier in the array.
    - Therefore, you can confidently place a `1` without additional checks.
- Stop early if you’ve already placed all `n` required `1`s, as there’s no need to continue checking.
- If you finish iterating through the flowerbed and haven’t placed all `n` `1`s, return `False`.
 
# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(1)$

```python
i = 0
while i < len(flowerbed):
	if n == 0:
		return True
	if flowerbed[i] == 0 and (i == len(flowerbed)-1 or flowerbed[i+1] == 0):
		flowerbed[i] = 1
		n -= 1
		i += 2
	elif flowerbed[i] == 1:
		i += 2
	else: 
		i += 3
return n == 0
```