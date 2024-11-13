---
date: 2024-11-05 03:03
sources: "[[topological sorting]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# topological sorting using khan's algo

Khan's algo for [[topological sorting]] implements a mechanism that is similar to [[graphs breadth first search]]. They may not be similar completely but they use the core mechanism. 

We should be aware of these concepts of directed graphs to understand Khan's algo better:
1. *in-edge:* an edge pointing to or coming into("in") the node.
2. *out-edge:* an edge pointing away or going "out" from the node. 
3. *in-degree:* the count of *in-edges* coming into the node. 
4. *out-degree:* the count of *out-edges* going away from the node. 

The *in-edge* and *in-degree* are important concepts here because we know [[topological sorting]] order depends on it. If a node has *in-degree* of 0 then we know this is the node that we visit first.  ^6e873e

If we take this in the context of [[trees]], we can see that the order for [[topological sorting]] would be root node first and then the nodes in the next level and goes on... 

we can notice that whatever we mapped above is similar to how [[graphs breadth first search]] works, since [[graphs]] have more freedom compared to [[trees]], [[graphs breadth first search]] alone can't help us. 

Hence khan's algo combines the [[graphs breadth first search]] and the in-degree concepts together. 

*Q:* How does khan's algo do it? 
*A:* We know this [[topological sorting using khan's algo#^6e873e]], what we also should know is that once we have visited the node with *in-degree* 0, we can decrement all its neighbours in-degree by 1 and remove the node. As we do this one-by-one we get the right order. 

How can we do this? This is where the [[graphs breadth first search]] comes. We need to use a [[Queue]] to keep track of the nodes that have in-degree 0, this way we can visit this node add it to the order and then decrement the in-degree of its neighbours and remove it. 

*Steps:*
1. compute the *in-degree* of all the nodes. add the nodes that have *in-degree* 0 to queue to visit them. 
2. pop each node from the [[Queue]], decrement the *in-degree* of its neighbours by 1. if any of the neighbours *in-degree* becomes 0 add it to the [[Queue]]
3. do this until [[Queue]] is empty.

> [!tip]- bfs vs khan's algo 
> In [[graphs breadth first search]] we add all nodes to the [[Queue]] as we traverse, but in [[topological sorting using khan's algo]] we add only the nodes that have *in-degree* 0 to the [[Queue]].

```python
def find_indegree(graph):
	indegree = {node: 0 for node in graph}
	for node in graph:
		for neighbour in get_neighbours(node):
			indegree[neighbour] += 1
	return indegree

def topo_sort(graph):
	q = deque()
	res = []
	indegree = find_indegree(graph)
	for node in indegree:
		if indegree[node] == 0:
			q.append(node)
	while q:
		node = q.popleft()
		res.append(node) # node with in-degree 0
		for neighbour in get_neighbours(node):
			indegree[neighbour] -= 1
			if indegree[neighbour] == 0:
				q.append(neighbour)
	return res id len(res) == len(graph) else None
```



---
## Related Notes
[[graphs]]
[[trees]]
[[graphs breadth first search]]
[[Queue]]
[[directed acyclic graphs]]
[[topological sorting]]

## References(links)
[Topological Sort Introduction](https://algo.monster/problems/topo_intro)