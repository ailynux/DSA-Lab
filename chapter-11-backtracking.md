# Chapter 11: Backtracking 🔙 <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Cold%20Face.png" alt="Cold Face" width="75" height="75" />

Welcome to Chapter 11 of the **Data Structures and Algorithms** repository! This chapter will introduce you to **Backtracking**, a fundamental algorithmic technique used to solve problems by building a solution incrementally and abandoning solutions that fail to satisfy the constraints.

---

## 🔙 What is Backtracking?

Backtracking is an algorithmic technique for solving constraint satisfaction problems. It builds a solution step by step, and if a step leads to an invalid state, the algorithm **backtracks** by undoing the last step and trying another path. 

### Key Concepts:
- **Recursive Search**: Backtracking uses recursion to explore all possible configurations.
- **Pruning**: If a solution is found to be invalid at any point, the algorithm abandons it and moves backward to try a different solution.
- **Efficient Search**: By pruning invalid paths early, backtracking reduces the number of possible configurations to explore.

### Common Use Cases:
- **Solving Puzzles**: Sudoku, N-Queens, Crossword puzzles.
- **Pathfinding**: Finding all possible paths in a maze.
- **Combinatorial Problems**: Generating permutations and combinations.

---

## 📋 Backtracking Algorithm <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Dizzy.png" alt="Dizzy" width="55" height="55" />

The general steps in a backtracking algorithm are:
1. **Choose**: Choose an option from a set of options.
2. **Explore**: Recursively explore the option.
3. **Un-choose**: If the current option doesn’t lead to a solution, undo the choice (backtrack) and try a different option.

### Python Example: Solving N-Queens Problem
The N-Queens problem is a classic problem where you need to place N queens on an N×N chessboard such that no two queens attack each other.

```python
def is_safe(board, row, col):
    # Check this row on the left side
    for i in range(col):
        if board[row][i] == 1:
            return False

    # Check upper diagonal on the left side
    for i, j in zip(range(row, -1, -1), range(col, -1, -1)):
        if board[i][j] == 1:
            return False

    # Check lower diagonal on the left side
    for i, j in zip(range(row, len(board), 1), range(col, -1, -1)):
        if board[i][j] == 1:
            return False

    return True

def solve_n_queens(board, col):
    if col >= len(board):
        return True

    for i in range(len(board)):
        if is_safe(board, i, col):
            board[i][col] = 1

            if solve_n_queens(board, col + 1):
                return True

            board[i][col] = 0  # Backtrack

    return False

# Example usage
N = 4
board = [[0] * N for _ in range(N)]
if solve_n_queens(board, 0):
    for row in board:
        print(row)
else:
    print("No solution exists")
```
## 📝 Practice Problems

### 1. **N-Queens Problem**  
- **Challenge**: Place N queens on an N×N chessboard such that no two queens attack each other.  
- **Hint**: Use backtracking to explore possible configurations and prune invalid paths early.

### 2. **Sudoku Solver**  
- **Challenge**: Given a partially filled 9x9 grid, complete the puzzle by filling in numbers from 1 to 9.  
- **Hint**: Use backtracking to try different numbers, and backtrack when conflicts arise.

### 3. **Permutations of a String**  
- **Challenge**: Given a string, find all its permutations.  
- **Hint**: Use backtracking to swap characters and generate all permutations.

### 4. **Rat in a Maze**  
- **Challenge**: Given a maze, find all possible paths for a rat to reach the end.  
- **Hint**: Use backtracking to explore all possible paths, marking dead ends as invalid.

---

## 📈 Summary

Backtracking is an essential algorithmic technique for solving problems that require searching through a large space of possibilities while ensuring constraints are met. By pruning invalid paths early and using recursion to explore valid ones, backtracking is effective for a wide range of problems such as puzzle solving, pathfinding, and combinatorial optimization.

## 🔗 Navigation

🔙 **Previous Chapter:** [Binary Search](chapter-10-binary-search.md)  
Learn how to efficiently search sorted arrays and solve complex search problems with the binary search algorithm.

🔜 **Next Chapter:** [Dynamic Programming](chapter-12-dynamic-programming.md)  
Explore how to break down complex problems into simpler subproblems with dynamic programming.

