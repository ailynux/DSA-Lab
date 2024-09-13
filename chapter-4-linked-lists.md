# Chapter 4: Linked Lists 📕

Welcome to Chapter 4 of the **Data Structures and Algorithms** repository! This chapter focuses on Linked Lists, a fundamental data structure used to store a sequence of elements, where each element points to the next one in the sequence.

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Cat%20with%20Wry%20Smile.png" alt="Cat with Wry Smile" width="65" height="65" /> What are Linked Lists?

A **Linked List** is a linear data structure where each element (called a "node") contains:
- **Data**: The value stored in the node.
- **Pointer (or reference)**: A link to the next node in the sequence.

Unlike arrays, linked lists do not have a fixed size and can dynamically grow or shrink by adding or removing nodes. They are useful when frequent insertion and deletion of elements are required.

### Key Types of Linked Lists:
1. **Singly Linked List**: Each node points to the next node, and the last node points to `null` (or `None` in Python).
2. **Doubly Linked List**: Each node has two pointers, one to the next node and one to the previous node.
3. **Circular Linked List**: The last node in the list points back to the first node, forming a loop.

![image](https://github.com/user-attachments/assets/df7a4ed0-3a1d-4016-9f0d-f41fcb87660b)

---

## 📋 Operations on Linked Lists

### 1. **Insertion**
You can insert a new node at:
- **Beginning**: Update the new node to point to the current head and set the new node as the head.
- **End**: Traverse to the end and update the last node's pointer to the new node.
- **Middle**: Insert a node after a given position by adjusting the previous and next pointers.

### 2. **Deletion**
To remove a node:
- **From Beginning**: Set the head to point to the next node.
- **From End**: Traverse to the node before the last one and set its next pointer to `null`.
- **From Middle**: Find the node to be deleted and adjust the pointers of the neighboring nodes.

### 3. **Traversal**
You can traverse a linked list by starting at the head and following each pointer until you reach the end.

### Python Example: Singly Linked List
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last_node = self.head
        while last_node.next:
            last_node = last_node.next
        last_node.next = new_node

    def delete_node(self, key):
        temp = self.head
        if temp and temp.data == key:
            self.head = temp.next
            temp = None
            return
        prev = None
        while temp and temp.data != key:
            prev = temp
            temp = temp.next
        if temp is None:
            return
        prev.next = temp.next
        temp = None

    def print_list(self):
        current = self.head
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")

# Example usage
ll = LinkedList()
ll.insert_at_end(1)
ll.insert_at_end(2)
ll.insert_at_end(3)
ll.print_list()

ll.delete_node(2)
ll.print_list()
```
## 📈 Advantages and Disadvantages

### **Advantages**:
- **Dynamic Size**: Linked lists can grow or shrink as needed, unlike arrays with a fixed size.
- **Efficient Insertions/Deletions**: Inserting and deleting elements is faster compared to arrays because there's no need to shift elements.

### **Disadvantages**:
- **No Direct Access**: You can't directly access elements by index like in an array; you must traverse the list.
- **More Memory**: Each node requires extra memory for storing a pointer to the next node.

---

## 📝 Practice Problems

### 1. **Reverse a Linked List**  
- **Challenge**: Reverse a singly linked list such that the last node becomes the head.  
- **Hint**: Use three pointers: `prev`, `current`, and `next`.

### 2. **Detect a Cycle in a Linked List**  
- **Challenge**: Determine if a linked list has a cycle (i.e., if a node points back to an earlier node).  
- **Hint**: Use Floyd's cycle detection algorithm (also known as the **Tortoise and Hare Algorithm**).

### 3. **Merge Two Sorted Linked Lists**  
- **Challenge**: Given two sorted linked lists, merge them into a single sorted linked list.  
- **Hint**: Use a two-pointer technique to traverse both lists simultaneously.

### 4. **Find the Middle of a Linked List**  
- **Challenge**: Find the middle node of a singly linked list.  
- **Hint**: Use two pointers—move one pointer twice as fast as the other.

---

## 📈 Summary

Linked lists are a fundamental data structure that provides efficient insertions and deletions. They are often used in scenarios where dynamic resizing is necessary or when frequent insertions and deletions are required. However, the lack of direct access to elements can be a drawback in some situations.

By mastering linked lists, you'll gain a deeper understanding of how data can be managed dynamically in memory, preparing you for more complex data structures like trees and graphs.

## 🔗 Navigation

🔙 **Previous Chapter:** [Hashmaps and Sets](chapter-3-hashmaps-and-sets.md)  
Explore more complex data structures that power dynamic data indexing and retrieval.

🔜 **Next Chapter:** [Stacks and Queues](chapter-5-stacks-and-queues.md)  
Understand how to manage data in a structured, linear fashion using stacks and queues.

[![Previous](https://img.shields.io/badge/Previous-Hashmaps_and_Sets-blue?style=for-the-badge)](chapter-3-hashmaps-and-sets.md)
[![Next](https://img.shields.io/badge/Next-Stacks_and_Queues-green?style=for-the-badge)](chapter-5-stacks-and-queues.md)
