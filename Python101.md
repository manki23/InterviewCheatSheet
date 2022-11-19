# Python 101

## Deque (Doubly Ended Queue)

```python
from collections import deque
```

Deque is preferred over a list in the cases where we need quicker append and pop operations from both the ends of the container, as deque provides an O(1) time complexity for append and pop operations as compared to a list that provides O(n) time complexity.

methods:   
- `append()`, `appendleft()`,
- `pop()`, `popleft()`,
- `count(occurences)`,
- `remove(first_occurence)`,
- `insert(index, elem)`,
- `index(elem, begin, end)`,
- `extend(iterable)`, `extendleft(iterable)`,
- `reverse()`,
- `rotate()`
```python
queue = deque([1, 2, 3])
...
```
***
## Sorted
Use sorted to sort according to multiple crierias:
```python
sorted(array, key=lambda x: (x[0], x[1]))
```