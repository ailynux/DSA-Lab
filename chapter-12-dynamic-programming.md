# Chapter 12: Dynamic Programming <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Hushed%20Face.png" alt="Hushed Face" width="75" height="75" />

Welcome to Chapter 12 of the **Data Structures and Algorithms** repository! In this chapter, we delve into Dynamic Programming (DP), a method for solving complex problems by breaking them down into simpler subproblems. It is especially useful for optimization questions where you're looking to find the best solution among many possibilities.

## What is Dynamic Programming? <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Robot.png" alt="Robot" width="45" height="45" />

Dynamic Programming is both a mathematical optimization method and a computer programming method. In both contexts, it refers to simplifying a complicated problem by breaking it down into simpler sub-problems in a recursive manner. 🧠

![image](https://github.com/user-attachments/assets/47f38ab4-431e-4904-a20f-7c7da3aec4e2)


### Key Concepts:
- **Overlapping Subproblems**: DP is applicable when a problem breaks down into subproblems that recur multiple times.
- **Optimal Substructure**: A problem exhibits optimal substructure if an optimal solution to the whole problem contains optimal solutions to the sub-problems.

### Common Techniques:
- **Memoization**: Storing the results of expensive function calls and returning the cached result when the same inputs occur again.
- **Tabulation**: Storing the result of a previous result in a table (usually an array).

## 📖 Example: Implementing Basic Techniques

### Python Implementation of Fibonacci Series <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Activities/Chess%20Pawn.png" alt="Chess Pawn" width="45" height="45" />

#### Memoization Approach
```python
def fib(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 2:
        return 1
    memo[n] = fib(n-1, memo) + fib(n-2, memo)
    return memo[n]
```
#### Tabulation Approach
```python
def fib(n):
    if n <= 2:
        return 1
    fib_table = [0] * (n + 1)
    fib_table[1] = 1
    fib_table[2] = 1
    for i in range(3, n + 1):
        fib_table[i] = fib_table[i - 1] + fib_table[i - 2]
    return fib_table[n]
```
## 📖 Advanced Example: Dynamic Programming in Use
#### Python Implementation of 0/1 Knapsack Problem
```python
def knapSack(W, wt, val, n):
    K = [[0 for x in range(W + 1)] for x in range(n + 1)]
 
    # Build table K[][] in bottom-up manner
    for i in range(n + 1):
        for w in range(W + 1):
            if i == 0 or w == 0:
                K[i][w] = 0
            elif wt[i-1] <= w:
                K[i][w] = max(val[i-1] + K[i-1][w-wt[i-1]],  K[i][w])
            else:
                K[i][w] = K[i][w]
 
    return K[n][W]
```
## 🧩 Practice Problems

Enhance your problem-solving skills with these dynamic programming challenges:

1. **Climbing Stairs** 🧗‍♂️
   - **Problem**: Determine how many distinct ways you can climb to the top of a staircase of `n` steps, taking 1 or 2 steps at a time.
   - **Insight**: Use a bottom-up approach to build the solution from smaller problems up.

2. **Coin Change Problem** 💰
   - **Problem**: Compute how many different ways you can make change for an amount, given an array of coin denominations.
   - **Insight**: This classic problem can be solved efficiently by understanding the combinations of coins that sum up to the total amount.

3. **Longest Increasing Subsequence** 📈
   - **Problem**: Find the length of the longest subsequence in a sequence such that all elements of the subsequence are sorted in increasing order.
   - **Insight**: This involves deciding when to extend a subsequence and when to merge with existing ones.

## 💡 Common Pitfalls in Dynamic Programming

Avoid these frequent mistakes to enhance your DP strategy:

- **Overcomplicating the Recursive Solution**: Initiating with a top-down approach without clear memoization can lead to redundant calculations and an increase in complexity.
- **Failing to Identify the Base Cases**: Incorrect or missing base cases can lead to incorrect results or infinite loops.
- **Ignoring Space Complexity**: While reducing time complexity is critical, it’s also essential to consider the space requirements of your DP solution.

---

## 📈 Summary

**Dynamic Programming** is a powerful technique for solving optimization challenges and is pivotal in applications across various industries. It provides a structured method to solve problems where decisions are interdependent, optimizing sequential decisions to achieve the best outcome.


### **Navigation:**

🔙 **Previous Chapter:** [Backtracking](chapter-11-backtracking.md)  
Explore how heaps manage data with priority structures for efficient data retrieval.

🔜 **Next Chapter:** [Coding Tools and Tips](chapter-13-coding-tools-tips.md)  
Dive into algorithms that traverse, search, and optimize data structures in complex networks.

[![Previous](https://img.shields.io/badge/Previous-Backtracking-blue?style=for-the-badge)](chapter-11-backtracking.md)
[![Next](https://img.shields.io/badge/Next-coding_tools_tips-green?style=for-the-badge)](chapter-13-coding-tools-tips.md)
