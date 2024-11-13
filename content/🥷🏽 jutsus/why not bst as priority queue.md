---
date: 2024-11-07 18:42
sources: "[[heap as priority queue]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# why not bst as priority queue?

- [[heaps]] are always complete binary trees -> Operations will be:
$$O(log\ n)$$
- Because of [[binary trees and binary search trees|BSTs]] rules of having left node lesser and right node greater, the [[trees]] can be skewed which can in the worst case be:
$$O(n)$$
- Heapification corrects the order every time of [[manipulating heaps]] where [[binary trees and binary search trees|BSTs]] have nothing like that. 

---
## Related Notes
[[queue]]
[[priority queue]]
[[heap as priority queue]]

## References(links)
