---
aliases: leetcode 2516
tags:
  - dsa-problem
  - dsa
dsa-patterns: 
- "[[strings]]"
- "[[sliding window]]"
- "[[two-pointers]]"
difficulty: medium
companies: 
publish: true
---

**DSA-PATTERNS:** [[strings]], [[sliding window]], [[two-pointers]]
**DIFFICULTY:** medium
**COMPANIES:**

# Problem Description

**Leetcode Link:** [Take k of each character from left and right](https://leetcode.com/problems/take-k-of-each-character-from-left-and-right/description/)

**Solution Link:** [Take K of Each Character From Left and Right - Leetcode - Python - YouTube](https://www.youtube.com/watch?v=QzcxeJZByNM)

You are given a string `s` consisting of the characters `'a'`, `'b'`, and `'c'` and a non-negative integer `k`. Each minute, you may take either the **leftmost** character of `s`, or the **rightmost** character of `s`.

Return _the **minimum** number of minutes needed for you to take **at least**_ `k` _of each character, or return_ `-1` _if it is not possible to take_ `k` _of each character._

**Example 1:**

```
**Input:** s = "aabaaaacaabc", k = 2
**Output:** 8
**Explanation:** 
Take three characters from the left of s. You now have two 'a' characters, and one 'b' character.
Take five characters from the right of s. You now have four 'a' characters, two 'b' characters, and two 'c' characters.
A total of 3 + 5 = 8 minutes is needed.
It can be proven that 8 is the minimum number of minutes needed.
```

**Example 2:**

```
**Input:** s = "a", k = 1
**Output:** -1
**Explanation:** It is not possible to take one 'b' or 'c' so return -1.
```

# Approach
- This problem is a problem that you face once in a while that just doesn't go to your head no matter what you do.
- Me and vikki tried to solve it together, we brainstormed many ideas and almost got there.
- We only progressed when we saw the hints, where one of the hints says you need keep the log of the count of a,b and c in the input.
- One more hint was that if we choose x elements from left then what is the minimum elements that we need to choose from left to satisfy this condition.
- After looking at this we went with the approach of finding the two parts one in the left and other in the right that we need for the solution, but the blunder of this problem lies there.
- In the way we were progressing, it was going to be a [[two-pointers]] approach but this is actually a [[sliding window]] approach, we were like `huh` when we saw that too.
- The main clue here is that you shouldn't try to find the two left and right parts to minimise the solution but you need to maximise the window in between the left and right part such that the condition is met.

**Actual Solution:**
- We need to first determine the overall count of a.b and c in the input.
- Now that we know the overall count we need to make sure to find a window that gets rid of some of the a,b and c such that the window is maximised and the condition of having at least k of each character is minimised.
- we can have two pointers after we count the overall characters. the right pointer moves to the right and deducts the count of the characters it passes, when the count of one of the characters goes below k that is when we know we need to move the left pointer to make sure we follow the condition. the left pointer adds the character that it passes to make sure the condition is holding this way we can find the maximum window that when deducted from the overall input gives us the minimum minutes.
- We need to do the inverse to find the solution.

![[leetcode-2516.excalidraw.png]]

# Solution 

**Time Complexity:** $$O(n)$$

**Space Complexity:** $$O(1)$$

```python
# total count
count = [0] * 3
for ch in s:
	count[ord(ch) - ord('a')] += 1

if min(count) < k:
	return -1

# sliding window 
l = 0
res = float('inf')
for r in range(len(s)):
	count[ch(s[r]) - ord('a')] -= 1
	while min(count) < k:
		count[ch(s[l]) - ord('a')] += 1
		l += 1
	res = min(res, len(s) - (r - l + 1))
return res
```