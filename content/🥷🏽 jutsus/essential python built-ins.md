---
date: 2024-11-05 01:43
sources: 
tags:
  - zettel
  - interview-prep
  - dsa
status: literature
publish: true
---
# essential python built-ins

- **enumerate:** getting values and index at the same time in a for loop.

```python
for i, value in enumerate(nums):
```

- **zip:** iterate on 2 [[Arrays]] at the same time.
- **set:** to store only unique values, i.e no duplicates allowed.
- **deque**: A double ended queue.

```python
dq = collections.deque()
dq = deque()

dq.append(val) # push right
dq.pop() # pop right
dq.appendleft() # push left
dq.popleft() # pop left
```

- **counter:** returns the freq of elements of a iterable variable.

```python
freq = collections.Counter(var) # var -> list, string or any iterable
for f in freq.keys():
	print(f, ": ", freq[f]) # 'a': 3 ...
keys = list(freq.keys()) # list of keys
values = list(freq.values()) # list of values
for f in freq.elements():
	print(f, " ") # g g e e e ...

# Add 2 counter variables
from collections import Counter  
  
counter1 = Counter(a=3, b=2)  
counter2 = Counter(a=1, b=2, c=3)  
combined = counter1 + counter2 # Output: Counter({'a': 4, 'b': 4, 'c': 3})

# Subtract 2 counter variables
difference = counter1 - counter2 # Output: Counter({'a': 2}) | Considers the first counter as primary therefore as 'c' was not present in first counter it was not considered (if you subtract it becomes -ve)
```

---
## Related Notes

## References(links)
