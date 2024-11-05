---
date: 2024-11-05 23:49
sources: "[[graphs]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Cyclic and Acyclic [[graphs]]

## Captures
We have directed and undirected [[graphs]] and these graphs could also be cyclic or acyclic graphs. 

*Cyclic:* [[graphs]] that have at least one single cycle i.e edges that allow traversal of the nodes in a circular fashion. 

```mermaid
graph LR;
	A --- B
	B --- D
	B --- C
	C --- A
	D --- X
```

*Acyclic:* [[graphs]] that have no cycles at all i.e the edges don't allow traversal of the nodes in a circular fashion.

```mermaid
graph LR;
	A --- B
	A --- C
	C --- D
	B --- E
	B --- F
```

Self-loops can only occur in directed [[graphs]] and they are considered cyclic because it forms a cycle with itself. 

```mermaid
graph LR;
	A --> B
	A --> C
	B --> D
	D --> D
	C --> E
	A --> E
```

Since directed graphs are very important and most of the data in this world are mostly directed. We have much importance in:
1. Directed Cyclic Graphs
2. Directed Acyclic Graphs (DAG) *
 
---
## Related Notes

## References(links)
