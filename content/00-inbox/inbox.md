```dataview
TABLE
	created_date as "Date",
	source as "Source"
FROM "content/00-inbox"
WHERE type = "inbox"
SORT created_date ASC
```
