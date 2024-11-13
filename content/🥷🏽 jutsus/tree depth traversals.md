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
# Tree Depth Traversals

### Summary
Since [[trees]] are unstructured data structures and unique. The way we can access the nodes is by traversing in a unique way, one such way is to traverse by depth. 

The overall algorithm of tree depth traversals more or so remains the same, but the order in which we process the nodes can be different.

> [!important]-
> **Depth Traversal involves using a [[Stack]] because the node that entered last is the one that must be popped out.**

### Types of Depth Traversals 

![Tree](https://proxy-prod.omnivore-image-cache.app/0x0,s6lOWUFJdazs8TNbiYpEyVc7M6YGLN1unOG736M4S85I/https://upload.wikimedia.org/wikipedia/commons/5/5e/Binary_tree_v2.svg)

*Pre-Order:* root -> left -> right
ex: 1, 7, 2, 6, 5, 11, 9, 9, 5
*In-Order:* left -> root -> right
ex: 2, 7, 5, 6, 11, 1, 9, 5, 9
*Post-Order:* left -> right -> root
ex: 2, 5, 11, 6, 7, 5, 9, 9, 1

> [!important]-
> **In-Order Traversal of a binary tree is insufficient to uniquely serialise a tree. Pr-order or post-order traversal is required.**

### Recursive Code

```python
def depthTraverse(root):
	# Base case: when node is None
	if not root:
		return
	print(root.val) # Pre-Order
	depthTraverse(root.left)
	# print(root.val) # In-Order
	depthTraverse(root.right)
	# print(root.val) # Post-Order
```

> [!use cases]-
> [[tree depth traversal use cases]]

### Tasks 
- [ ] Implement each order traversal iteratively as a bonus.

---
### Related Notes
[[trees]]
[[tree depth traversal use cases]]
[[binary trees and binary search trees]]
[[Searching & Sorting]]
[[Recursion]]

### References(links)
[Mastering Binary Tree Traversals: A Comprehensive Guide | by Adam DeJans Jr. | Plain Simple Software | Medium](https://medium.com/plain-simple-software/mastering-binary-tree-traversals-a-comprehensive-guide-d7203b1f7fcd)