# Chapter 5: Stacks and Queues <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Grinning%20Cat.png" alt="Grinning Cat" width="65" height="65" />

Welcome to Chapter 5 of the **Data Structures and Algorithms** repository! This chapter introduces two essential linear data structures: stacks and queues. Both play a critical role in various computing scenarios, from managing data in a controlled order to handling real-time data processing.

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Abacus.png" alt="Abacus" width="75" height="75" /> What are Stacks?

A stack is a collection of elements that follows the Last In, First Out (LIFO) principle. The most recently added element is the first one to be removed.

### Key Concepts:
- **LIFO Principle**: Last In, First Out.
- **Push Operation**: Adds an element to the top of the stack.
- **Pop Operation**: Removes the top element from the stack.
- **Peek Operation**: Returns the top element without removing it from the stack.

### Common Uses:
- Undo mechanisms in text editors.
- Function call management in programming languages.

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Card%20Index%20Dividers.png" alt="Card Index Dividers" width="65" height="65" /> What are Queues?

A queue is a collection of elements that adheres to the First In, First Out (FIFO) principle. The first element added to the queue will be the first one to be removed.

### Key Concepts:
- **FIFO Principle**: First In, First Out.
- **Enqueue Operation**: Adds an element to the end of the queue.
- **Dequeue Operation**: Removes the element from the front of the queue.
- **Front Operation**: Provides access to the first element.

### Common Uses:
- Managing tasks in computing systems.
- Handling data in real-time processing like print spooling.

## 📖 Example: Implementing Basic Operations

### Stack Example
```python
stack = []
# Push elements
stack.append('a')
stack.append('b')
stack.append('c')
print("Stack:", stack)

# Pop element
print("Popped Element:", stack.pop())
print("Updated Stack:", stack)

# Peek element
print("Peek Element:", stack[-1])
```
### Queue Example
```python
from collections import deque

queue = deque()
# Enqueue elements
queue.append('a')
queue.append('b')
queue.append('c')
print("Queue:", list(queue))

# Dequeue element
print("Dequeued Element:", queue.popleft())
print("Updated Queue:", list(queue))

# Front element
print("Front Element:", queue[0])
```
## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Clipboard.png" alt="Clipboard" width="65" height="65" /> Practice Problems
1. **Balanced Parentheses**: 📚 Utilize a stack to verify whether parentheses in an expression are balanced. This fundamental use of stacks helps ensure that every opening symbol has a corresponding closing symbol in the correct order.

2. **Recent Calls Counter**: 📞 Implement a queue to monitor the number of calls received in a call center within the last minute. This simulates real-time data processing, typical in operations management.

3. **Reverse First K Elements of a Queue**: 🔁 Create a function that reverses the first k elements of a queue, an interesting twist that combines queue operations with array manipulation techniques.

## Summary <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Fountain%20Pen.png" alt="Fountain Pen" width="85" height="85" />

Stacks and queues are not just theoretical concepts but are foundational to developing efficient algorithms and managing data effectively in various software applications. Their intrinsic properties of order management—LIFO for stacks and FIFO for queues—allow developers to handle data with precision, ensuring optimal control over program flow and timing.

---

### Navigation

🔙 **Previous Chapter:** [Hashmaps and Sets](chapter-4-linked-lists.md)  
Explore more complex data structures that power dynamic data indexing and retrieval.

🔜 **Next Chapter:** [Stacks and Queues](chapter-6-trees-and-graphs.md)  
Understand how to manage data in a structured, linear fashion using stacks and queues.

[![Previous](https://img.shields.io/badge/Previous-Hashmaps_and_Sets-blue?style=for-the-badge)](chapter-3-hashmaps-and-sets.md)
[![Next](https://img.shields.io/badge/Next-Trees_and_Graphs-green?style=for-the-badge)](chapter-5-trees-and-graphs.md)

