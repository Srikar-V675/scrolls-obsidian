---
aliases:
  - leetcode 242
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[hash tables]]"
difficulty: easy
companies:
  - Uber
  - Google
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[hash tables]]

**DIFFICULTY:** easy

**COMPANIES:**
- Uber
- Google

# Problem Description

**Leetcode Link:** [Valid Anagram - LeetCode](https://leetcode.com/problems/valid-anagram/description/)

**Solution Link:** None 

Given two strings `s` and `t`, return `true` if `t` is an

anagram

of `s`, and `false` otherwise.

**Example 1:**

**Input:** s = "anagram", t = "nagaram"

**Output:** true

**Example 2:**

**Input:** s = "rat", t = "car"

**Output:** false

# Approach
- We need to compare the counts of characters in each [[arrays]].

# Solution 

**Time Complexity:** $O(N + M)$

**Space Complexity:** $O(N + M)$

```python
def isAnagram(self, s: str, t: str) -> bool:
	return collections.Counter(s) == collections.Counter(t)
```