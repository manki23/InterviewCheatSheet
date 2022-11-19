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

***
### Time and Space complexity
O(nb_of_nodes + nb_of_edges)

***
### Application of BFS
- Finding connected components
- Solving puzzles with only one solution (such as mazes)
- Maze generation algorithm
- ...