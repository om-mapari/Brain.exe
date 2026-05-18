---
title: Learn By Patterns
created: 2026-04-18
updated: 2026-05-18
tags:
    - om
---
---

## 1️⃣ Step 1: Check Constraints 📌

### 🔹 Small n (≤ 20)

- Brute force is valid
- Backtracking / Recursion
- Exponential allowed:
    - `2^n`, `n!`
- Try all possible Permutations & Combinations 

---

### 🔹 Medium n (10³ → 10⁶)

- ❌ No brute force
- Use:
    - Linear Time →  `O(n) / O(n log n)`
- Patterns
    - `Greedy`
    - Two pointers - with sorting
    - Heap
    - Dynamic Programming

---

### 🔹 Large n (≥ 10⁷)

- ❌ No linear solutions
- Use:
    - `O(log n)  only`
    - Binary search
    - Math formulas
    - O(1) tricks

---

## 2️⃣ Step 2: Analyze Input Format

### 🌳 Tree / BST

- DFS:
    - All paths
    - Recursive traversal
    - Pre/In/Post order
- BFS:
    - level-by-level
    - shortest path in unweighted tree
- Focus:
    - tree properties, parent-child relationships

---

### 🌐 Graph (nodes + edges)

- BFS → shortest path
- DFS → connected components
- Union-Find:
    - "connected components"
    - "number of groups"
- Topological sort:
    - for Dependencies

---

### 🧩 2D Grid / Matrix

- DFS/BFS:
    - Islands problems
- Union-Find:
    - Connected regions
- DP:
    - Path problems
- Consider: 4-directional or 8-directional movement

---

### 📊 Sorted Array

- Two pointers technique - [[../1. Two Pointers/index|1. Two Pointers]]
- Binary search
- Greedy

---

### 🔤 String

- Two pointers:
    - Palindrome
- Sliding window:
    - Substrings
- Trie:
    - Word problems
- Stack:
    - parentheses/brackets

---

### 🔗 Linked List

- Two pointers -> Fast/Slow pointers
- Dummy node techniques
- Cycle detection

---

## 3️⃣ Step 3: Analyze Output Format

### 📚 List of Lists (combinations, subsets, paths)

- Backtracking is almost always the answer
- Generate all possibilities
- Use recursion with choice/no-choice pattern

---

### 🔢 Single Number Output (max/min profit, cost, ways, jumps):

- Dynamic Programming for optimization
- Greedy for local optimal choices
- Mathematical approach for counting

---

### 🔄 Modified Array / String  (in-place operations):

- Two Pointers for in-place modifications

---

### 📈 Ordered List (sorted sequence, valid task order):

- Sorting with custom comparators
- Topological sort
- Heap

---

## 4️⃣ Step 4: Keyword → Pattern Mapping 🔑

### 🧠 Dynamic Programming

- "number of ways"
- "Maximum/minimum" + "sum/profit/cost"
- "Can you reach"
- "Longest/shortest subsequence"
- "Optimal" or "best"

---

### 👉 Two Pointers

- "palindrome"
- "sorted array"
- "target sum"
- "remove duplicates"

---

### ⛰ Heap

- "k largest/smallest"
- "top k"
- "median"
- "priority"

---

### 📚 Stack

- "Parentheses" or "brackets"
- "valid expression"
- "Nested structure"
- "Undo operations"

---

### 📉 Monotonic Stack

- "Next greater element"
- "Next smaller element"

---

### 🗺 HashMap

- "Count frequency"
- "Find duplicates"
- "Anagram"

---

### 🌲 Trie

- "Word search"
- "Word prefixes"

---

### ⚡ Greedy

- "Minimum operations"

---

### 🔗 Union Find

- "Connected components"
- "Number of groups"

---

### 🔍 Binary Search

- "kth element"
- "Search in sorted"
- "Minimize maximum"
- "First/last occurrence"

---

### 🔢 Bit Manipulation

- "XOR" operations
- ""Single number" problems
- "power of 2"

---

### 📐 Math / Geometry

- "GCD / LCM"
- "prime numbers"
- "Angle calculations"
- "Coordinate”

---

### 🎮 Game Theory

- "Optimal strategy"
- "Win/lose scenarios"
- "Minimax"

---

### 🪟 Sliding Window

- "Substring" with conditions
- Subarray" with fixed/variable size
- "Maximum/minimum window"
- "Contains all"

---

## 5️⃣ How to Use This 

- Step-by-step:
    1. Constraints
    2. Input
    3. Output
    4. Keywords

- Practice strategy:
    - Solve **5–10 problems per pattern**
    - Practice **only classification**
    - Maintain personal keyword notes

---
