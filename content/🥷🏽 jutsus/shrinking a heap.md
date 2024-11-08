---
date: 2024-11-07 07:10
sources: "[[manipulating heaps]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Shrinking a Heap

Again follows the same properties mentioned in [[growing a heap]]. 

### Steps
1. Remove the desired node first, this would not follow the *Complete Binary Tree* property. 
2. To make sure we follow the *complete binary tree property* we need to add something at the position we removed the node. Only option is to add the last node. 
3. Now we are following the *complete binary tree* property but it might not follow *heap order* property.
4. `Heapify down` because we removed a node and swapped with the last node -> element we swapped to that position is definitely lesser than root node(map-heap).

```mermaid
graph TD;
71 --> 19
71 --> 43
19 --> 12
43 --> 35
12 --> 6
12 --> 2
19 --> 4
4 --> 1
```

```mermaid
graph TD;
71 --> 19
71 --> 43
19((19)) --> 12
43 --> 35
12 --> 6
12 --> 2
19 --> 4
4 --> 1
```

```mermaid
graph TD;
71 --> 1
71 --> 43
1 --> 12
43 --> 35
12 --> 6
12 --> 2
1 --> 4
```

```mermaid
graph TD;
71 --> 12
71 --> 43
12 --> 1
43 --> 35
1 --> 6
1 --> 2
12 --> 4
```

```mermaid
graph TD;
71 --> 12
71 --> 43
12 --> 6
43 --> 35
6 --> 1
6 --> 2
12 --> 4
```
[[add aliases to fish shell]]
---
## Related Notes
[[heaps]]
[[manipulating heaps]]
[[growing a heap]]

## References(links)
[Learning to Love Heaps. Today marks the halfway point of this… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/learning-to-love-heaps-cef2b273a238)

[For shrinking a heap, why do we need to remove the root node first and then...](https://www.perplexity.ai/search/for-shrinking-a-heap-why-do-we-LeuK2tAWTveZfE0D6EJfzg)