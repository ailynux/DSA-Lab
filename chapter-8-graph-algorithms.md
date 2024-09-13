# Chapter 8: Graph Algorithms <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Activities/Fireworks.png" alt="Fireworks" width="65" height="65" />

Welcome to Chapter 8 of the **Data Structures and Algorithms** repository! In this chapter, we explore graph algorithms—powerful tools used to traverse, search, and optimize data structures within complex networks. These algorithms are foundational in many areas, including computer networks, social networks, and geographic information systems.

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Mirror%20Ball.png" alt="Mirror Ball" width="65" height="65" /> What are Graph Algorithms?

<table>
  <tr>
    <td style="vertical-align: top;">
      <img src="https://github.com/user-attachments/assets/b4108803-d354-431e-a0b4-4606ef20c438" alt="Graph Algorithm Visualization" style="width:800px;">
    </td>
    <td style="vertical-align: top; padding-left: 20px;">
      Graph algorithms are procedures where the input is a graph or directed graph, and the output could be a numerical value, a path, or another graph. These algorithms aim to solve specific problems related to navigating and organizing interconnected data.
    </td>
  </tr>
</table>


### Key Types of Graph Algorithms:
- **Traversal Algorithms**: Visit nodes of a graph in a systematic way, such as Depth-First Search (DFS) and Breadth-First Search (BFS).
- **Shortest Path Algorithms**: Calculate the shortest path between nodes, critical in routing and navigation, such as Dijkstra's Algorithm and Bellman-Ford Algorithm.
- **Network Flow Algorithms**: Determine the optimal way to send data through a network, like Ford-Fulkerson method.
- **Spanning Tree Algorithms**: Find minimal subset of edges which connect all vertices in the graph, crucial for creating efficient network designs, such as Kruskal’s and Prim’s algorithms.

## 🔄<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Beaming%20Face%20with%20Smiling%20Eyes.png" alt="Beaming Face with Smiling Eyes" width="55" height="55" /> Graph Traversal Techniques

### Depth-First Search (DFS)
DFS explores as far as possible along each branch before backtracking, making it excellent for scenarios that require exploring all options before deciding.

```python
def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)
    print(start)
    for next in graph[start] - visited:
        dfs(graph, next, visited)
    return visited
```
### Breadth-First Search (BFS)
BFS explores the neighbor nodes at the present depth prior to moving on to nodes at the next depth level. It’s ideal for finding the shortest path on unweighted graphs.
```python
from collections import deque

def bfs(graph, start):
    visited, queue = set(), deque([start])
    while queue:
        vertex = queue.popleft()
        if vertex not in visited:
            visited.add(vertex)
            queue.extend(graph[vertex] - visited)
    return visited
```
---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Spiral%20Calendar.png" alt="Spiral Calendar" width="85" height="85" /> Practice Problems

Enhance your skills with these tailored graph algorithm challenges:

1. **Path Finding: Dijkstra's Algorithm**
   - **Challenge**: Implement Dijkstra's algorithm to find the shortest path in a weighted graph. Focus on understanding how edge weights affect decision-making in path selection.
   - **Example Code**:
     ```python
     import heapq

     def dijkstra(graph, start):
         distances = {vertex: float('infinity') for vertex in graph}
         distances[start] = 0
         priority_queue = [(0, start)]
         while priority_queue:
             current_distance, current_vertex = heapq.heappop(priority_queue)
             if current_distance > distances[current_vertex]:
                 continue
             for neighbor, weight in graph[current_vertex].items():
                 distance = current_distance + weight
                 if distance < distances[neighbor]:
                     distances[neighbor] = distance
                     heapq.heappush(priority_queue, (distance, neighbor))
         return distances
     ```

2. **Cycle Detection: Depth-First Search (DFS)**
   - **Challenge**: Use DFS to determine if a cycle exists within a graph. This is critical for applications that need to avoid circular references or loops.
   - **Example Code**:
     ```python
     def dfs(graph, start, visited=None, parent=None):
         if visited is None:
             visited = set()
         visited.add(start)
         for neighbor in graph[start]:
             if neighbor not in visited:
                 if dfs(graph, neighbor, visited, start):
                     return True
             elif parent != neighbor:
                 return True
         return False
     ```

3. **Network Connectivity: Breadth-First Search (BFS)**
   - **Challenge**: Use BFS to verify if all nodes in a graph are reachable from a given starting node. This explores the graph layer-by-layer to ensure full coverage.
   - **Example Code**:
     ```python
     from collections import deque

     def bfs(graph, start):
         visited = set()
         queue = deque([start])
         while queue:
             vertex = queue.popleft()
             if vertex not in visited:
                 visited.add(vertex)
                 queue.extend(graph[vertex] - visited)
         return visited
     ```

---
## Summary <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Green%20Book.png" alt="Green Book" width="45" height="45" />

Graph algorithms are indispensable for analyzing and managing complex networks across various industries. They equip us with the means to conduct efficient data navigation, allocate resources optimally, and plan networks effectively. Mastering these algorithms empowers professionals to address challenges in sectors such as transportation, telecommunications, and social networking, where understanding the connections and flow within large data sets is crucial.

### **Navigation:** <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Cat%20with%20Wry%20Smile.png" alt="Cat with Wry Smile" width="25" height="25" />

🔙 **Previous Chapter:** [Dynamic Programming](chapter-7-dynamic-programming.md)  
Explore optimization strategies for solving recursive problems with efficiency.

🔜 **Next Chapter:** [Advanced Data Structures](chapter-9-advanced-data-structures.md)  
Delve into complex structures that provide sophisticated means to manage and organize data.

[![Previous](https://img.shields.io/badge/Previous-Dynamic_Programming-blue?style=for-the-badge)](chapter-7-dynamic-programming.md)
[![Next](https://img.shields.io/badge/Next-Advanced_Data_Structures-green?style=for-the-badge)](chapter-9-advanced-data-structures.md)
