---
date: 2024-11-05 23:55
sources:
  - "[[tree level order traversal]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# level order traversal by level dry run

```mermaid
graph TD
A(1) --> B(2)
A --> C(3)
B --> D(4)
B --> E(5)
C --> F(6)
C --> G(7)
```

![[tree level order traversal#Iterative Code by Level]]

*Iteration-0:*
```
q = [1]
level = []
res = []
```

*Iteration-1:*
```
q = [2, 3]
level = [1]
res = [ [1], ]
```

*Iteration-2:*
```
q = [4, 5, 6, 7]
level = [2, 3]
res = [ 
	[1], 
	[2, 3]
]
```

*Iteration-3:*
```
q = []
level = [4, 5, 6, 7]
res = [ 
	[1], 
	[2, 3], 
	[4, 5, 6, 7]
]
```

---

### Related Notes
[[tree level order traversal]]
[[trees]]

### References(links)
Neetcode.io yt videos. check it out.