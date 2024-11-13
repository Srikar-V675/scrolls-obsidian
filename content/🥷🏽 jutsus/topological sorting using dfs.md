---
date: 2024-11-05 23:28
sources: "[[topological sorting]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# topological sorting using dfs

We know that [[topological sorting]] is nothing but making sure we visit a node only when we know we have visited every single node that leads up to it. 

Since [[graphs depth first search]] is very good at following a path and when it reaches a leaf node it backtracks. We can take this mechanism to our advantage. We can use a stack to store the ordering in reverse order. Where we push to stack only when we know every neighbouring node of the cur node is visited or it is the leaf node. 

```python
visited = set()
stack = []

def dfs(node):
	visited.add(node)
	for neighbour in get_neighbours(node):
		if neighbour not in visited:
			dfs(neighbour)
	# after visiting all its neighbours we can push to stack. 
	stack.append(node)

# make sure we visit all paths available
for node in graph:
	if node not in visited:
		dfs(node)

print("Ordering: ", stack[::-1])
```

We use the `for loop` to visit the nodes because there can be multiple nodes (like root nodes with no edge leading up to it). To counter this we need to make sure we don't miss any node. 

The actual ordering is the reverse of the `stack` because notice that in [[graphs depth first search]] we are reaching the deepest level and then backtracking. We are essentially going deep and then backtracking hence we are constructing the [[topological sorting]] in reverse i.e from the leaf nodes. 

> [!tldr]-
> **See it this way, what does [[graphs depth first search]] do? 
> A: It follows a path and backtracks when it visits a node that is already visited 
> In the path it takes what is the last node it visits? 
> A: A leaf node (or node that has visited all its neighbours). 
> What is the position of this node in [[topological sorting]] ?
> A: It is one of the last nodes in the order to be visited hence we are constructing the [[topological sorting]] in reverse. **

---
## Related Notes
[[graphs]]
[[graphs depth first search]]
[[topological sorting]]
[[directed acyclic graphs]]
[[Stack]]

## References(links)
[Perplexity | Topological Sorting using dfs](https://www.perplexity.ai/search/topological-sorting-using-dfs-p9IM5VswTLGwYovBZxkp.Q)