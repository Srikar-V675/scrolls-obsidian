---
aliases:
  - leetcode 77
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[recursion]]"
difficulty: medium
companies:
  - Facebook
  - Google
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[recursion]]

**DIFFICULTY:** medium

**COMPANIES:**
- facebook
- google

# Problem Description

**Leetcode Link:** [Combinations - LeetCode](https://leetcode.com/problems/combinations/)

**Solution Link:** [Neetcode](https://www.youtube.com/watch?v=q0s6m7AiM7o)

Given two integers n and k, return all possible combinations of k numbers chosen from the range [1, n].

You may return the answer in any order.

Example 1:
```
Input: n = 4, k = 2
Output: [[1,2],[1,3],[1,4],[2,3],[2,4],[3,4]]
Explanation: There are 4 choose 2 = 6 total combinations.
Note that combinations are unordered, i.e., [1,2] and [2,1] are considered to be the same combination.
```

Example 2:
```
Input: n = 1, k = 1
Output: [[1]]
Explanation: There is 1 choose 1 = 1 total combination.
```

# Approach

- Biggest blunder: I thought I couldn't use a for loop in a recursion problem and spent shit load of time trying to figure the solution without the for loop.
- Let's try to understand what they have asked. They have basically asked us to find the combinations by choosing k elements from 1-n integers, since it is a combinatorial problem order doesn't matter i.e [1, 2] = [2, 1].
- Let's see the decision tree I constructed to understand better.

![[combinations-dt.png]]

- at every step we can see that we are going from what we chose+1 to the n.
- if we chose 1 then we go from 2-4 because those are the options available.
- if we chose 2 then we go from 3-4 eventhough we can use 1 is because when we chose 1 we generated teh combination [1, 2] which would be same as [2, 1].
- This is where I knew I could have used a for loop but i thought `in recursion I can't use a for loop` and it just became complicated.

# Solution

**Time Complexity:** $O(K * (nCk))$
**Space Complexity:** $O(K * (nCk))$

```python
def backtrack(start, combi):
    if len(combi) == k:
        res.append(combi.copy()) # copy() -> because we keep updating combi in the function we don't want it to update in `res`.
        return 
    for i in range(start, n+1):
        combi.append(i)
        backtrack(i+1, combi)
        combi.pop() # since we appended i we need to pop to let us add a new combi
res = []
backtrack(1, [])
return res
```