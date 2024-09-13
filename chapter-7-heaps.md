# Chapter 7: Heaps <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/World%20Map.png" alt="World Map" width="75" height="75" />

<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Eye%20in%20Speech%20Bubble.png" alt="Eye in Speech Bubble" width="55" height="55" /> Welcome to Chapter 7 of the **Data Structures and Algorithms** repository! In this chapter, we'll explore heaps, a specialized tree-based data structure that is extremely useful for implementing priority queues. Heaps help manage data in a way that the highest (or lowest) priority element is always at the front.

<p align="center">
  <img src="https://github.com/user-attachments/assets/ac0404c5-cb8f-4d04-a0b2-d0d7007df6ec" width="250" alt="Descriptive Alt Text">
  <img src="https://github.com/user-attachments/assets/f675d223-fc7a-41d6-9c93-d3652f5feea2" width="250" alt="Descriptive Alt Text">
  <img src="https://github.com/user-attachments/assets/45f76e23-3516-464e-b39f-1857fc7cfa06" width="250" alt="Descriptive Alt Text">
</p>

## 📚 What are Heaps? <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Face%20with%20Monocle.png" alt="Face with Monocle" width="55" height="55" />

A heap is a complete binary tree which satisfies the heap property; it is in a specific order based on the values of its nodes. Heaps can be of two types, depending on the order:
- **Max-Heap**: The value of each node is less than or equal to the value of its parent, with the maximum-value element at the root.
- **Min-Heap**: The value of each node is greater than or equal to the value of its parent, with the minimum-value element at the root.

![image](https://github.com/user-attachments/assets/cb496207-d371-454e-b7af-6bb160c86ad2)

### Key Concepts:
- **Heap Property**: The key property defining the structure of the heap.
- **Complete Binary Tree**: A binary tree in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible.

### Common Operations:
- **Insertion**: Adding an element to the heap while maintaining the heap property.
- **Deletion**: Removing the root element from the heap and ensuring the heap property is maintained post-removal.
- **Heapify**: The process to rearrange the heap to maintain the heap property.
- **Peek**: Retrieving the root element without removing it from the heap.

## 📖 Example: Implementing Basic Operations

### Python Implementation
```python
import heapq

# Creating a Min-Heap
heap = []
heapq.heappush(heap, 25)
heapq.heappush(heap, 35)
heapq.heappush(heap, 15)
heapq.heappush(heap, 5)

print("Initial Heap:", heap)

# Removing element from the heap
smallest = heapq.heappop(heap)
print("Smallest element:", smallest)
print("Heap after removal:", heap)

# Peek element
print("Peek element:", heap[0])
```
## 🧩 Practice Problems

Challenge yourself with these heap-related problems to solidify your understanding and improve your algorithmic skills:

1. **Find the Kth Largest Element**:
    - 🏆 **Task**: Utilize a min-heap to determine the kth largest element in an unsorted array. This is a common interview question that tests your ability to manipulate heap properties.
    - **Example**:
      ```python
      import heapq

      def find_kth_largest(nums, k):
          min_heap = nums[:k]
          heapq.heapify(min_heap)
          for num in nums[k:]:
              if num > min_heap[0]:
                  heapq.heapreplace(min_heap, num)
          return min_heap[0]
      ```

2. **Merge K Sorted Arrays**:
    - 🔄 **Task**: Merge k sorted arrays into a single sorted array using a heap. This problem demonstrates the efficiency of heaps in sorting and merging data.
    - **Example**:
      ```python
      def merge_arrays(lists):
          merged_list = []
          heap = [(lst[0], i, 0) for i, lst in enumerate(lists) if lst]
          heapq.heapify(heap)

          while heap:
              val, list_ind, element_ind = heapq.heappop(heap)
              merged_list.append(val)
              if element_ind + 1 < len(lists[list_ind]):
                  next_tuple = (lists[list_ind][element_ind + 1], list_ind, element_ind + 1)
                  heapq.heappush(heap, next_tuple)

          return merged_list
      ```

3. **Continuous Median**:
    - 📊 **Task**: Design a data structure that continuously finds the median in a stream of numbers. This advanced problem highlights the dynamic utility of heaps in statistics and real-time data analysis.
    - **Example**:
      ```python
      from heapq import *

      class MedianFinder:

          def __init__(self):
              self.heaps = [], []

          def addNum(self, num):
              small, large = self.heaps
              heappush(small, -heappushpop(large, num))
              if len(large) < len(small):
                  heappush(large, -heappop(small))

          def findMedian(self):
              small, large = self.heaps
              if len(large) > len(small):
                  return float(large[0])
              return (large[0] - small[0]) / 2.0
      ```
---
## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Grinning%20Face%20with%20Smiling%20Eyes.png" alt="Grinning Face with Smiling Eyes" width="25" height="25" /> Summary

Heaps are not merely theoretical constructs but are versatile and efficient tools essential for managing prioritized data across various applications. Mastery of heaps is crucial for any software developer looking to implement quick access data structures for priority-based scheduling, network bandwidth management, and other scenarios where timely access to high-priority elements is required. These skills open up a broad range of efficient solutions for complex algorithmic challenges.

### **Navigation:**

🔙 **Previous Chapter:** [Trees and Graphs](chapter-6-trees-and-graphs.md)  
🔜 **Next Chapter:** [Greedy Algorithms](chapter-8-greedy-algorithms.md)

[![Previous](https://img.shields.io/badge/Previous-Trees_and_Graphs-blue?style=for-the-badge)](chapter-6-trees-and-graphs.md)
[![Next](https://img.shields.io/badge/Next-Dynamic_Programming-green?style=for-the-badge)](chapter-8-greedy-algorithms.md)

