# Breadth First Search

```python
from collections import deque

def bfs(graph, root):
    q = deque([root])
    visited = {root}
    while q:
        v = q.popleft()
        # if v is the goal:
        #     return v
        for child in graph[v]:
            if child not in visited:
                visited.add(child)
                # child.parent = v
                q.append(child)
```

***
### Difference from DFS:   
- uses a queue instead of a stack
- it checks whether a node has been explored before enqueueing the node rather than delaying this check until the node is dequeued from the queue.
***
### NB:
- 'vertex' == 'node'
- 'vertice' == 'edge'
- the *parent* attribute is useful for accessing the nodes in a shortest path, for example by backtracking from the destination node up to the starting node.

***
### Time and Space complexity
O(nb_of_nodes + nb_of_edges)
***
### Application of BFS
- Finding the shortest path between two nodes
- ...