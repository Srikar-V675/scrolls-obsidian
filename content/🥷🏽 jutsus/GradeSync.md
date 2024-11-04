---
date: 2024-11-05 02:30
tags:
  - documentation
project: "[[SyncWise]]"
publish: true
---

# GradeSync

**PROJECT:** [[SyncWise]]

## GradeSync

> [!abstract]-
> This project proposes the development of a comprehensive web-based platform for analyzing and extracting results from Visvesvaraya Technological University (VTU). The platform is designed to facilitate teachers in managing student data, including batches, sections, and semesters, while providing insightful dashboards that visualize academic performance metrics across these categories. To streamline the previously manual process of result extraction, the system employs web scraping techniques coupled with CAPTCHA solving to automatically retrieve student results by sections. This data is stored in a centralised database, enabling real-time calculations of key performance indicators such as Semester Grade Point Average (SGPA) and overall percentage. <br> 
In addition to performance tracking, the platform will feature a predictive SGPA forecasting model and a risk indicator to identify students at risk of underperforming. A leaderboard will also be integrated to foster healthy competition among students by displaying their rankings based on academic performance. Both teachers and students will benefit from the platform; teachers will have access to detailed analytics for informed decision-making, while students can view their marks, monitor their performance against peers, and utilize forecasting tools to better understand their academic trajectory. This innovative solution aims to enhance educational outcomes by leveraging data analytics and automation, ultimately supporting both educators and learners in achieving academic excellence.

## Features 
![[features#Features List]]

![[gradesync db-design#DB Design]]


### Conflicts
- Database models clash between sqlalchemy and django-models
- Student data clash from *StudySync* with *GradeSync's* for login students DB table

![[gradesync architecture#Architecture]]
