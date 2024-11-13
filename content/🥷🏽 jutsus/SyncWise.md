---
date: 2024-11-05 02:23
tags:
  - project
  - software-dev
  - machine-learning
  - ai
status: ongoing
publish: true
---
# SyncWise

> [!abstract]-
> An integrated education platform for colleges (aka our college for now) that combines student performance analysis along with a doubt-resolution system. The dashboard enables teachers to manage batches, students, and performance metrics through a REST API built on FastAPI, while also providing students and teachers with personalised insights into their academic progress. Key features include performance visualisations, predictive analytics for semester forecasting, and an at-risk indicator for student assessments. Additionally, a chatbot powered by Retrieval-Augmented Generation (RAG) will assist students in resolving doubts, streamlining communication between students and teachers. If teh doubt is not resolved by the chatbot then the student can raise a ticket. This comprehensive solution enhances educational outcomes by leveraging data analytics and AI-driven support mechanisms. 

## Overview
**Team Members:** 
*Member-1:* Srikar V *Role:* Data analysis, GradeSync backend, ML & AI integration
*Member-2:* Vignesh P *Role:* Frontend, ticketing system backend
**Objective**: A comprehensive solution for managing results and student doubts.
**Deliverables**: 
*Website*
*GradeSync:*
- Dashboards
- Analytics 
- Risk-Indicator
- Forecasting 

*Study Sync*
- Doubt-resolution chatbot 
- Ticketing System + chatting
**Deadline**: *10-12-2024*
**Timeline:**
Start date: *26-09-2024*
End date: NA

## Tasks

```tasks
path includes 02-Projects/SyncWise
not done
```

## Milestones


## Ideas
- Add pdf extraction too for results.
- Forecasting model 
- Risk-Indicator model
- [ ] Optimise the scraping to use multi-processing or threading etc.

## Tech Stack 
*Backend:* Django, FastAPI
*Frontend:* React, Tailwind CSS 
*Database:* Postgres, Vector DB
*Redis:* Caching, Session Management, Scraping progress
*ML Models:* FastAPI 
*Chatbot:* Vertex AI, langchain, langflow
 
## Links & References
[EduInsights + Ticketing System](https://www.perplexity.ai/search/eduinsights-ticketing-system-bF3a3fRAQJ28F_4ooQQp_g)