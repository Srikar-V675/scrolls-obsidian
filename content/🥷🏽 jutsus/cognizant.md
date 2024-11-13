---
date: 2024-11-05 02:40
tags:
  - interview-experience
  - job-prep
job-role: SDE
package: INR 4.5 - 6.5 lpa
---

## Process

*Round-1:* Communication Assessment `12-09-2024`

*Round-2:* Aptitude Assessment + Technical Assessment

*Aptitude Assessment:* `18-09-2024`

Section-1: Quant 
Section-2: Logical Reasoning

> Reflections
> The Quant section was fucked because of the page unresponsive shit.
> Logical reasoning went pretty well.

*Technical Assessment:* Cluster 2 -> Python + SQL + Cloud Fundamentals `19-09-2024`

Section-1: 2 coding Qs
Section-2: 2 SQL queries
Section-3: Cloud MCQs - 15% of Qs

*Resources*
[🔥Cognizant SQL Questions asked on 18/09/2024 | Cognizant Technical Assessment🔥 - YouTube](https://youtu.be/j3FrOs9AlL0?si=d7CrlJVf3DmO2mQn)
[SQL SELECT Statement](https://www.w3schools.com/sql/sql_select.asp)

*Experience:*

**Section-1: SQL Queries** 
2 Qs - All Test Cases Passed

Went well, I finished within 10 mins. Got a little confused with the joins so I experimented with the output and got the right answer.

**Section-2: Coding Qs**
2 Qs - All Test Cases Passed

Q-1: Answer Sheets

Given *num* and *array* as inputs. *array* contains the answers of each student where each digit of the number is a answer. You need to grade the student if he has passed or not by checking the following rules:
1. all digs in the answer are different from digits in *num*
2. sum of digs in the answer is greater than the minimum dig in *num*
Return the count of students that passed the test.

```
Input:
num = 7777
array = [909, 213]

Output:
count = 1

Explanation:
For student-1, his answer is 909.
- all digs are different from digits in num
- sum of digits = 18 > 7 (min of num) so pass
For student-2, his answer is 213.
- all digs are different from digits in num
- sum of digits = 6 < 7 so fail
Hence, count = 1 is the output.
```

Code: the solution is pretty straight forward.

Q-2: Library

A librarian by mistake rearranged the books that were in alphabetical order wrongly. Now he wants to know how many books he need to replace or rearrange without touching the books that are already at the right place.

```
Input:
string = "helco"

Output:
books = 3

Explanation:
If string was in right order then the string would be: "cehlo". We can see that characters at 0, 2, 3 were only misplaced and the others are in the right position.
Hence, books = 3 is the output.
```

Code: you need to sort the string and then compare each character in both strings, if they are not the same then increment the count.

*Overall:* the coding round went pretty well, the only problem I had was the compilation was taking time and the typing was lagging. Probably because of the internet or just the `MSB` browser.

**Section-3: Cloud Fundamentals**
Went pretty fine, they were just MCQs anyway. I might gotten 2-3 Qs wrong. I got confused between *SaaS* and *PaaS*.

