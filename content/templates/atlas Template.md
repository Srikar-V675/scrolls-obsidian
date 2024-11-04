---
date: <% tp.file.creation_date() %>
tags:
  - atlas
publish: true
---
# <% tp.file.title %>

```dataview
TABLE
	date as "Date",
	sources as "Source"
FROM "content/🥷🏽 jutsus"
WHERE atlas = [[atlas]]
```