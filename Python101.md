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

## defaultdict
```python
from collections import defaultdict
```

## bisect_left
```python
import bisect
```
The bisect_left() method finds and returns the position at which an element can be inserted into a Python list while maintaining the sorted order of the Python list. If the list already has elements with the same value as the new element, the insertion point is to the left of first such element.

```python
bisect_left(pythonList, newElement, lo=0, hi=len(a));
```
Parameters:
- `pythonList` – The Python list whose elements are in sorted order.
- `newElement` –  The new element for which the position is to be found in the already sorted Python list.

- `lo` – The lowest position of the search interval to be used as a heuristic.

- `hi` – The highest position of the search interval to used as  a heuristic.

Return Value:
- The position at which the element can be inserted into the Python list while maintaining the sorted order of the list.

Similar:
- `insort(list, newElement, lo=0, hi=len(a))`:   
    - The insort() method inserts a new element into an already sorted Python list.
    - If the list already has existing elements as the new element then the new element is inserted into the right of the last such existing element.
    - The functions insort() and insort_right() behave the same way.
    - Invoking insort() is equivalent to calling the bisect_right() and calling the list.insert().
- `insort_left()`, `insort_right()`, `bisect_right()`...