---
title: 1. Two Pointers
description: My Notes
tags:
    - dsa
created: 2026-04-17
updated: 2026-05-22
---
---

## 1️⃣ Core Idea

- Use **2 pointers (indices)** instead of 1
- Move them **in coordination**
- Goal → **reduce time, avoid extra space**

---

## 2️⃣ When to Think Two Pointer 🚀

### ✔️ Strong Signals

- ONLY ON -> Array / Linked List
- Sorted OR can be sorted
- Find:
    - `Pair / Triplet / Quadruple`
- Operations:
    - Merge
    - Remove duplicates
    - Rearrange elements
- Constraint:
    - **If No extra space allowed**
- Linked List:
    - Cycle detection
- Time Complaxcity:

| Approach    | Time                  | Space | Notes                |
| ----------- | --------------------- | ----- | -------------------- |
| Brute Force | O(n²)                 | O(1)  | Simple but slow      |
| HashMap     | O(n)                  | O(n)  | Fast but extra space |
| Two Pointer | O(n log n) - shorting | O(1)  | Optimal space        |

---

## 3️⃣ Types of Two Pointer Problems (Important)


### 1. 🔁 Opposite Ends (Most Common)

![[1-index.webp]]

>One pointer at start `s`, one at end `e`
>Move towards center  `while (s < e)`

#### 📌 Used in:

- Pair sum
- Palindrome
- Sorting / rearranging

#### Example Problems

- [[1. Two Sum]]
- 3Sum / 4Sum
- Container with most water
- Trapping rain water
- Reverse string/Array

---

### 2. 🐢 Slow & Fast Pointer

> Next type is using two pointers with different speed of movement. 
> Typically they starts from the left end, then the `fast pointer` advances fast and give some feedback to the `slow pointer` and do some calculation.

![[2-index.webp]]

#### 📌 Used in:

- Linked list problems
- Cycle detection

#### Example Problems

- Find the middle of a linked list
- Remove Dublicate from sorted LL - [[3. Slow Fast ptr]]
- Linked List Cycle
- Find duplicate number
- Remove nth node

---

### 3. 🔗 Two Arrays / Merging

> In this category, you will be given 2 arrays or lists, then have to process them with individual pointers.

![[3-index.jpg]]

#### 📌 Used in:

- Merge sorted arrays
- Intersection problems

#### Example Problems

- Merge Sorted Array
- Intersection of arrays
- strstr()

---

### 4. ✂️ Split & Merge

>The last one is similiar to previous category but there is one thing is added. First, you need to split the given list into 2 separate lists and then do two pointers approach to merge or unify them. There aren't many tasks here.

![[4-index.jpg]]

---
