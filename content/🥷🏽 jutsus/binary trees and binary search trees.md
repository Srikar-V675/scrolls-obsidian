---
date: 2024-11-05 23:46
sources: "[[trees]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Binary Trees and BSTs

### Summary
Each node except the root node in a binary tree contains: left subtree and right subtree. A searchable binary tree is a binary search tree. 

![[binary-tree.excalidraw.png]]

**Complete Binary tree:** a binary tree in which every level, except the last is completely filled and all nodes in the last level are as far left as possible.

**Balanced Binary tree:** a binary tree in which the left and right subtree of every node doesn't differ in height by no more than 1.

> [!Node Class]-
> 
> ```python
> class Node:
> 	def __init__(self, val):
> 		self.val = val
> 		self.left = None
> 		self.right = None
> ```
> <br>

### Binary Search Trees 
These [[trees]] are a special case of binary trees where each node follows a rule.

> *Rule:* left node is lesser than current node and right node is greater.

![[bst.excalidraw.png]]

> [!info]+
> **In-order traversal of a BST will give the elements in order.**

> [!time complexity]-
> |Operation|Big-O|
> |---|---|
> |Access|O(log(n))|
> |Search|O(log(n))|
> |Insert|O(log(n))|
> |Remove|O(log(n))|

> [!important]-
> **Space complexity of traversing a balanced binary tree would O(h), where 'h' is the height of the tree.** 
> **Space Complexity of traversing a BST would be O(log n).**
> **Space Complexity of traversing a skewed binary tree or BST would be O(n).**

---
### Related Notes
[[trees]]
[[tree depth traversals]]
[[tree depth traversal use cases]]
[[Searching & Sorting]]
[[tree level order traversal]]

### References(links)
[Leaf It Up To Binary Trees. Most things in software can be broken… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/leaf-it-up-to-binary-trees-11001aaf746d)