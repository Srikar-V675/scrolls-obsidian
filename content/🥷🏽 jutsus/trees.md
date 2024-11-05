---
date: 2024-11-06 00:16
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Trees

## Summary
Trees are abstract non-sequential data structures that are really just a bunch of nodes and links that are connected to one another.

trees are undirected and connected acyclic graphs, they are acyclic because they do not contain cycles or loops. 

trees are a recursive data structure because each node is a root node of its own subtree. Hence [[Recursion]] is a useful technique for traversal of a tree.

![[recursive-subtree.excalidraw.png]]

## Terms
*Root:* the parent of all nodes that is at the top of the tree.
*link/edges:* are the connections between 2 nodes.
*child:* a node that has a parent, all nodes are child except the root.
*parent:* a node that has children, all nodes except leaf nodes.
*siblings:* nodes that are children of the same node.
*internal:* any node that has a child node, all parent nodes.
*leaf:* a node that has no child.

![[tree-terms.excalidraw.png]]

## Characteristics
> If a tree has n nodes then it will always have (n-1) edges/links. Why? because there is no link connecting to the root node.

> Trees contain smaller trees within themselves often referred to as *subtrees*.

> [!note]
> *Depth of a node:* how far away is the node from the root of the tree?
> *Height of a node:* how far is this node from the farthest away leaf? (Remember: we are turning the tree upside down in CS, hence height is determined this way.)

> [!important]+
> [[types of trees]]

> [!tip]-
> **Look out for very skewed trees like a [[Linked List]]**

### Traversals 
[[tree depth traversals]]
[[tree level order traversal]]

### Tasks 
- [ ] Self-balancing binary trees. don't forget.

---
### Questions
Q: Difference between a balanced tree and unbalanced tree? 
![[balanced vs unbalanced trees#Balanced vs Unbalanced]]

### Key Terms
![[trees#Terms]]

### Related Notes
[[tree depth traversals]]
[[tree level order traversal]]
[[binary trees and binary search trees]]
[[Searching & Sorting]]
[[Linked List]]
[[Recursion]]
[[types of trees]]

### References(links)
[Tree cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/tree/)
[Leaf It Up To Binary Trees. Most things in software can be broken… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/leaf-it-up-to-binary-trees-11001aaf746d)
[How To Not Be Stumped By Trees. As soon as the data structure lightbulb… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/how-to-not-be-stumped-by-trees-5f36208f68a7)
[Mastering Binary Tree Traversals: A Comprehensive Guide | by Adam DeJans Jr. | Plain Simple Software | Medium](https://medium.com/plain-simple-software/mastering-binary-tree-traversals-a-comprehensive-guide-d7203b1f7fcd)