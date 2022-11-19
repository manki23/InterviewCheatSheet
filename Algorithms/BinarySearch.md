# Binary Search

```python
def binarySearch(OrderedNbList: List[int], target: int) -> int:
    low = 0
    high = len(OrderedNbList) - 1
    while low < high:
        middle = round((low + high) / 2)
        if target < OrderedNbList[middle]:
            high = middle - 1
        else:
            low = middle
    return low if target == OrderedNbList[low] else None
```

## Complexity
O(logN)