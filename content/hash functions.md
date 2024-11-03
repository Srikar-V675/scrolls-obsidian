---
creation: 2024-09-22 19:46
source: "[[hash tables]]"
atlas: "[[04-Atlas/DSA]]"
type: literature
publish: true
---
# Hash Functions 

### Summary
Hash functions are an integral part of [[hash tables]]. These functions let us map a key to a value, it performs some kind of operation on the key to determine the index in which the value should be stored in [[hash tables]]. 

The value can be an index to an array that contains the actual value or the value itself. 
> [!example]
> If *The Book of Life* is the key then the value could be the row in the shelf in which the book is in the library. Here the shelf can be the array and the row is the index of the array.

![[Hash-Table-example.excalidraw]]

Each index of the [[hash tables]] are called *buckets* and can sometimes hold more than one value, this scenario is called a ==collision==. 

> [!example]
> An example of a collision would be if there was another book with 13 letters in the above example then even that book would belong to the bucket-1 in hash table.

The ==concept of collisions== is still a better idea than searching the entire array because we are decreasing the search space drastically, but collisions can cause a problem if majority of elements are mapped to a single bucket. Hence a good hash function is one that can *distribute the keys equally among the buckets* and is *easy to compute*.

--- 
### Key Terms
*Buckets:* refers to each index of [[hash tables]] that stores a value.
*Collisions:* can happen when two keys belong to the same bucket in [[hash tables]].

### Related Notes
[[Arrays]]
[[hash tables]]

### References(links)
[Hashing Out Hash Functions. Over the course of the past few months… | by Vaidehi Joshi | basecs | Medium](https://medium.com/basecs/hashing-out-hash-functions-ea5dd8beb4dd)