---
tags:
  - documentation
date: 2024-11-14 17:13
project: "[[SyncWise]]"
publish: true
---

# syncwise things to keep in mind

**PROJECT:** [[SyncWise]]

-  as soon as you create an instance of `Batch` instances of all 8 `Semester` must be created automatically.
-  `teacher` user can only see sections to which she is class teacher. (useful when creating students for that section)
-  add filtering by query params to the APIs that need it.
-  add a function that checks whether the `results.vtu.ac.in` website has changes its structure and by how much percentage.
    -  we can determine website structure changes
    -  go ahead and change it probably.

## Ideas
-  calculate risk of student failure.
-  show the students at highest risks in dashboard.
- for the students marks after it is scraped it is anyway in JSON format maybe we can use a noSQL DB for this? Since if a student has different option of subjects then when identifying the subject we can't put that into the DB. 