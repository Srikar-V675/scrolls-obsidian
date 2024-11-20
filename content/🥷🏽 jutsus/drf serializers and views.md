---
date: 2024-11-19 22:44
sources: 
tags:
  - zettel
  - software-dev
status: literature
publish: true
---
# DRF Serializers and Views

Serializers are nothing but converters that convert the received request data to python data types and does the processing of the stuff like creation, updating etc...

APIViews or ViewSets recieve the request pass it to the serializer which checks validity and execute some operations and then the APIViews returns a response.

```mermaid
graph TD;
A[User] --Request --> B[APIViews/ViewSet]
B -- initializes --> C[Serializer]
C --> D{Validity?}
D -->|Yes| E[Execute Ops]
D -->|No, Error| A
E -- return --> B
B -- response --> A
```

---
## Related Notes

## References(links)
