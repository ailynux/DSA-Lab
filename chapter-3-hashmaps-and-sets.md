# Chapter 3: Hashmaps and Sets <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Smilies/Disguised%20Face.png" alt="Disguised Face" width="55" height="55" />

Welcome to Chapter 3 of the **Data Structures and Algorithms** repository! This chapter focuses on two powerful data structures: hashmaps and sets. We'll explore how these structures can significantly improve the efficiency of data retrieval and manipulation, making them indispensable for solving complex problems in software development.

## 📚 What are Hashmaps?

Hashmaps, also known as hash tables, are data structures that store data in key-value pairs. They use a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.

### Key Concepts:
- **Hash Function**: A function that converts a given key into a specific slot in the hashmap.
- **Collisions**: Occurs when two keys hash to the same index; several techniques can resolve collisions.
- **Load Factor**: A measure that decides when to resize the hashmap to maintain its operational efficiency.
  
![image](https://github.com/user-attachments/assets/232bc11d-3673-4293-ad12-310f0b218aa3)

### Common Operations:
- **Insert**: Add a key-value pair to the hashmap.
- **Delete**: Remove a key-value pair by key.
- **Search**: Retrieve the value associated with a given key.
- **Traverse**: Go through each key-value pair in the hashmap.

## 🎻 What are Sets?

Sets are collections of unique elements. They are typically implemented as hash tables with keys and no corresponding values, focusing solely on membership presence.

### Key Concepts:
- **Uniqueness**: Each element in a set must be unique.
- **Implementation**: Often backed by a hashmap for efficient lookups.

### Common Operations:
- **Add**: Insert an element into the set.
- **Remove**: Delete an element from the set.
- **Contains**: Check if an element exists in the set.
- **Size**: Return the number of elements in the set.

## 📖 Example: Implementing Basic Operations

### Hashmap Example - *python*
```python
# Creating a hashmap
my_hashmap = {}
my_hashmap["name"] = "Alice"
my_hashmap["age"] = 30

# Accessing elements
print("Name:", my_hashmap["name"])

# Deleting element
del my_hashmap["age"]
print("Hashmap after deletion:", my_hashmap)
```
### Set Example - *python*
```python
# Creating a set
my_set = set()
my_set.add("apple")
my_set.add("banana")

# Checking for an element
print("Does set contain apple?", "apple" in my_set)

# Removing an element
my_set.remove("banana")
print("Set after removal:", my_set)
```
## 🎲 Practice Problems

Sharpen your skills with these hand-picked challenges:

1. **Unique Characters**: Can you write an algorithm using a set to determine if a string contains all unique characters? Try it out!
2. **Two Sum**: Given an array of integers, find two numbers such that they add up to a specific target. Use a hashmap to track indices.
3. **Group Anagrams**: How would you group an array of strings into anagrams? Use a hashmap to categorize them based on sorted characters as keys.

##  Summary <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Animals/T-Rex.png" alt="T-Rex" width="45" height="45" />

Hashmaps and sets are indispensable tools for data manipulation and rapid retrieval, making them essential for software solutions that manage and process large datasets. Mastery of these structures will elevate your problem-solving skills and help you tackle complex challenges with ease.

![image](https://github.com/user-attachments/assets/73cb62c1-bfd8-4930-8707-a9cc17013290)

---

### Navigation

🔙 **Previous Chapter:** [Arrays and Strings](chapter-2-arrays-and-strings.md)  
🔜 **Next Chapter:** [Linked Lists](chapter-4-linked-lists.md)

[![Previous](https://img.shields.io/badge/Go_to-Previous_Chapter-blue?style=for-the-badge)](chapter-2-arrays-and-strings.md)
[![Next](https://img.shields.io/badge/Go_to-Next_Chapter-brightgreen?style=for-the-badge)](chapter-4-linked-lists.md)

## 🤝 Connect with Me

I'm always excited to connect, collaborate, or help out in any way I can! Reach out to me directly here:

[![LinkedIn](https://img.shields.io/badge/Connect_with_me_on_LinkedIn-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/ailyn-diaz-802943225)

Feel free to contribute to this repository or suggest improvements. Let's learn and grow together!

---


