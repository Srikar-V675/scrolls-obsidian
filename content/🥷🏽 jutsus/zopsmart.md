---
date: 2024-11-05 02:36
tags:
  - interview-experience
  - job-prep
job-role: SDE
package: INR 10 lpa
---

### About ZopSmart
Helps offline businesses to go online by providing them with the required tools and techniques to setup their online store.

Also helps the business to engage with their customers and accelerate time-to-market. 

*Industries:* **Retail, E-Commerce, Logistics, Supply Chain**
*Brands:* **Kroger, McAfee, GAP...**

#### Products:
*Website & Mobile Apps:* Android, IOS, websites.
*Marketing:* Personalised marketing, promotions etc.
*Logistics:* Planning & track orders for customers and businesses, Delivery.
*Analytics*
*Customer Support*

#### Technology
*Tech:* ReactJS, NextJS, NodeJS, GoLang, Java, SQL, Redis for caching, Solr for searching, Neo4j graph DB for personalisation.
*Cloud:* AWS, GCP, Azure.

### Process

#### Round-1: Coding Round *2024-09-13*
It went shitty af because the questions were not logical they were more inclined towards solving edge cases

The given time was 45 mins and we had to solve 3 Qs of the idiotic kind. The webcam was not needed so I copied using chatGPT. I solved 1.5 Qs.

#### Round-2: Technical Round *2024-09-20 11:30 am*
Somehow my name was one among the 5 students that got selected for this round. I'm not exactly sure what they will ask. 

