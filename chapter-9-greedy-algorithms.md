# Chapter 9: Greedy Algorithms 💰

Welcome to the **Greedy Algorithms** section of the **Data Structures and Algorithms** repository! This section is dedicated to exploring algorithms that make locally optimal choices at each step in the hope of finding a globally optimal solution. Greedy algorithms are widely used in areas such as network routing, scheduling, and optimization problems.

## 📘 Introduction to Greedy Algorithms

Greedy algorithms build up a solution piece by piece, always choosing the next piece that offers the most immediate benefit. They are known for their simplicity and efficiency in solving optimization problems where a global solution can be achieved through a series of locally optimal decisions.

### Key Concepts:
- **Greedy Choice Property**: At each step, make the best possible decision based on the current situation without reconsidering previous decisions.
- **Optimal Substructure**: A problem has this property if an optimal solution can be constructed efficiently from optimal solutions to its subproblems.

## 📚 Key Concepts in Greedy Algorithms

This section introduces essential problems and techniques that demonstrate the power and utility of greedy algorithms.

### **Introduction to Greedy Algorithms**  
Greedy algorithms build a solution piece by piece, making the most optimal choice at each step without reconsidering previous decisions. This approach works well for problems where local decisions lead to a globally optimal solution.

---

### **Activity Selection Problem**  
The activity selection problem involves choosing the maximum number of activities that don't overlap. Each activity has a start and finish time, and the goal is to select the largest number of compatible activities.  
- **Approach**: Sort activities by finish time and always pick the next activity that finishes the earliest and is compatible with the previously selected activities.

---

### **Huffman Encoding**  
Huffman encoding is a greedy algorithm used in data compression. It assigns variable-length codes to characters based on their frequencies, with more frequent characters receiving shorter codes.  
- **Approach**: Build a binary tree where the most frequent characters have shorter paths, resulting in efficient data compression.

---

### **Minimum Spanning Tree (MST)**  
A Minimum Spanning Tree (MST) is a subset of the edges of a graph that connects all the vertices together, without any cycles, and with the minimum possible total edge weight.  
- **Algorithms**: 
  - **Kruskal’s Algorithm**: Sort edges by weight and add them to the MST while avoiding cycles.
  - **Prim’s Algorithm**: Start with one node and grow the MST by adding the smallest edge connecting the tree to a new vertex.

---

### **Dijkstra's Shortest Path Algorithm**  
Dijkstra’s algorithm finds the shortest path from a source node to all other nodes in a weighted graph, where all edge weights are non-negative.  
- **Approach**: It uses a priority queue to greedily select the shortest known distance to a vertex and update neighboring distances based on the current vertex.

---

### **Job Scheduling Problem**  
The job scheduling problem involves scheduling tasks with deadlines to maximize total profit. Each task has a profit and a deadline, and the goal is to complete as many profitable jobs within their deadlines.  
- **Approach**: Sort jobs by profit and assign each job to the latest available slot before its deadline, ensuring that the schedule is filled with the most profitable jobs.

---

### **Fractional Knapsack Problem**  
In the fractional knapsack problem, you are given items with weights and values and a maximum weight limit for a knapsack. You can take fractions of items to maximize the total value.  
- **Approach**: Sort items by value-to-weight ratio and take as much of the highest ratio items as possible until the knapsack is full.

---

Each of these problems demonstrates how greedy algorithms excel at making the best local choice in hopes of achieving the globally optimal solution. Mastering these techniques will help you solve a variety of optimization problems efficiently.

---

## 📝 Example: Activity Selection Problem

One common problem that can be solved using a greedy approach is the **Activity Selection Problem**, where we are given a set of activities with start and finish times. The goal is to select the maximum number of non-overlapping activities.

### Python Example:
```python
def activity_selection(activities):
    # Sort activities by finish time
    activities.sort(key=lambda x: x[1])
    
    # The first activity is always selected
    selected_activities = [activities[0]]
    
    # Iterate through the sorted activities
    for i in range(1, len(activities)):
        # If this activity starts after the last selected activity finishes, select it
        if activities[i][0] >= selected_activities[-1][1]:
            selected_activities.append(activities[i])
    
    return selected_activities

# Activities represented as (start, finish) pairs
activities = [(1, 4), (3, 5), (0, 6), (5, 7), (3, 9), (5, 9), (6, 10), (8, 11), (8, 12), (2, 14), (12, 16)]

# Run the greedy algorithm
print(activity_selection(activities))
```
## 🔍 Solve Problems Section

Test your knowledge and practice these common problems using greedy algorithms:

1. **Fractional Knapsack Problem**  
   - 🏋️ **Challenge**: Maximize the total value when fractions of items can be taken. Implement a solution using a greedy approach based on the value-to-weight ratio of items.
   - 💡 **Hint**: Sort items by their value-to-weight ratio and take the most valuable first.

2. **Job Sequencing Problem**  
   - 🗓️ **Challenge**: Schedule jobs to maximize profit within their respective deadlines. Use a greedy approach to select the most profitable jobs.
   - 💡 **Hint**: Prioritize jobs with higher profit, but ensure they fit within their deadlines.

3. **Huffman Encoding**  
   - 🔤 **Challenge**: Implement Huffman’s greedy algorithm for lossless data compression, which constructs an optimal prefix-free code for the given frequencies of symbols.
   - 💡 **Hint**: Use a priority queue to build the tree for optimal encoding.

4. **Prim's Algorithm**  
   - 🛠️ **Challenge**: Construct a Minimum Spanning Tree (MST) using Prim’s algorithm for a weighted, connected graph.
   - 💡 **Hint**: Start with any node, and repeatedly add the smallest edge connecting the tree to a new vertex.

---

## 📈 Summary

Greedy algorithms are a powerful technique in computer science, providing efficient solutions to many optimization problems. Their strength lies in their ability to make fast, local decisions, which in many cases lead to globally optimal solutions. While greedy algorithms do not always guarantee an optimal solution for every problem, they shine when both the **greedy choice property** and **optimal substructure** are present.

Mastering greedy algorithms is essential for solving a wide range of problems in areas like:
- **Data compression** (Huffman Encoding)
- **Scheduling** (Job Sequencing)
- **Graph theory** (Prim’s Algorithm, Minimum Spanning Tree)

The elegance of greedy algorithms is their simplicity and speed, making them an essential tool in your algorithmic toolkit.

---

## 🔗 Navigation

🔙 **Previous Chapter:** [Graph Algorithms](chapter-8-graph-algorithms.md)  
Explore traversal, shortest path, and network flow algorithms used to optimize and search through complex graphs.

🔜 **Next Chapter:** [Binary Search](chapter-10-binary-search.md)  
Learn how to efficiently search sorted arrays and solve complex search problems with this divide-and-conquer algorithm.

[![Previous](https://img.shields.io/badge/Previous-Graph_Algorithms-blue?style=for-the-badge)](chapter-8-graph-algorithms.md)
[![Next](https://img.shields.io/badge/Next-Binary_Search-green?style=for-the-badge)](chapter-10-binary-search.md)
