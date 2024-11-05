---
date: 2024-11-05 23:54
sources: 
tags:
  - zettel
  - databases
status: literature
publish: true
---
# Joins in SQL

### Summary
Joins in SQL are a way of combining tables that are related by a primary & foreign key relationship or by common rows. It helps maintain the data integrity, schema and minimise redundancy. 

### Types 
**Inner Join:** result-set contains only the rows that have matching values in both left and right tables.

**Left Join:** result-set contains all the rows in left table and matching rows of right table. Unmatched rows will contain *NULL*.

**Right Join:** result-set contains all the rows in right table and matching rows of left table. Unmatched rows will contain *NULL*.

**Full Join:** result-set contains a combination of rows in left table and right table. Unmatched rows will contain *NULL*.

**Natural Join:** combines two tables based on common columns in the two tables. The common columns are not specified but identified by SQL and the matching rows of the tables are combined.

## Tasks
- [ ] Further exploration on Joins   
- [ ] Explore syntax of joins and natural joins
---
## Related Notes


## References(links)
[SQL Joins (Inner, Left, Right and Full Join)](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)