##### Preparation:
[[DB Normalization]]
[[acid properties in dbms]]
[[joins in sql]]
[Difference between Process and Thread - GeeksforGeeks](https://www.geeksforgeeks.org/difference-between-process-and-thread/)
[Cache Memory in Computer Organization - GeeksforGeeks](https://www.geeksforgeeks.org/cache-memory-in-computer-organization/)
[Scheduling Algorithms in OS (Operating System) - javatpoint](https://www.javatpoint.com/os-scheduling-algorithms)
[Introduction of Deadlock in Operating System - GeeksforGeeks](https://www.geeksforgeeks.org/introduction-of-deadlock-in-operating-system/)
[What is an Operating System? - GeeksforGeeks](https://www.geeksforgeeks.org/what-is-an-operating-system/)
[What is P2P (Peer-to-Peer Process)? - GeeksforGeeks](https://www.geeksforgeeks.org/what-is-p2p-peer-to-peer-process/)
[Client-Server Model - GeeksforGeeks](https://www.geeksforgeeks.org/client-server-model/)
[Banker's Algorithm in Operating System - GeeksforGeeks](https://www.geeksforgeeks.org/bankers-algorithm-in-operating-system-2/)
[ChatGPT: Programs](https://chatgpt.com/share/66ec6df2-06d4-8013-b8b8-aadcd54c39a7)
OOPs
Projects 

#### Reflections & Experience:
My Interviewer was *Kush Rajpurohit*, he said he was a Frontend developer in the SDE-2 position. First was the introduction, I introduced myself and I told him about the fact that I was coding since 8th grade(disclaimer! It kind of went bad).

He asked about my primary programming language, which was *python*. Next question was to explain a project I've worked on I explained about *EduInsights*, how I got the idea, what was the problem, what I built and how I built it.

It was time for a DSA question. It was a linked list question. 
> *Description:*
> You have two [[Linked List]] each node is a digit of a number. You need to reverse the digits of the number of each linked list and find the sum. You also need to reverse the digits of the sum and store each digit in a linked list.

![[Zopsmart-ll-Q-example.excalidraw | 500center]]

My first approach was to store each number in a string such that it is easy to reverse but that kicked back on me because you can't modify strings. I ended going with an approach of using int itself.

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

def addLL(head1, head2):
    first = 0
    second = 0
    
    cur = head1
    while cur:
        first = (first*10) + cur.value
        cur = cur.next
        
    
    cur = head2
    while cur:
        second = (second*10) + cur.value
        cur = cur.next
    
    # reverse first number
    first = reverseNum(first)
    
    # reverse second number
    second = reverseNum(second)
    
    sum = first + second
    sum = reverseNum(sum)
    
    sum = str(sum)
    head = Node(int(sum[0]))
    
    for i in range(1, len(sum)):
        newNode = Node(int(sum[i]))
        head.next = newNode
    
    return head
    
    
def reverseNum(num):
    rev = 0
    while num != 0:
        dig = num % 10
        rev = (rev * 10) + dig
        num = num // 10
    return rev

head1 = Node(2)
newNode = Node(3)
head1.next = newNode

head2 = Node(5)
newNode = Node(4)
head2.next = newNode

head = addLL(head1, head2)
cur = head
while cur:
    print(cur.value)
    cur = cur.next
```

The time was up and the online editor got fucked and was running without giving the answer, he said:
> "I had expectations since you are coding from 8th grade, so I'm giving you 5 mins extra please give me the output."

#### Round-3: Technical Round *2024-09-20 2:30 pm*
Good news! I got selected for the next round. So this round was with the interviewer *Sakul Thakuri* who is a Senior SDE. First was the introduction and mine was very similar to what I said in the last round. He also asked me about the project and I answered in a similar way I did in last round. 

Time for the DSA questions:
> *Description*
> [1, 0, 0, 1]
> [0, 1, 1, 1]
> [1, 0, 0, 1]
> traverse from [0, 0] to [m, n].

It was clearly a graph question I didn't know graphs and I tried to think of a solution without graph but I couldn't come up with it so I said *idk*. 

He gave me another question.
> *Description*
> A monkey who likes to eat bananas. The monkey can eat bananas in k - where k is the no. of bananas the monkey can eat per hour. We are given an array whose length represents the number of piles and the elements represent number of bananas in each pile. We are also given h - the number of hours the monkey has to eat all the piles of bananas. The monkey likes to eat slow if given time so if k value is 4 and number of bananas is 6 in the pile then the monkey will spend first hour eating 4 bananas and the next hour eating only the 2 bananas left slowly. You need to find the minimum number of k the monkey needs to eat bananas to finish in h hours.

> *Input:*
> piles = [3, 6, 7, 11], h = 8
> *Output:*
> k = 4

I solved this in better approach I'm guessing. Optimal is using a [[Binary Search]].
- [x] Find optimal solution for ZopSmart monkey problem 🔼 📅 2024-09-21 ✅ 2024-09-21

*Solution:* [Koko Eating Bananas](https://github.com/Srikar-V675/DSA-Problems/blob/450f6708fa29bafe97b99b60596026994a5864d7/Arrays%20%7C%20Strings/Medium/12.%20Koko%20Eating%20Bananas.md)
 
He asked me some theory Qs from OS, DBMS, OOPs. Some of the questions were:
OS?, processes and threads, deadlocks, mutex and semaphores, scheduling algos.
indexes, normalisation, denormalisation

OOPs?, 4 concepts in OOPs, how to enforce abstraction in code (A: some abstract classes thingy, didn't answer)

He also asked me to explain a topic in ML, since I had ML in my skills. I explained what is ML first and then I explained decision [[trees]] to him. I'm hoping I'll get selected for he next round, if so the job is pakka because next is the HR round. Fingers crossed.

#### Round-4: Another Technical Round *23-09-2024*

I was wrong, completely wrong. I got selected for the on-site [[Interv]], I went in the hopes that it would be an HR Round but another technical round. My interviewer was someone with a lot of experience I could tell. 

First was the introductions, he never gave his intro. I gave mine the very same way as in previous rounds. And the projects stuff. 

He asked me some Qs about deep learning, I think I answered them pretty well. Then he asked what is OOPs and then difference between Java and Python.

I didn't answer the Java vs Python Q pretty well. Then we asked some questions about SQL I answered pretty much most of them except the Primary key vs Unique key Q.

He also gave me two tables: user & orders and asked me to write a SQL query to get the user with highest average purchase or orders. I wrote this query, but he now asked me to write a query to get the third highest I knew there was a workaround using SELECT and IN statements but I wasn't sure.

He asked a [[Linked List]] [[04-Atlas/DSA]] question. It was a unique reversal question.

```
Input: a -> b -> c -> d -> e -> f -> null
Output: a -> c -> b -> f -> e -> d -> null
Explanation:
swap   swap        swap
| a | b -> c | d -> e -> f |
```

I was tensed and pretty much wrote nothing but the reverse logic for 5 mins and then stuck for 20 mins. I figured out how to connect the pieces after swapping the elements in the piece. 

*My Solution:* [LL Unique Reverse](https://github.com/Srikar-V675/DSA-Problems/blob/3af1698405a2e758603949d7c2ea38bbf01e422b/ll.py)

The thing that got to me was, he glanced at my code for 30 secs and told me that the reversal itself doesn't work but the python code above executes just fine and reversal out of all the things works fine. I tried explaining but he was not ready.

*Status:* REJECTED

### References(links)
[ZopSmart](https://www.zopsmart.com/)
[ZopSmart Interview Experience for SDE - GeeksforGeeks](https://www.geeksforgeeks.org/zopsmart-interview-experience-for-sde/)
[ZopSmart Interview Experience For SDE-1 (On-Campus) - GeeksforGeeks](https://www.geeksforgeeks.org/zopsmart-interview-experience-for-sde-1-on-campus/)
