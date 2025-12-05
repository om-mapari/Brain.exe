

| Problem | Problem |
|----------|----------|
| [1. Two Sum](https://leetcode.com/problems/two-sum/)  ![image1](../../resources/4a959f9aceb54ae6b8d3e0728208d5c9.png) | [167. Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) ![image2](../../resources/2f7281c4b4e545faa93e9d705afeec95.png) |
| [15. 3Sum](https://leetcode.com/problems/3sum/)<br><br>Given an integer array `nums`, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.<br>Notice that the solution set must not contain duplicate triplets.<br><br>**Example 1:**<br>**Input:** nums = [-1,0,1,2,-1,-4]<br>**Output:** [[-1,-1,2],[-1,0,1]] | ![image3](../../resources/e39099fc96194293bcf808d17790364a.png) |
| [1679. Max Number of K-Sum Pairs](https://leetcode.com/problems/max-number-of-k-sum-pairs/)<br><br>**Input:** nums = [1,2,3,4], k = 5<br>**Output:** 2<br><br>Pairs: [1,4], [2,3] | ![image4](../../resources/f27f18e37e0a4753baa481819b6cd239.png) |
| **2 Pairs with Equal Sum**<br><br>To generate unique pairs:<br>`for i = 1 → n-1`<br>`for j = i+1 → n`<br><br>![image5](../../resources/641b5419a30a4f37a9f1db2d8203d3a0.png) | ![image6](../../resources/13f8c95925ff4c969fb295a7aa0af1a7.png) |
| [1497. Check If Array Pairs Are Divisible by k](https://leetcode.com/problems/check-if-array-pairs-are-divisible-by-k/)<br><br>We’re talking about **all pairs**.<br>Number of pairs must be `n / 2` (where `n` is even).<br><br>**Example 1:**<br>**Input:** arr = [1,2,3,4,5,10,6,7,8,9], k = 5<br>**Output:** true<br>**Explanation:** Pairs are (1,9), (2,8), (3,7), (4,6), (5,10).<br><br>**Example 2:**<br>**Input:** arr = [1,2,3,4,5,6], k = 7<br>**Output:** true<br>**Explanation:** Pairs are (1,6), (2,5), (3,4).<br><br>![image7](../../resources/37130469ed554edc8de8cfc94f937de5.png)<br><br>### Remainder Conditions
| rem | condition |
|-----|------------|
| freq(x) rem | equal to freq(k - x) |
| freq(0) rem | even |
| freq(k/2) rem | even | | ![image8](../../resources/a4b22aaf9fea41f78cbc3cd9ad0077c2.png) |
