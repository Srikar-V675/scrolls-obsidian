---
aliases:
  - leetcode 409
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[strings]]"
  - "[[hash tables]]"
  - greedy
difficulty: easy
companies: 
publish: true
---

**DSA-PATTERNS:** [[strings]], [[hash tables]], greedy

**DIFFICULTY:** easy

**COMPANIES:**
- 

# Problem Description

**Leetcode Link:** [Longest Palindrome - LeetCode](https://leetcode.com/problems/longest-palindrome/description/)

**Solution Link:** 

Given a string s which consists of lowercase or uppercase letters, return the length of the longest palindrome that can be built with those letters.

Letters are case sensitive, for example, "Aa" is not considered a palindrome.

Example 1:

```
Input: s = "abccccdd"
Output: 7
Explanation: One longest palindrome that can be built is "dccaccd", whose length is 7.
```

Example 2:

```
Input: s = "a"
Output: 1
Explanation: The longest palindrome that can be built is "a", whose length is 1.
```

# Approach
- The main logic here is that the count of each character matters and it also matters whether the count is even or odd.
- We know that for a palindrome if it is even length then they can be split half and half on two sides. ex: `ab|ba` 
- For odd length palindrome we know that the right and left have even characters and there is one extra character in the middle. ex: `ab|a|ba`
- I did in mistake in the odd part or actually the whole tbh where what I thought was if the frequency of a character is `even` then I can directly add it to the `res` but if the frequency was `odd` what I thought was that I can only add the highest frequency of `odd` to the result.
- The way I was thinking was pure idiocy and solely structured on the test cases that leetcode gave and I gracefully fell in the trap.
- The actual approach for `odd` frequency is that we can `-1` which will give us an even number of characters and add that to the `res` and I can also toggle a variable that there is a `odd` so that I can add this extra one in the middle like we talked about for `odd` length palindrome.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(1)$ -> because we are using [[hash tables]] for only alphabets i.e lowercase and uppercase only which is fixed number.

```python
freq = collections.Counter(s)
res = 0
isOdd = False

for f in freq.values():
	if f % 2 == 0:
		res += f
	else:
		res += (f-1)
		idOdd = True

return (res+1) if isOdd else res
```