---
date: 2024-11-05 23:49
sources: 
tags:
  - zettel
  - databases
status: literature
publish: true
---
# DB Normalization

### Summary
*Normalization* is the process of minimising redundancy in relations or a set of relations. Redundancy in relations can cause insert, delete and update anomalies. The same concept is used in databases with a set of rules or forms to follow.

### Normal Forms
**First Normal Form - 1NF:** each table cell must contain only single value and each column name must be unique.

**Second Normal Form - 2NF:** each non-key attribute is dependent on the primary key.

**Third Normal Form - 3NF:** all non-key attribute but be independent of each other.

**Boyce-Codd Normal Form - BCNF:** stricter form of 3NF, states that each non-key attribute be dependent only on the candidate key.

**Fourth Normal Form - 4NF:** ensures that the table doesn't contain any multi-valued dependencies.

**Fifth Normal Form - 5NF:** decomposing table into smaller tables to remove data redundancy and ensure data integrity

## Tasks
- [ ] Further exploration on DB Normalization
---
### Questions
Q: Difference between 2NF, 3NF and BCNF?

### Key Terms

### Related Notes


### References(links)
[Normal Forms in DBMS - GeeksforGeeks](https://www.geeksforgeeks.org/normal-forms-in-dbms/)