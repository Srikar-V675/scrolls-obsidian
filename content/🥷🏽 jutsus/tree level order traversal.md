---
date: 2024-11-06 00:15
sources:
  - "[[binary trees and binary search trees]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Level Order Traversal  

### Summary
*Level Order Traversal* as the name suggests, we traverse the tree by visiting every node in each level. We always go from left to right and hence it is also called breadth first search. 

> [!important]-
> **Level Order Traversal involves using a [[Queue]] because first node that enters is the first node to come out.**
> 

![[level-order-traversal-example.excalidraw.png]]

### Iterative Code

```python
q = deque()
q.append(root)
while q:
	node = q.popleft()
	print(node.val)
	if node.left:
		q.append(node.left)
	if node.right:
		q.append(node.right)
```

> *Check this out:* [[level order traversal dry run]]

### Iterative Code by Level 

```python
q = dequeu()
q.append(root)
res = []
while q:
	level = []
	for _ in range(len(q)): # len(q) = no. of root nodes at that level
		node = q.popleft()
		level.append(node.val)
		if node.left:
			q.append(node.left)
		if node.right:
			q.append(node.right)
	res.append(level)
print(res) # prints each levels nodes.
```

> *Check this out:* [[level order traversal by level dry run]]

### Use Cases
*Serialisation:* serialising a binary tree into a linear data structure like [[Arrays]] or [[Linked List]]. 

*Find min depth:* first leaf node encountered represents the min depth of the tree because we go level by level. 

*Tree modification:* of all nodes at a certain level of binary tree. 

---
### Related Notes
[[trees]]
[[binary trees and binary search trees]]
[[level order traversal dry run]]
[[level order traversal by level dry run]]

### References(links)
Mostly on my own.