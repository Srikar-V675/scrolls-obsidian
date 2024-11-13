---
date: 2024-11-06 00:13
sources:
  - "[[tree depth traversals]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Depth Traversal Use cases

### Summary
We know [[tree depth traversals]] have different ordering and each of these ordering have their own unique use cases that help us for efficient operations.

### Pre-Order *root -> left -> right*
*Tree Copying:* When copying [[trees]] we would like to visit the root nodes first and then left and right nodes hence pre-order traversal helps.

*Evaluating Prefix Expressions*

*Creating Prefix Notation:* converting binary tree to prefix notation.

*Directory Structure:* when representing directory structure as a tree we would like to list the folders before the files.

### In-Order *left -> root -> right*

> [!tip]-
> **In-Order is closely related to [[binary trees and binary search trees]]**

*Sorted Output:* to get the elements in sorted order in a binary search tree. 

*BST Validation:* validate whether all nodes in a BST follow the rule of BST. 

*Finding Kth smallest/largest element* 

### Post-Order *left -> right -> root*

> [!tip]-
> **Post-Order is closely related to dependency management.**

*Tree Deletion:* to safely delete a tree we need to first delete its children and then the root to avoid dangling nodes.

*Postfix Expression [[Trees]]*

*Dependency Resolution:* situations where dependencies must be resolved before executing a task (node). 

![[post-order-dependency-example.excalidraw.png]]

---
### Related Notes
[[trees]]
[[tree depth traversals]]
[[binary trees and binary search trees]]
[[Searching & Sorting]]

### References(links)
[Mastering Binary Tree Traversals: A Comprehensive Guide | by Adam DeJans Jr. | Plain Simple Software | Medium](https://medium.com/plain-simple-software/mastering-binary-tree-traversals-a-comprehensive-guide-d7203b1f7fcd)