---
date: 2024-11-11 19:28
tags:
  - pr
project: "[[SyncWise]]"
link: https://github.com/Srikar-V675/syncwise/pull/17
branch: create-student
publish: true
---

**PROJECT:** [[SyncWise]]

**LINK:**

**BRANCH:** `create-student`

## Changes 
- made changes in `UserSerializer` with respect to creating new `User`
- added `StudentSerializer` with basic functionality
- modified `UserViewSet` with respect to queryset
- added `StudentViewSet` with basic functionality

## Description

#### UserSerializer
- filtered fields -> `("id", "username", "email", "password", "first_name", "last_name")`.
- creation of new `User` is modified where the `User` is created and assigned group `Students` and the `User` is given the department by the creator of the student automatically(by teacher).

**refer:** `gradesync/serializers.py`

#### UserViewSet
- queryset filtered by authenticated `User's` department.

**refer:** `gradesync/views.py`

#### Endpoints
**User endpoints:** `/api/users/`
**Student endpoints:** `/api/students/`

### Next Tasks 
- [ ] write tests 
- [ ] class teacher(FK User) field for `Section`