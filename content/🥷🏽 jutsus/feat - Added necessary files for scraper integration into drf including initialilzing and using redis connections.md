---
date: 2024-12-17 07:47
tags:
  - pr
project: "[[SyncWise]]"
link: https://github.com/Srikar-V675/syncwise/pull/18
branch: scraping
publish: true
---

**PROJECT:** [[SyncWise]]

**LINK:** [Added necessary files for scraper integration into drf including initialilzing and using redis connections by Srikar-V675 · Pull Request #18 · Srikar-V675/syncwise · GitHub](https://github.com/Srikar-V675/syncwise/pull/18)

**BRANCH:** `scraping`

## Changes 
1. Added serializers for Identifying subjects, batch creating subjects from list, scraping students in a batch, computing performance of students after score is scraped
2. Added necessary views for the above serializers along with a view for getting the scraping info progress, total and errors from redis hash_name mapping
3. Changed the Score table to store the score in a JSONField and created helpers to compute total, percentage and sgpa from scores
4. Added code that initializes redis connection on startup and some helpers to make my life easier when communicating and updating the scraping info
5. Added some helper funcs to scraper.py and also created new file scraper_drf.py for utils related to drf and scraping.

## Description

### Scraping Steps

```mermaid
graph TD;
	A[1. Identify Subject] --> B[2. Check Subjects]
	B --> C[3. Add Credits to each Subject and Add to DB]
	C --> D[4. Scrape the Results by Batch]
	D --> E[5. While Scraping goes on keep hitting the progress endpoint]
	E --> F[6. Compute Student Performance]
```

### 1. Identify Subjects

**endpoint:** `/api/identify/`

**request-type:** `POST`

**request-params:** 
```json
{
  "usn": "string",
  "result_url": "string"
}
```

**response-example:**
```json
{
  "subjects": [
    {
      "sub_name": "ENVIRONMENTAL STUDIES",
      "sub_code": "21CIV57"
    },
    {
      "sub_name": "AUTOMATA THEORY AND COMPILER DESIGN",
      "sub_code": "21CS51"
    },
    ...
  ],
  "status": "Succesfully scraped student results!!"
}
```

> [!note]-
> `status` in response will tell if any errors were there while scraping.

### 2. Check Subjects
- Check the returned subjects if there are any other subjects that needs to be added can be added when adding these subjects.

### 3. Add Credits to Each Subject and Add to DB
- Add the credits for each subject and send a request to the endpoint to add the subjects to the DB.

**endpoint:** `/api/subjects/`

**request-type:** `POST`

**request-params:** 
```json
{
  "sub_name": "string",
  "sub_code": "string",
  "credits": 9223372036854776000,
  "sem": 0
}
```

**request-example:**
```json
[
    {
      "sub_name": "ENVIRONMENTAL STUDIES",
      "sub_code": "21CIV57",
      "credits": 1,
      "sem": 1
    },
    {
      "sub_name": "AUTOMATA THEORY AND COMPILER DESIGN",
      "sub_code": "21CS51",
      "credits": 3,
      "sem": 1
    },
    ...
]
```

**response-example:**
```json
[
  {
    "id": 1,
    "sub_name": "ENVIRONMENTAL STUDIES",
    "sub_code": "21CIV57",
    "credits": 1,
    "sem": 1
  },
  {
    "id": 2,
    "sub_name": "AUTOMATA THEORY AND COMPILER DESIGN",
    "sub_code": "21CS51",
    "credits": 3,
    "sem": 1
  },
  ...
]
```

### 4. Scrape the results by Batch
- Now we can scrape the results one by one by Students present in that Batch with respect to the corresponding Semester.

**endpoint:** `/api/scrape/batch/`

**request-type:** `POST`

**request-params:**
```json
{
  "batch": 0,
  "semester": 0,
  "result_url": "string"
}
```

**request-example:**
```json
{
  "batch": 1,
  "semester": 1,
  "result_url": "https://results.vtu.ac.in/DJcbcs24/index.php"
}
```

**response-example:**
```json
{
  "message": "Scraping background task has started.",
  "redis_name": "e26dbfda-a0ba-43aa-b25c-1b5c24a0c1e4"
}
```

> [!warning]-
> This endpoint must be requested only when you are sure the Student objects are created for this Batch. You can make a request to `/api/upload/` for bulk upload of Student objects from a `.csv` file.

### 5. Keep Hitting the progress endpoint
- The scraping takes quite the time to execute hence it is created as a background task and is running another thread. In order to track the progress a redis_mapping is created that returns the scraping info that is needed. This endpoint helps us determine the end of the progress or any error in scraping.

**endpoint:** `/api/scrape/progress/{redis_name}/`

**request-type:** `GET`

**example-url-request:** `/api/scrape/progress/e26dbfda-a0ba-43aa-b25c-1b5c24a0c1e4/`

> [!note]-
> The code is the `redis_name` that is returned by scraping endpoint that is what we need to use to get the scraping info.

**response-example:**
```json
{
  "details": {
    "total": "6",
    "errors": "[]",
    "progress": "6"
  }
}
```

> [!warning]-
> If by any reason before the progress is 100% the endpoint returns an error then that means that the scraping has stopped due to an unforeseen problem or error.

### 6. Compute the Student Performance
- The above scraping only does the scraping and stores the scores in the DB but doesn't compute the performance of students like total, progress and sgpa.

**endpoint:** `/api/scrape/performance/`

**request-type:** `POST`

**request-params:**
```json
{
  "batch": 0,
  "semester": 0
}
```

**response-example:**
```json
{
  "message": "Succesfully computed student performances"
}
```

