---
date: 2024-11-05 23:33
sources: "[[graph representations]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# adjacency list problems

> [!info]-
> **Degree** of a vertex is the number of edges that it has or the number of neighbouring nodes it has.

What can be the highest degree of a node? It would not be more than:
$$(|V| - 1)$$
because the potential neighbours a node can have is the number of vertices minus itself.

Since in an adjacency list, each vertex has its neighbours as a [[Linked List]], the maximum length of the [[Linked List]] will be:
$$(|V| - 1)$$

This would make the access time equal to:
$$O(d)$$
where,
d = degree of the vertex. `d` could be equal to:
$$(|V| - 1)$$

> [!caution]-
> **Another problem is about the fact that directed [[graph representations]] would occupy O(E) while undirected [[graph representations]] would occupy O(2E). Just take up a example you'll realise.**

---
## Related Notes
[[graphs]]
[[graph representations]]

## References(links)
[From Theory To Practice: Representing Graphs | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/from-theory-to-practice-representing-graphs-cfd782c5be38)