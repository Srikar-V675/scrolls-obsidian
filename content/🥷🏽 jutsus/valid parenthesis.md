---
aliases:
  - leetcode 20
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[strings]]"
  - "[[hash tables]]"
  - "[[stack]]"
difficulty: easy
companies:
  - Facebook
  - Google
  - Microsoft
  - Amazon
publish: true
---

**DSA-PATTERNS:** [[strings]], [[hash tables]], [[stack]]
**DIFFICULTY:** easy
**COMPANIES:** 
- Facebook
- Google
- Microsoft
- Amazon

# Problem Definition

**Leetcode link:** [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)
**Youtube link:** [Neetcode Solution](https://www.youtube.com/watch?v=WTzjTskDFMg)

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.
 
Example 1:
```
Input: s = "()"
Output: true
```
Example 2:
```
Input: s = "()[]{}"
Output: true
```
Example 3:
```
Input: s = "(]"
Output: false
```

# Approach

- To ensure that open brackets are closed in the correct order and to handle nested brackets, we will utilize a **stack**.
- We need a dictionary to map closing brackets to their corresponding opening brackets, allowing us to verify matches efficiently.
- When encountering a closing bracket, we should check:
    - If the stack is empty, which would indicate an unmatched closing bracket.
    - If the top of the stack does not match the corresponding opening bracket, we should immediately return `False`.
- Initially, I used a simple if-else structure for checking pairs of brackets but overlooked early stopping conditions based on the third point.

# Code

## Better
**Time Complexity:** $$O(N)$$
**Space Complexity:** $$O(1)$$

```python
stack = []
for ch in s:
    if ch == ')' and stack and stack[-1] == '(':
        stack.pop()
    elif ch == ']' and stack and stack[-1] == '[':
        stack.pop()
    elif ch == '}' and stack and stack[-1] == '{':
        stack.pop()
    else:
        stack.append(ch)
return True if not stack else False
```

## Optimal

**Time Complexity:**$$ O(N)$$
**Space Complexity:** $$O(N)$$
```python
stack = []
brackets = {
    ')': '(',
    ']': '[',
    '}': '{'
}
for ch in s:
    if ch in brackets:
        if stack and stack[-1] == brackets[ch]:
            stack.pop()
        else:
            return False
    else:
        stack.append(ch)
return True if not stack else False
```