# Depth First Search


- A recursive implementation:
```python
def dfs(graph, root):
    root.visited = True
    for child in graph[root]:
        if not child.visited:
            dfs(graph, child)
```
***
- An iterative implementation:
```python
def dfs(graph, root):
    stack = [root]
    while stack:
        node = stack.pop()
        if not node.visited:
            node.visited = True
            for child in graph[node]:
                stack.append(child)
```
or??
```python
def bfs(graph, root):
    q = deque([root])
    visited = {root}
    while q:
        v = q.popleft()
        visited.add(child)
        for child in graph[v]:
            if child not in visited:
                q.append(child)
```
***
### Difference from BFS:   
- uses a stack instead of a queue for bfs
- it explore a node before enqueueing the node to explore later its children (oposite behavior than bfs).

***
### Time and Space complexity
O(nb_of_nodes + nb_of_edges)

***
### Application of DFS
- Finding connected components
- Solving puzzles with only one solution (such as mazes)
- Maze generation algorithm
- ...


### Some leetcode examples:
```python
def maxAreaOfIsland(self, grid: List[List[int]]) -> int:
    m = len(grid)
    n = len(grid[0])
    isInsideGrid = lambda x, y: (0 <= x < m) and (0 <= y < n)
    seen = set()

    def dfs(x, y):
        if not (isInsideGrid(x, y) and (x, y) not in seen and grid[x][y]):
            return 0
        seen.add((x, y))

        return (1 + dfs(x+1, y) + dfs(x-1, y) + dfs(x, y-1) + dfs(x, y+1))

    return max(dfs(x, y) for x in range(m) for y in range(n))
```

Complexity m * n