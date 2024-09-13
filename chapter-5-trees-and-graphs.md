# <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Chart%20Decreasing.png" alt="Chart Decreasing" width="75" height="75" /> Chapter 5: Trees and Graphs <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Chart%20Increasing.png" alt="Chart Increasing" width="75" height="75" />

Welcome to Chapter 5 of the **Data Structures and Algorithms** repository! This chapter covers two crucial hierarchical data structures: trees and graphs. These structures are fundamental in scenarios ranging from database operations to advanced network analysis, providing a robust means of organizing and processing information efficiently.

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Camping.png" alt="Camping" width="55" height="55" /> What are Trees?

A tree is a non-linear data structure that simulates a hierarchical tree structure, with a root value and subtrees of children with a parent node, represented as a set of linked nodes.

### Key Concepts:
- **Root**: The top node in a tree.
- **Child**: A node directly connected to another node when moving away from the Root.
- **Parent**: The converse notion of a child.
- **Leaf**: A node with no children.
- **Depth**: The distance from the root to the node.
- **Height**: The depth of the deepest node.

  ![image](https://github.com/user-attachments/assets/21bd3060-1607-4522-a7ec-fa1f54deb9a4)


### Common Tree Types:
- **Binary Tree**: A tree where each node has up to two children.
- **Binary Search Tree (BST)**: A binary tree in which each node has a key greater than all the keys in the node's left subtree and less than those in its right subtree.

### Common Operations:
- **Insertion**: Add a node to the tree.
- **Deletion**: Remove a node from the tree.
- **Traversal**: Process nodes in the tree in a certain order (e.g., in-order, pre-order, post-order).

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Milky%20Way.png" alt="Milky Way" width="95" height="95" />What are Graphs?

Graphs are networks consisting of nodes (also called vertices) connected by edges (also called arcs). A graph may be undirected, implying bidirectional ties, or directed, indicating directed relationships.

### Key Concepts:
- **Vertex**: The fundamental unit of which graphs are formed.
- **Edge**: Connection between two vertices.
- **Path**: A sequence of vertices connected by edges.
- **Cycle**: A path that starts and ends at the same vertex.

### Common Graph Types:
- **Undirected Graph**: Edges have no direction.
- **Directed Graph (Digraph)**: Edges have a direction.
- **Weighted Graph**: Each edge has a weight or cost associated with it.

### Common Operations:
- **Add Vertex/Edge**: Add a new vertex or edge to the graph.
- **Find Path**: Find a path from one vertex to another.
- **Traversal**: Visit each vertex in the graph.

## 📖 Example: Implementing Basic Operations

### Tree Example - *python*
```python
class Node:
    def __init__(self, key):
        self.left = None
        self.right = None
        self.val = key

# A function to insert a new node with the given key
def insert(root, key):
    if root is None:
        return Node(key)
    else:
        if root.val < key:
            root.right = insert(root.right, key)
        else:
            root.left = insert(root.left, key)
    return root

# A function to do inorder tree traversal
def inorder(root):
    if root:
        inorder(root.left)
        print(root.val)
        inorder(root.right)

# Driver program to test the above functions
root = Node(50)
root = insert(root, 30)
root = insert(root, 20)
root = insert(root, 40)
root = insert(root, 70)
root = insert(root, 60)
root = insert(root, 80)

inorder(root)
```
### Graph Example - *python*
```python
graph = {
    'A' : ['B','C'],
    'B' : ['D', 'E'],
    'C' : ['F'],
    'D' : [],
    'E' : ['F'],
    'F' : []
}

def find_path(graph, start, end, path=[]):
    path = path + [start]
    if start == end:
        return path
    if start not in graph:
        return None
    for node in graph[start]:
        if node not in path:
            newpath = find_path(graph, node, end, path)
            if newpath: return newpath
    return None

print("Path from A to F:", find_path(graph, 'A', 'F'))
```
## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Stop%20Sign.png" alt="Stop Sign" width="45" height="45" /> Practice Problems

Test your understanding and enhance your skills with these challenges:

1. **Tree Height**: 🌳 Write a function to determine the height of a binary tree. The height is the number of edges on the longest downward path between the root and a leaf.

    ```python
    def height(node):
        if node is None:
            return 0
        else:
            left_height = height(node.left)
            right_height = height(node.right)
            return max(left_height, right_height) + 1
    ```

2. **Graph Cycle Detection**: 🔍 Implement an algorithm to check whether a graph contains a cycle. This is crucial for understanding whether a dataset has any dependencies or loops.

    ```python
    def has_cycle(graph):
        visited = set()
        stack = set()

        def visit(vertex):
            if vertex in stack:
                return True
            if vertex in visited:
                return False

            visited.add(vertex)
            stack.add(vertex)
            for neighbor in graph[vertex]:
                if visit(neighbor):
                    return True
            stack.remove(vertex)
            return False

        return any(visit(v) for v in graph)
    ```

3. **Route Between Nodes**: 🚦 Given a directed graph, design an algorithm to find out whether there is a route between two nodes. This can help in scenarios like network traffic routing, social networks, and more.

    ```python
    def find_route(graph, start, end):
        from collections import deque
        queue = deque([start])
        visited = set()

        while queue:
            node = queue.popleft()
            if node == end:
                return True
            if node not in visited:
                visited.add(node)
                queue.extend(graph[node])
        return False
    ```
---

## Summary <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Roller%20Coaster.png" alt="Roller Coaster" width="75" height="75" />

Trees and graphs are not just theoretical concepts; they are sophisticated structures that enable efficient organization and processing of complex hierarchical and networked data. Mastery of these structures is crucial for developing solutions that require advanced data manipulation capabilities and for solving problems that involve large-scale data management.

### **Navigation:**

🔙 **Previous Chapter:** [Stacks and Queues](chapter-4-stacks-and-queues.md)  
🔜 **Next Chapter:** [Heaps](chapter-6-heaps.md)

[![Previous](https://img.shields.io/badge/Previous-Stacks_and_Queues-blue?style=for-the-badge)](chapter-4-stacks-and-queues.md)
[![Next](https://img.shields.io/badge/Next-Heaps-green?style=for-the-badge)](chapter-6-heaps.md)
