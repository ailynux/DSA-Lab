# Chapter 10: Binary Search 🔍

Welcome to Chapter 10 of the **Data Structures and Algorithms** repository! In this chapter, we will explore **Binary Search**, an efficient algorithm used to find the position of a target value within a sorted array. Binary search is a divide-and-conquer algorithm that repeatedly divides the search interval in half, making it highly efficient.

---

## 🔍 What is Binary Search? <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Bomb.png" alt="Bomb" width="65" height="65" />

Binary Search is an algorithm that searches for a target value in a **sorted** array by repeatedly dividing the search interval in half. 

![image](https://github.com/user-attachments/assets/b8ee8cb0-1aff-4aa5-b73b-8c93337f2de1)

### Key Concepts:
- **Divide-and-Conquer**: At each step, the algorithm eliminates half of the remaining elements.
- **Sorted Input**: Binary search only works on sorted collections.
- **Time Complexity**: O(log n), making it much faster than linear search (O(n)).

### Binary Search Algorithm:
1. Find the middle element of the array.
2. If the middle element equals the target, the search is complete.
3. If the target is less than the middle element, search the left half.
4. If the target is greater than the middle element, search the right half.
5. Repeat until the target is found or the interval is empty.

---

## 📋 Binary Search Implementation

### Python Example: Recursive Binary Search
```python
def binary_search(arr, low, high, target):
    if high >= low:
        mid = (high + low) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] > target:
            return binary_search(arr, low, mid - 1, target)
        else:
            return binary_search(arr, mid + 1, high, target)
    else:
        return -1

# Example usage
arr = [2, 3, 4, 10, 40]
target = 10
result = binary_search(arr, 0, len(arr)-1, target)
if result != -1:
    print("Element found at index", result)
else:
    print("Element not present in array")
```
### Python Example: Iterative Binary Search
```python
def binary_search_iterative(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (high + low) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

# Example usage
arr = [2, 3, 4, 10, 40]
target = 10
result = binary_search_iterative(arr, target)
if result != -1:
    print("Element found at index", result)
else:
    print("Element not present in array")
```
## 📝 Practice Problems

### 1. **Find First and Last Position of Element in Sorted Array**  
- **Challenge**: Given a sorted array of integers, find the first and last position of a given target. If the target is not found, return `[-1, -1]`.  
- **Hint**: Use modified binary search to find both first and last occurrences.

### 2. **Search in a Rotated Sorted Array**  
- **Challenge**: Given a rotated sorted array, search for a target value.  
- **Hint**: Modify the binary search to handle the rotated segments of the array.

### 3. **Find Peak Element**  
- **Challenge**: Find a peak element in an array. A peak element is one that is greater than its neighbors.  
- **Hint**: Use binary search to locate the peak by comparing middle elements with their neighbors.

### 4. **Square Root of a Number**  
- **Challenge**: Implement a function to compute the square root of a number using binary search.  
- **Hint**: Search for the square root by narrowing down the search range between `0` and the number itself.

---

## 📈 Summary

Binary search is a powerful tool for quickly finding elements in sorted arrays. By repeatedly dividing the array in half, it reduces the time complexity to **O(log n)**, making it ideal for searching in large datasets. Mastering binary search prepares you to handle more complex problems like searching in rotated arrays, finding peaks, and efficiently calculating square roots.

## 🔗 Navigation

🔙 **Previous Chapter:** [Greedy Algorithms](chapter-9-greedy-algorithms.md)  
Explore optimization strategies where local decisions lead to globally optimal solutions.

🔜 **Next Chapter:** [Backtracking](chapter-11-backtracking.md)  
Learn how to solve constraint satisfaction problems using the backtracking algorithm.

[![Previous](https://img.shields.io/badge/Previous-Greedy_Algorithms-blue?style=for-the-badge)](chapter-9-greedy-algorithms.md)
[![Next](https://img.shields.io/badge/Next-Backtracking-green?style=for-the-badge)](chapter-11-backtracking.md)
