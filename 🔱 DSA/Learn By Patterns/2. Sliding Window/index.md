---
title: 2. Sliding Window
description: My Notes
tags:
    - dsa
created: 2026-05-18
updated: 2026-05-21
---
---

## 1️⃣ Fixed Size Sliding Window Template

📌 Use when **window size is constant (`k`)**
### Pattern template

- Build first window
- Slide by:
    - add new element
    - remove old element
    - update answer


> [!warning] Remember
>  No of windows = `n-k+1`


```cpp
// Step 1: Build first window of size k
for (int i = 0; i < k; i++) {
	add(arr[i]);
}

// Use first window
update_answer();

// Step 2: Slide window
for (int i = k; i < n; i++) {

	// Add new element
	add(arr[i]);

	// Remove old element
	remove(arr[i - k]);

	// Update answer
	update_answer();
}

```

Example: [max sum of subarray of size `k`](https://www.geeksforgeeks.org/problems/max-sum-subarray-of-size-k5313/1)

```cpp
int maxSubarraySum(vector<int>& arr, int k) {
    int n = arr.size();

    // Edge case: window size larger than array
    if (k > n) return -1;

    int windowSum = 0;

    // Step 1: Build first window of size k
    for (int i = 0; i < k; i++) {
        windowSum += arr[i];
    }

    // Initialize result using first window
    int maxResult = windowSum;

    // Step 2: Slide window
    for (int i = k; i < n; i++) {
        // add new element to window
        windowSum += arr[i];

        // remove old element
        windowSum -= arr[i - k];

        // Update answer
        maxResult = max(maxResult, windowSum);
    }

    return maxResult;
}

// TC - `O(n)` 
// SC - `O(1)` 

```

---

## 2️⃣ Variable Size Sliding Window Template

📌 Use when **window size is not fixed**  
You expand and shrink based on a condition.
### Pattern

- Expand window using `right`
- Add the new element in Window
- Keep checking condition
    - while invalid:
        - shrink from left to till it becomes valid
- update answer
- Repeat


> [!warning] Remember
>  `WinSize = right - left + 1`

```cpp
int left = 0;

for (int right = 0; right < n; right++) {

    // 1. Add new element in window
    add(arr[right]);

    // 2. Shrink from left while invalid
    while (invalid_window()) {
        remove(arr[left]);
        left++;
    }

    // 3. Use valid window
    update_answer();
}
```


Example: [Longest Substring Without Repeating Characters  ](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)

```cpp  
int lengthOfLongestSubstring(string s) {  
	int left = 0, maxLen = 0;  
	unordered_map<char, int> freq;  

	// Step 1: Expand window  
	for (int right = 0; right < s.size(); right++) {  
		char c = s[right];  
		freq[c]++;  

		// Step 2: Shrink while invalid  
		while (freq[c] > 1) {  
			freq[s[left]]--;  
			left++;  
		}  

		// Step 3: Update answer  
		maxLen = max(maxLen, right - left + 1);  
	}  

	return maxLen;  
}  

// TC - `O(n)`  
// SC - `O(k)` // k = unique chars  
```

---

0️⃣. BF

Useful calculations
- No of windows = n-k+1

BF approach
 1 2 3 4 5 6
 window size k=2

for( i= 0 --> i < n - (k - 1) )

    for( j= i --> j < i + k )

---
