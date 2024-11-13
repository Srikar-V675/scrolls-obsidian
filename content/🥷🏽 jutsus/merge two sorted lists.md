---
aliases:
  - leetcode 21
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[linked list]]"
  - "[[merge sort]]"
difficulty: easy
companies:
  - microsoft
publish: true
---

**DSA-PATTERNS:** [[linked list]], [[merge sort]]
**DIFFICULTY:** easy
**COMPANIES:** 
- microsoft

# Problem Description

**Leetcode Link:** [Merge two sorted lists](https://leetcode.com/problems/merge-two-sorted-lists/)

**Solution Link:** 

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one **sorted** list. The list should be made by splicing together the nodes of the first two lists.

Return _the head of the merged linked list_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg)
```
**Input:** list1 = [1,2,4], list2 = [1,3,4]
**Output:** [1,1,2,3,4,4]
```

**Example 2:**

```
**Input:** list1 = [], list2 = []
**Output:** []
```

**Example 3:**

```
**Input:** list1 = [], list2 = [0]
**Output:** [0]
```

# Approach

Its very similar to how we merge two [[arrays]] in [[merge sort]]. There is nothing else to it, I'm pretty sure you would understand it if you knew [[merge sort]]. The only thing I didn't notice from the problem statement was that it mentioned using the same nodes in the input and not creating new nodes. 

# Solution 

**Time Complexity:** $$O(m+n)$$

**Space Complexity:** $$O(m+n)$$

```python
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next

dummy = ListNode()
cur = dummy
while list1 and list2:
	if list1.val <= list2.val:
		cur.next = list1
		list1 = list1.next
	else:
		cur .next = list2
		list2 = list2.next
	cur = cur.next

if list1:
	cur.next = list1
if list2:
	cur.next = list2

return dummy.next
```