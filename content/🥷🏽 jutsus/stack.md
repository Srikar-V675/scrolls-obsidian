---
date: 2024-11-06 00:10
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Stack

## Summary
- A stack is a abstract data type that follows `LIFO - Last In First Out`. 

### Idea
Stack literally means a stack of items. I remember in school when I used to submit books(stack of books) I always used to put my book in the middle because if mine is the last one on `top` then that book is the first one that is picked by the teacher.

![[Stack-books.excalidraw.png]]

> [!note]
> Operations on stack occur only in one direction i.e at the `top`. Be it `push` or a `pop`, it always happens at the top.

### Implementation

^77c198

- Just like [[Queue]], we can implement stack using [[Arrays]] or [[Linked List]].
- We have the same problems as we have for [[Queue]] implementation using [[Arrays]].
	- *Since stack can grow infinitely without any upper limit*, [[Arrays]] eventually can't find a contagious memory of that size and hence it raises a `stack overflow exception`.
	- This is what happens when we have an infinite [[Recursion]].
- In the case of a Singly [[Linked List]], we can add or remove elements from the `head node` which would always be O(1) time complexity. And we can always add a node as long as there is memory left (if not then there is a major memory problem).

![[Stack-Operations.excalidraw.png]]

### Functions
1. *push:* add element to the top of stack. 
2. *pop:* remove element from the top of stack. 
3. *top (peek):* returns the value of top but doesn't pop it.
4. *isEmpty:* check if stack is empty.
5. *size:* returns size of stack.

> [!example]
> 1. undo / redo
> 2. browser history
> 3. call stacks

> [!tip]
> Stacks are used to implement *depth-first-search*.

### Time complexity

|Operation|Big-O|
|---|---|
|Top/Peek|O(1)|
|Push|O(1)|
|Pop|O(1)|
|isEmpty|O(1)|
|Search|O(n)|

### Essential Qs
- [Valid Parentheses](https://github.com/Srikar-V675/DSA-Problems/blob/21c0ba2329fb01ebd7bceb23f557611f06d4584f/Arrays%20%7C%20Strings/Easy/7.%20Valid%20Parentheses.md)
- [Implement Queue using Stacks](https://github.com/Srikar-V675/DSA-Problems/blob/21c0ba2329fb01ebd7bceb23f557611f06d4584f/Queues/Easy/2.%20Implement%20Queue%20using%20Stacks.md)
### Recommended Qs
- [Implement Stack using Queue](https://github.com/Srikar-V675/DSA-Problems/blob/21c0ba2329fb01ebd7bceb23f557611f06d4584f/Queues/Easy/1.%20Implement%20Stack%20using%20Queue.md)


## Tasks
- [ ] Permanent zettels. 
- [ ] Explain [[#^77c198 |Implementation]] properly 

---
## Key Terms
- *LIFO:*  the item that comes in first is the one to go out.
- *Stack Overflow:* an exception that occurs when the stack array can no longer find contagious memory.

## Related Notes
- [[Arrays]]
- [[Linked List]]
- [[Recursion]]
- [[Queue]]

## References(links)
- [Stack cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/stack/)
- [Stacks and Overflows. When I was first learning to code… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/stacks-and-overflows-dbcf7854dc67)