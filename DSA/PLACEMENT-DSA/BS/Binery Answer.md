
**Identify :**

MINIMUM VALUE IS MAXIMIZE = MINIMUM && MAXIMUM IN SAME QUESION
then it is binery search question

Powerful Template :: [**Link**](https://leetcode.com/problems/first-bad-version/discuss/769685/Python-Clear-explanation-Powerful-Ultimate-Binary-Search-Template.-Solved-many-problems.)

![image1](../../resources/2c926665bc3b4f6baf4cfc0f33e0b3c9.png)

int binery_search(array)
{
  int s = 0, e = arr.size(),ans = -1,mid;
  while (s \<= e)
  {
    mid = s + (e - s) / 2;
    if (isValid(mid))
    {
      ans = mid;
      e = mid - 1;
    }
    else {
      s = mid + 1;
    }
  }
  return ans;
}

bool isValid() {
  conditions..
}

============================================================
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/first-bad-version/">278. First Bad Version</a></p>
<p></p>
<p>isBadVersion() -&gt; return version is bad or not</p>
<p></p>
<p>0 1 2 3 4 5</p>
<p>^ ^ ^ ^ ^ ^</p>
<p>F F F F T T</p>
<p></p>
<p>s m e</p>
<p></p>
<p>se = m</p>
<p>05 = 2</p>
<p>35 = 4</p>
<p>33 = 3</p>
<p></p>
<p></p></th>
<th><p>![image2](../../resources/2044c5fdaddd4448bd351ef7299d2269.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/peak-index-in-a-mountain-array/https:/leetcode.com/problems/peak-index-in-a-mountain-array/">852. Peak Index in a Mountain Array</a></p>
<p></p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> arr = [0,1,0]<br />
<strong>Output:</strong> 1</p>
<p><strong>Example 2:</strong></p>
<p><strong>Input:</strong> arr = [0,2,1,0]<br />
<strong>Output:</strong> 1</p>
<p><strong>Example 3:</strong></p>
<p><strong>Input:</strong> arr = [0,10,5,2]<br />
<strong>Output:</strong> 1</p></td>
<td><p>![image3](../../resources/e45a705fb2f14b6390cfa316ac0b3cbc.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/sqrtx/">69. Sqrt(x)</a></p>
<p></p>
<p>![image4](../../resources/cb88e593bfaf4fb19b666e3e703f5eb2.png)</p>
<p></p>
<p></p></td>
<td><p>![image5](../../resources/aa00597f05514c5ab23591d57b71eeff.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/search-insert-position/">35. Search Insert Position</a></p>
<p></p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> nums = [1,3,5,6], target = 5<br />
<strong>Output:</strong> 2</p>
<p><strong>Example 2:</strong></p>
<p><strong>Input:</strong> nums = [1,3,5,6], target = 2<br />
<strong>Output:</strong> 1</p>
<p><strong>Example 3:</strong></p>
<p><strong>Input:</strong> nums = [1,3,5,6], target = 7<br />
<strong>Output:</strong> 4</p>
<p></p></td>
<td><p>![image6](../../resources/ee3043314b6746ffa677d69306534dbe.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>Hard Question Template:</p>
<p></p>
<p><a href="https://leetcode.com/problems/split-array-largest-sum/">410. Split Array Largest Sum</a></p>
<p></p>
<p>In this type of Question</p>
<p></p>
<p>Given = arr , m</p>
<p>Aim = create m subarray (contiguous)</p>
<p>return sum = min(sum of all sub array)</p>
<p></p>
<p></p></td>
<td>TODO = <a href="https://leetcode.com/discuss/general-discussion/1302335/aggressive-cows-spoj-fully-explained-c">https://leetcode.com/discuss/general-discussion/1302335/aggressive-cows-spoj-fully-explained-c</a></td>
</tr>
<tr class="odd">
<td><p>Input:</p>
<p>N = 4</p>
<p>A[] = {12,34,67,90} = 90+34+67+12 = 203/2 =</p>
<p>M = 2</p>
<p>Output:113</p>
<p>Explanation:Allocation can be done in</p>
<p>following ways:</p>
<p>{12} and {34, 67, 90} Maximum Pages = 191</p>
<p>{12, 34} and {67, 90} Maximum Pages = 157</p>
<p>{12, 34, 67} and {90} Maximum Pages = 113</p>
<p></p>
<p>Therefore, the minimum</p>
<p>of these cases is 113, which is selected</p>
<p>as the output.</p>
<p></p>
<p>We have to minimize maximum no of pages allocated per studend</p>
<p>We have to distibute books such that load is almost equally distibuated</p>
<p>We have to distibute books such pages per student should be maximize</p></td>
<td><p>![image7](../../resources/a627a70727f74bcbb670d9af7cde61ea.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><blockquote>
<p><a href="https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/">1011. Capacity To Ship Packages Within D Days</a></p>
<p></p>
<p>Debug</p>
<p>1 55 28</p>
<p>Valid</p>
<p>1 27 14</p>
<p>15 27 21</p>
<p>Valid</p>
<p>15 20 17</p>
<p>Valid</p>
<p>15 16 15</p>
<p>Valid</p>
<p></p>
<p><a href="https://leetcode.com/problems/split-array-largest-sum/discuss/89819/C%2B%2B-Fast-Very-clear-explanation-Clean-Code-Solution-with-Greedy-Algorithm-and-Binary-Search">https://leetcode.com/problems/split-array-largest-sum/discuss/89819/C%2B%2B-Fast-Very-clear-explanation-Clean-Code-Solution-with-Greedy-Algorithm-and-Binary-Search</a></p>
<p></p>
<p><a href="https://leetcode.com/problems/koko-eating-bananas/">https://leetcode.com/problems/koko-eating-bananas/</a></p>
<p><a href="https://leetcode.com/problems/minimized-maximum-of-products-distributed-to-any-store/">https://leetcode.com/problems/minimized-maximum-of-products-distributed-to-any-store/</a></p>
<p></p>
</blockquote>
<ul>
<li><p><a href="https://leetcode.com/problems/split-array-largest-sum/">410. Split Array Largest Sum (Hard)</a></p></li>
<li><p><a href="https://leetcode.com/problems/kth-smallest-number-in-multiplication-table/">668. Kth Smallest Number in Multiplication Table (Hard)</a></p></li>
<li><p><a href="https://leetcode.com/problems/maximum-length-of-repeated-subarray/">718. Maximum Length of Repeated Subarray (Medium)</a></p></li>
<li><p><a href="https://leetcode.com/problems/find-k-th-smallest-pair-distance/">719. Find K-th Smallest Pair Distance (Hard)</a></p></li>
<li><p><a href="https://leetcode.com/problems/swim-in-rising-water/">778. Swim in Rising Water (Hard)</a></p></li>
<li><p><a href="https://leetcode.com/problems/longest-duplicate-substring/">1044. Longest Duplicate Substring (Hard)</a></p></li>
<li><p><a href="https://leetcode.com/problems/longest-repeating-substring/">1062. Longest Repeating Substring (Medium)</a></p></li>
<li><p><a href="https://leetcode.com/problems/find-the-smallest-divisor-given-a-threshold/">1283. Find the Smallest Divisor Given a Threshold (Medium)</a></p></li>
<li><p><a href="https://leetcode.com/problems/sum-of-mutated-array-closest-to-target/">1300. Sum of Mutated Array Closest to Target (Medium)</a></p></li>
<li><p><a href="https://leetcode.com/problems/minimum-number-of-days-to-make-m-bouquets/">1482. Minimum Number of Days to Make m Bouquets (Medium)</a></p></li>
<li><p><a href="https://leetcode.com/problems/sell-diminishing-valued-colored-balls/">1648. Sell Diminishing-Valued Colored Balls (Medium)</a></p></li>
<li><p><a href="https://leetcode.com/problems/maximum-value-at-a-given-index-in-a-bounded-array/">1802. Maximum Value at a Given Index in a Bounded Array (Medium)</a></p></li>
<li><p><a href="https://leetcode.com/problems/minimum-speed-to-arrive-on-time/">1870. Minimum Speed to Arrive on Time (Medium)</a></p></li>
</ul>
<blockquote>
<p></p>
<p></p>
<p><a href="https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/">https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/</a></p>
<p></p>
</blockquote></td>
<td><p></p>
<p></p></td>
</tr>
</tbody>
</table>
