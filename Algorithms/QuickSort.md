# QuickSort

```python
def quickSort(array, low, high):
    if low < high:
        pivot = array[high]

        #pointer for greater element
        i = low - 1

        for j in range(low, high):
            if array[j] <= pivot:
                i = i + 1
                array[i], array[j] = array[j], array[i]
        pivot = i + 1
        array[pivot], array[high] = array[high], array[pivot]

        quickSort(array, low, pivot - 1)
        quickSort(array, pivot + 1, high)
```
***
## Complexity
- average: O(NlogN)   
- worst case: O(n2)