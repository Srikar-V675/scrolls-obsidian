---
aliases: leetcode 125
tags:
  - dsa-problem
  - dsa
dsa-patterns: 
- "[[arrays]]"
- "[[two-pointers]]"
difficulty: easy
companies: 
- Spotify
- Facebook
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[two-pointers]]
**DIFFICULTY:** easy
**COMPANIES:**
- Spotify
- Facebook

# Problem Definition

**Leetcode Link:** [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description/)

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

Example 1:
```
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
```

Example 2:
```
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.
```

Example 3:
```
Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
```

# Approach

- This is a classic 2-pointer problem. To check a palindrome we can have 2 pointers one at each end, and the left pointer increases while the right pointer decreases allowing to check if we have same characters.
- But in this case we have non-alphanumerical characters in the string which we must ignore. It's simple we just need to check the character at left pointer and right pointer, if they are not alphanumeric then we update the pointer values and check.

# Solution

**Time Complexity:** O(N)
**Space Complexity:** O(1)

```python
left = 0
right = len(s) - 1
while left < right:
    if not s[left].isalnum():
        left += 1
        continue
    if not s[right].isalnum():
        right -= 1
        continue
    if s[left].lower() != s[right].lower():
        return False
    left += 1
    right -= 1
return True
```