---
aliases:
  - leetcode 11
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - "[[two-pointers]]"
difficulty: medium
companies:
  - Facebook
  - Google
publish: true
---

**DSA-PATTERNS:** [[arrays]], [[two-pointers]]

**DIFFICULTY:** medium

**COMPANIES:**
- facebook
- google

# Problem Definition

**Leetcode Link:** [Container with Most Water](https://leetcode.com/problems/container-with-most-water/)

**Solution Link:** [Neetcode](https://youtu.be/UuiTKBwPgAo?si=FBBeDg_J1mPFqF_b)

You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.

Example 1:

![](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg)

```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

Example 2:
```
Input: height = [1,1]
Output: 1
```

# Approach

- To find the maximum area of water that can be contained, we need to identify two lines that are as far apart as possible while also being tall enough to maximize the area.
- The key observation is that if we have two heights (e.g., 2 and 8), we should consider moving away from the shorter line (in this case, 2) to potentially find a taller line that is closer to the other line (8).
- This means we need to maintain two pointers: one at the beginning of the array and one at the end.
- By calculating the area formed by these two lines and then adjusting our pointers based on their heights, we can efficiently find the maximum area.

# Solution

**Time Complexity:** $O(N)$
**Space Complexity:** $O(1)$

```python
maxArea = 0
left = 0
right = len(height) - 1
while left < right:
    if height[left] < height[right]:
        maxArea = max(maxArea, (right - left) * height[left])
        left += 1
    else:
        maxArea = max(maxArea, (right - left) * height[right])
        right -= 1
return maxArea
```