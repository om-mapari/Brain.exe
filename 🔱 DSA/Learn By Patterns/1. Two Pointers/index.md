---
title: 1. Two Pointers
description: My Notes
tags:
    - dsa
created: 2026-04-17
updated: 2026-05-19
---
---

## Tags

- ⭐ = solved in first try  
- 📍 = revisit 
- 🔥 = important  
- ⚠️ = solved but edge case missed 
- 👀 = solved but had to see little soluation first 
- 💀 = out of the box
- no tag = pending/not started

## 1. Pattern: Two Pointers

| Question                                                                                                                             | Tags  | Remember                                                                                                                                                                                            | My Soluation                    |
| ------------------------------------------------------------------------------------------------------------------------------------ | ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| 1. [Pair with Target Sum (easy)](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)                        | ⭐     | if only small char in string then we can use freq map                                                                                                                                               | [[1. Two Sum]]                  |
| 2. [Rearrange 0 and 1](https://www.geeksforgeeks.org/problems/segregate-0s-and-1s5106/1)                                             | ⭐     |                                                                                                                                                                                                     |                                 |
| 3. [Remove Duplicates (easy)](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)                                     | ⭐     |                                                                                                                                                                                                     |                                 |
| 4. [Squaring a Sorted Array (easy)](https://leetcode.com/problems/squares-of-a-sorted-array/)                                        | --    |                                                                                                                                                                                                     |                                 |
| 5. [Triplet Sum to Zero (medium)](https://leetcode.com/problems/3sum/)                                                               | ⚠️ 📍 | reperating number condition                                                                                                                                                                         | [[2. 3Sum 4Sum]]                |
| 6. [Triplet Sum Close to Target (medium)](https://leetcode.com/problems/3sum-closest/)                                               | ⭐     |                                                                                                                                                                                                     |                                 |
| 7. [Triplets with Smaller Sum (medium)](https://www.geeksforgeeks.org/problems/count-triplets-with-sum-smaller-than-x5549/1)         | ⭐     |                                                                                                                                                                                                     |                                 |
| 8. [Dutch National Flag Problem (medium)](https://leetcode.com/problems/sort-colors/description/)                                    | ⭐     | like merge sort..<br>mid for curr<br>000 mid 222<br><br>s should be stored with 0 <br>and e should be sorted with 2                                                                                 | [[4. Dutch National Flag Algo]] |
| 9. [Problem Challenge 1: Quadruple Sum to Target (medium)](https://leetcode.com/problems/4sum/)                                      |       | reperating number condition                                                                                                                                                                         | [[2. 3Sum 4Sum]]                |
| 10. [Problem Challenge 2: Comparing Strings containing Backspaces (medium)](https://leetcode.com/problems/backspace-string-compare/) | 📍    |                                                                                                                                                                                                     |                                 |
| 11. [Problem Challenge 3: Minimum Window Sort (medium)](https://leetcode.com/problems/shortest-unsorted-continuous-subarray/)        | 📍    | till s sorted<br>from e sorted<br>but edge case where the unsorted part might not be actually unsorted. so find max and min in that and then decrease our s and inc e to make up to the max and min |                                 |

## 2. Pattern: Fast & Slow pointers

| Question                                                                                                        | Tags | Remember                                                                    | My Soluation            |
| --------------------------------------------------------------------------------------------------------------- | ---- | --------------------------------------------------------------------------- | ----------------------- |
| 1. [LinkedList Cycle (easy)](https://leetcode.com/problems/linked-list-cycle/)                                  | ⭐    |                                                                             |                         |
| 2. [Start of LinkedList Cycle (medium)](https://leetcode.com/problems/linked-list-cycle-ii/)                    | 💀📍 | the maths behind it<br>2 (slow) = fast<br>2 (P + C - X) = P + C - X + C     | [[5. LinkedList Cycle]] |
| 3. [Happy Number (medium)](https://leetcode.com/problems/happy-number/)                                         | 💀📍 | you get to see same number again for sure<br>2 -> 4 -> 8 -> 16 -> .... -> 8 |                         |
| 4. [FIND DUPLICATE NUMBER](https://leetcode.com/problems/find-the-duplicate-number/description/)                | 💀📍 | Logic behind it:<br>Array values in range [1, n], so no element points to index 0. Index 0 is guaranteed to be outside the cycle, making it the perfect starting point to detect the duplicate (cycle entrance). | [[5. LinkedList Cycle]] |
| 5. [Middle of the LinkedList (easy)](https://leetcode.com/problems/middle-of-the-linked-list/)                  |      | Floyd Cycle Detection Alog                                                  |                         |
| 6. [Problem Challenge 1: Palindrome LinkedList (medium)](https://leetcode.com/problems/palindrome-linked-list/) |      |                                                                             |                         |
| 7. [Problem Challenge 2: Rearrange a LinkedList (medium)](https://leetcode.com/problems/reorder-list/)          |      |                                                                             |                         |
| 8. [Problem Challenge 3: Cycle in a Circular Array (hard)](https://leetcode.com/problems/circular-array-loop/)  |      |                                                                             |                         |

---
