---
date: 2024-11-06 00:18
sources:
  - "[[graphs]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Graph Edges

## Captures
We all know the main type of edges and they are *directed* and *undirected* edges. But we also need to know that there are several other types of edges that branch out from these two but have different significance based on the [[graphs]]. 

*Tree edges:* are the edges that make sure when you are traversing you reach new node in levels like in trees. 

*Non-Tree edges:* are the edges that are not tree edges but there can be overlaps depending on the [[graphs]] as you know they are not rule-followers. 

Under non-tree edges we have three main types:
1. Forward edges 
2. backward edges 
3. cross edges 

Let's take an example to help us understand, these edges. 

![[types-of-edges.excalidraw.png]]

All the blue edges above are *tree edges*, you can see that they make a tree if you structure it properly. 

*Forward edges:* green edges are forward edges *why?* because if you see it in the perspective of the tree edges, `u --> x` is going forward in the tree. 

*Back edges:* red edges are back edges *why?* because again just like forward edges, `x --> v` is going back in the tree. If you  notice there are also self-loops.

*Cross edges:* brown edges are cross edges because, cross edges are the edges that connect two subtrees that don't have common ancestors. here `w --> y` who are in two different subtrees with no common ancestors. 

These types apply to both directed and undirected [[graphs]]. But undirected graphs can only have tree edges and forward edges. 

---
## Related Notes
[[graphs]]

## References(links)
[Spinning Around In Cycles With Directed Acyclic Graphs | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/spinning-around-in-cycles-with-directed-acyclic-graphs-a233496d4688)