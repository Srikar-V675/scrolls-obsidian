---
aliases:
  - leetcode 3
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[two-pointers]]"
  - "[[hash tables]]"
difficulty: medium
companies:
  - Facebook
  - Amazon
  - Microsoft
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[two-pointers]], [[hash tables]]

**DIFFICULTY:** medium

**COMPANIES:**
- facebook
- amazon
- microsoft

# Problem Description

**Leetcode Link:** [Longest Substring without Repetitions](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)

Given a string s, find the length of the longest substring without repeating characters.

Example 1:
```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

Example 2:
```
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```
Example 3:
```
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

## Approach

- To find the longest substring without repeating characters, we can utilize a hashmap to track character indices efficiently.
- Initially, I attempted to clear the hashmap whenever I encountered a repetition, which led to unnecessary operations.
- This approach caused issues due to overlapping characters; resetting the hashmap and restarting from the left pointer resulted in extra operations.
- Instead, we can use two pointers:
    - **Left Pointer:** Indicates the start of the current substring.
    - **Right Pointer:** Iterates through the string from start to end.
- For each character at index `right`:
    - Check if it exists in the hashmap.
    - If it does, verify whether its index is greater than or equal to `left`. If so, this indicates a repetition within our current window.
        - In this case, update `maxLength` to reflect the longest substring found so far.
- During each iteration:
    - Update the hashmap with the current character's index. This allows us to know where each character was last seen in the string.
- By maintaining this structure, we ensure an efficient and straightforward solution.

![[longest substring without repeating characters.png]]

# Solution

**Time Complexity:** $O(N)$
**Space Complexity:** $O(N)$

```python
maxCount = 0
seen = {}
left = right = 0
while right < len(s):
    if s[right] in seen and seen[s[right]] >= left:
        maxCount = max(maxCount, right - left)
        left = seen[s[right]] + 1
    seen[s[right]] = right
    right += 1
maxCount = max(maxCount, right - left)
return maxCount
```