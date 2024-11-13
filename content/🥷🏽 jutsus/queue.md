---
date: 2024-11-06 00:04
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Queue

## Summary
- Queue is a linear data structure that offers a functionality that follows `FIFO - First In First Out`. 

### Idea
- Queue follows FIFO which states that the first one to come in is also the first one to come out.
- To ensure we follow this rule or functionality Queue's allow for addition of element at end of sequence(**enqueue** operation) and removal of elements from the start of sequence(**dequeue** operation).
- End of sequence is called the back, tail, rear of the Queue.
- Start of sequence is called the front, head of the Queue.

![[Queue-People.excalidraw.png]]

> [!hint]
> **Breadth First Search** is implemented using Queue.

### Implementation
- Since Queue is a abstract data structure, it has to be implemented using another data structure as its base. 
- Since Queue holds sequence of elements, the structures that come to mind are: [[Arrays]] and [[Linked List]].
- Since Queues are dynamic I would say Linked Lists are a better option right off the bat, but lets look into the reasoning a little more.

#### [[Arrays]] vs [[Linked List]] for Implementation

**[[Arrays]]**:
- [[Arrays]] are static data structures i.e we need to know the expected size of array beforehand.
- While insertion and removal at end in an array is O(1) time, insertion or removal at start of an array is still O(n) time because of the shifting that needs to be taken care of.
- Hence enqueue would be O(1) time but dequeue would be O(n) time because after removal we need to shift the elements. This can be overcome by using a circular array.
- But there is still a big problem looming behind this implementation and i.e the fact that when we enqueue and the corresponding memory is not available, then we need to copy the array and re-allocate it(O(n) time). 
- It's still considered O(1) on average.
- There can also be wastage of memory as we can never know that at any given time most of the elements are present in the queue.

**[[Linked List]]:**
- As I said, [[Linked List]] can be best implementation for a Queue.
- Linked Lists are dynamic and you don't have to know the size before hand.
- We can maintain 2 pointers that point to the head and tail of the list which gets rid of the fact that we need to traverse.
- We can make use of the pointers and enqueue and dequeue in O(1) not on average but all the time.

![[Queue-ArrayvsLL.excalidraw.png]]

> [!info]
> `Queues` are used in many places **message queues**, **job scheduling**, **request & response queuing** in web servers etc...

### Time complexity

|Operation|Big-O|
|---|---|
|Enqueue/Offer|O(1)|
|Dequeue/Poll|O(1)|
|Front|O(1)|
|Back|O(1)|
|isEmpty|O(1)|
### Essential Qs
- [Implement Stack using Queue](https://github.com/Srikar-V675/DSA-Problems/blob/21c0ba2329fb01ebd7bceb23f557611f06d4584f/Queues/Easy/1.%20Implement%20Stack%20using%20Queue.md)

### Recommended Qs
- [Implement Queue using Stacks](https://github.com/Srikar-V675/DSA-Problems/blob/21c0ba2329fb01ebd7bceb23f557611f06d4584f/Queues/Easy/2.%20Implement%20Queue%20using%20Stacks.md)

## Tasks
- [ ] Permanent zettels
- [ ] Learn `Circular Array` just the basics.

---
## Key Terms
- **Enqueue:** addition of an element to end of queue.
- **Dequeue:** removal of an element from start of queue.

## Related Notes
- [[Arrays]]
- [[Linked List]]

## References(links)
- [Queue cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/queue/)
- [To Queue Or Not To Queue. When I first learned about background… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/to-queue-or-not-to-queue-2653bcde5b04)