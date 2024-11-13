---
date: 2024-11-05 23:59
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Linked List

## Summary
- Like [[Arrays]], Linked Lists is used to represent sequential data. But the way they store the data differs, where [[Arrays]] store their elements in a contagious memory while linked lists stores its elements that are scattered in memory by linking their addresses.

![[LL-vs-Array.excalidraw.png]]

- The elements in a Linked List are called as `Nodes`.

### Memory Management
- Biggest differentiator between [[Arrays]] and linked lists is the memory management. 
- [[Arrays]] 
	- take up more memory or make use of the operations more because whenever we create an array we need to find a contiguous block of memory and sometimes it can take time to find it. 
	- And when we need to add a element to an array, then if there is space we need to insert the array and shift the following elements. If there is no space or memory left then the whole array must be copied and recreated with more memory.
	- It is a static data structure.
> [!note]
> In the case dynamically typed languages like Ruby, JS, Python, we don't have to worry too much about how much memory an array uses as it is taken care of and is abstracted away. But it doesn't mean that it isn't happening because abstraction is just hiding away the things.
- Linked lists
	- Since the nodes can be anywhere in the memory and as long as we have the address then we can link the nodes together.
	- In the case of adding elements we can just insert the new node and update the links you don't have to push the following elements like in [[Arrays]]. It is like doing a plug & play.
	- It is a dynamic data structure.

### Parts of a Linked List
- A Linked list contains a set of nodes that are linked together sequentially.
- Each individual node contains:
	1. data: the actual value or element
	2. link: the link to next node (address)
- The last node usually is linked to a null to indicate the end of list.
- We need to make sure we don't lose the head or the first element of the list as there is no other way to access the linked list otherwise.

![[LL-Node.excalidraw.png]]


> [!quote]
> "A node only knows about what data it holds and who its neighbours is."

### Types of LL
The parts of linked lists don't usually change but the way we structure can change leading to different types of linked lists for different use cases.

1. **Singly Linked List - SLL**
	- These type of linked lists are the most simple type.
	- Each `Node` contains a data part and link part, where the link part links to the next `Node` of the same type.
	- You can traverse through the linked list only in one way - start at the head and go until you reach a `NULL`.
2. **Doubly Linked List - DLL**
	- As the name suggests it has two links for each node: `prev` & `next`.
	- The `prev` part points to the previous node and `next` part points to the next node in the list.
	- Since they have two link parts they can travel in both ways from left to right or right to left.
3. **Circular Linked List**
	- It is a weird data structure where the tail node is not `NULL` indicating end of list but there is a tail node that points to the head of the list which makes it circular.
	- Traversing by trying to find a `NULL` would make it a infinite loop, you need to know when to stop.
	- You can add an element to end of list easily because you can directly use the tail node to add to list and make that the new tail node and point it tot the head.
	- You can implement both SLL & DLL as a circular LL.

![[Types-LL.excalidraw.png]]

### To Use or Not Use
- Linked lists are good when you usually need to insert or remove from the beginning of the list. But can be hell when you need to find or insert a element that is at the end of Linked list.

> [!quote]
> A linked lists is usually efficient when you want to add or remove some elements, but can be very slow to search and find a single element.

**Points to Remember:**
1. Linked lists are dynamic, they can grow & shrink easily.
2. Inserting & deleting is fast & convenient
3. Searching is slow
4. Finding elements, requires traversal of whole LL and slow since you can't use binary search.

### Time complexity

|Operation|Big-O|Note|
|---|---|---|
|Access|O(n)||
|Search|O(n)||
|Insert|O(1)|Assumes you have traversed to the insertion position|
|Remove|O(1)|Assumes you have traversed to the node to be removed|

### Common Routines
- Finding the number of nodes in linked list
- Finding middle or detecting cycle in LL by using the slow & fast pointer
- Reversing a LL in-place.
- Merge 2 LLs together.

### Corner Cases
1. Empty LL
2. single node
3. two nodes
4. LL has cycles

>[!tip]
>Clarify with interviewer prior to solving a Linked List Q, if there can be a cycle in the Linked list.

### Patterns/Techniques
1. Make use of dummy nodes in front of the head to tackle edge cases like empty LL or single node.
2. **2 pointers:** use slow & fast pointers effectively to solve Qs like find kth node from last, find the middle node, detect cycle in LL.
3. **Elegant modification operations:** make modifications in-place (reversal), truncate a LL, swapping values of nodes(not links), combining 2 LLs

### Essential Qs
- [Reverse Linked List](https://github.com/Srikar-V675/DSA-Problems/blob/3ddaa74d67b82afd2b0400b88b4e3c0cf0291e1b/Linked%20Lists/Easy/1.%20Reverse%20Linked%20List.md)
- [Linked List Cycle](https://github.com/Srikar-V675/DSA-Problems/blob/7a988ed05b1c873fbc39a64090acc4f8e92853f3/Linked%20Lists/Easy/2.%20Linked%20List%20Cycle.md)


---
## Key Terms
- **Node:** Atomic component of a Linked List that usually contains 2 parts: `data` & `link`.
- **Traversal:** Visiting every single node or element of a data structure sequentially.
- **Fast & Slow Pointers:** A technique used in LL Qs where one pointer moves faster(fast or hare pointer) than the other(slow or tortoise pointer).

## Related Notes
- [[Arrays]]
- [[Two-Pointers]]

## References(links)
- [Linked list cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/linked-list/)
- [What’s a Linked List, Anyway? \[Part 1\] | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)
- [What’s a Linked List, Anyway? \[Part 2\] | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)
