---
date: 2024-11-11 05:32
sources: "[[heaps]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Heap in Python

Python comes with a built-in module called `heapq` which can implement a heap(-> [[priority queue]]). It implements a [[min heaps]] by default but there is a simple workaround to implement [[max heaps]].

#### heapq.heappush():
It does as the name suggests... It takes 2 arguments: `array` and `element`. 

#### heapq.heappop():
Takes an `array` and returns the smallest element([[min heaps]]).

> [!example]
> ```python
> import heapq
> heap = []
> heapq.heappush(heap, (5, "write code"))
> heapq.heappush(heap, (3, "write tests"))
> heapq.heappush(heap, (1, "write design"))
> heapq.heappop(heap) -> (1, "write design")
> ```

To implement [[max heaps]] you can just `multiply -1` to the priority of each element you push and pop. Simple as that.
 
A known list can be converted into a heap by using the `heapify` function of `heapq`. This operation is $$O(n)$$

```python
import heapq
arr = [3, 5, 1]
heapq.heapify(arr)
```

---
## Related Notes
[[heaps]]
[[arrays]]
[[priority queue]]
[[heaps implementation]]
[[heap as priority queue]]
[[min heaps]]
[[max heaps]]

## References(links)
[Heap Fundamentals](https://algo.monster/problems/heap_intro)