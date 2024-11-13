---
date: 2024-11-05 23:34
sources: "[[binary trees and binary search trees]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Balanced vs Unbalanced Trees

## Balanced vs Unbalanced

### Balanced Trees 
Balanced trees are a type of binary tree where the tree follows a rule that makes tree traversal efficient.

*Rule:* any binary tree is a balanced tree if the difference between the heights of left subtree and right subtree is at most 1.

**Access:** 
$$
\begin{gathered}
O(log \ n) \\
log \ n = ~h \\
h = height \ of \ tree
\end{gathered}
$$

> [!example]-
> ![[balanced trees mermaid]]

> **The above tree is a balanced tree because the height difference between left and right subtree is exactly 1.**

### Unbalanced Trees 
Unbalanced trees are the trees that don't follow the balanced rule and are usually skewed towards one side making it look like a [[Linked List]] which is a sequential data structure. Hence it defeats the use of having a tree. 

**Access:**
$$
\begin{gathered}
O(n) 
\end{gathered}
$$

> [!attention]-
> **The drawback of unbalanced trees is the operations performed on them are costly due to their skewness and similarity to sequential data structures.**

> [!example]-
> ![[unbalanced trees]]

---
## Related Notes
[[binary trees and binary search trees]]
[[tree depth traversals]]
[[Linked List]]
## References(links)
Google