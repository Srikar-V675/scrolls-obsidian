---
date: 2024-11-05 23:56
sources:
  - "[[tree level order traversal]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Level Order Traversal Dry Run

```mermaid
graph TD
A(1) --> B(2)
A --> C(3)
B --> D(4)
B --> E(5)
```

![[tree level order traversal#Iterative Code]]

*Iteration-0:*
```
q = [1]
res = None
```

*Iteration-1:*
```
q = [2, 3]
res = 1
```

*Iteration-2:*
```
q = [3, 4, 5]
res = 1, 2
```

*Iteration-3:*
```
q = [4, 5]
res = 1, 2, 3
```

*Iteration-4:*
```
q = [5]
res = 1, 2, 3, 4
```

*Iteration-5:*
```
q = []
res = 1, 2, 3, 4, 5

ends because q is empty
```

---
### Related Notes
[[tree level order traversal]]
[[trees]]

### References(links)
Neetcode.io yt videos. check it out.