---
aliases:
  - leetcode 76
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[strings]]"
  - "[[hash tables]]"
  - "[[sliding window]]"
  - "[[two-pointers]]"
difficulty: hard
companies:
  - Airbnb
publish: true
---

**DSA-PATTERNS:** [[strings]], [[hash tables]], [[sliding window]], [[two-pointers]]

**DIFFICULTY:** hard

**COMPANIES:**
- airbnb

# Problem Description

**Leetcode Link:** [Minimum Window Substring - LeetCode](https://leetcode.com/problems/minimum-window-substring/description/)

**Solution Link:** [Minimum Window Substring - Airbnb Interview Question - Leetcode 76 - YouTube](https://www.youtube.com/watch?v=jSto0O4AJbM)

Given two strings s and t of lengths m and n respectively, return the minimum window substring of s such that every character in t (including duplicates) is included in the window. If there is no such substring, return the empty string "".

The testcases will be generated such that the answer is unique.

Example 1:

```
Input: s = "ADOBECODEBANC", t = "ABC"
Output: "BANC"
Explanation: The minimum window substring "BANC" includes 'A', 'B', and 'C' from string t.
```

Example 2:

```
Input: s = "a", t = "a"
Output: "a"
Explanation: The entire string s is the minimum window.
```

Example 3:

```
Input: s = "a", t = "aa"
Output: ""
Explanation: Both 'a's from t must be included in the window.
Since the largest window of s only has one 'a', return empty string.
```

# Approach
- In this question, problem was that I understood the logic in which I could do it(I had the idea) but I couldn't convert that to optimal code or just write the code for it.
- The main idea  you need to understand here is that we have characters that we need and we need to have these characters in the window that we need to return. 
- We need to `have` our `need` basically.
- It is basically [[two-pointers]] but also a [[sliding window]] I say this because of the fact that we need to use [[two-pointers]] to return the minimum window substring.
- We need the [[hash tables]] to determine if our have's and need's match.
- The first [[hash tables]] is the frequency of characters in string `t` and the second [[hash tables]] is updated as we traverse the string `s`.
- We have a `left` pointer that start at `0` and we have a `right` pointer that moves front to determine whether we have our `haves` for the `needs`.
- The initial value of `need` would be the length of the first [[hash tables]] let's say `countT` i.e `need` is basically the number of characters that must satisfy their own frequency.
- As you are traversing the [[strings]] with the `right` pointer we need to check if the `ch` is present in `countT` and whether this frequency matches the frequency in the window and `countT`, if so then we can increment our `have`.
- we get our result when `have == need` and here we need to understand that the `right` pointer stays still and the `left` pointer must be incremented so that we can get the minimum substring by removing unnecessary characters at the front or for us to be able to find new substring further in the front by removing one of the `have` to make the condition not satisfy.
- The mistake I did in the above step while implementing it was that I made it complex by thinking of making it a if condition which involved unnecessary operations and what I had to do was I had to use a `while` loop.
- In the end we can return the res substring if the resLen is not infinity else return `""`.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(1)$ -> because alphabets -> fixed number

```python
if t == "":
	return ""

countT = collections.Counter(t)
window = {}
have, need = 0, len(countT)

res, resLen = (-1, -1), float("inf")

l = 0
for r, ch in enumerate(s):
	window[ch] = window.get(ch, 0) + 1
	if ch in countT and window[ch] == countT[ch]:
		have += 1
	while have == need:
		if (r-l+1) < resLen:
			res = (l, r)
			resLen = r-l+1
		window[ch] -= 1
		if s[l] in countT and window[s[l]] < countT[s[l]]:
			have -= 1
		l += 1

l, r = res 
return s[l: r+1] if resLen < float("inf") else ""
```