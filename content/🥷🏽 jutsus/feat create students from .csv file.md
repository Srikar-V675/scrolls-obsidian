---
date: 2024-11-21 13:13
tags:
  - pr
project: "[[SyncWise]]"
link: https://github.com/Srikar-V675/syncwise/pull/17
branch: create-student
publish: true
---

**PROJECT:** [[SyncWise]]

**LINK:** 

**BRANCH:** create-student

## Changes 
- created new serializer -> `StudentBulkUploadSerializer` for bulk upload of students through .csv file(for now can extend to excel) 
- created new APIView -> `StudentBulkUploadView`
- made some small changes to admin page.

## Description

#### Bulk Upload Students 
- allow the creation of `students` by uploading a .csv file and necessary fields.
**CSV file format:**

| first_name | last_name | email           |
| ---------- | --------- | --------------- |
| foo        | man       | foo@example.com |
- first a `User` is created and assigned the `Students` group, the `dept` is determined by the teacher who made the request.
- after the `User` is created this user is used to create the `Student` instance. 
- the data for the `User` is determined from the .csv file while for the `Student` instance it is taken from the `POST` request.
- since we are doing a bulk upload of student, I've implemented bulk creation of all the users and then the students, to make sure we have less requests to the DB.

##### API docs 
**method:** `POST`
**endpoint:** `/api/upload/`
**body:** 
```json
{
	'file': .csv file,
	'batch': <id of batch>,
	'section': <id of section>,
	'semester': <is of semester>
}
```
**success response:** 
```json
{
	'message': 'Students uploaded succesfully'
}
```

> [!note]
> Try making the request from postman because you can't upload file in swagger-ui.

