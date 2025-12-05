
<table>
<colgroup>
<col style="width: 41%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>Incresing decresing array pattern</strong></p>
<p></p>
<p><a href="https://leetcode.com/problems/maximum-ascending-subarray-sum/">1800. Maximum Ascending Subarray Sum</a></p>
<p></p>
<p>incresing only</p>
<p><strong>Input:</strong> nums = [10,20,30,5,10,50]<br />
<strong>Output:</strong> 65<br />
<strong>Explanation:</strong> [5,10,50] is the ascending subarray with the maximum sum of 65.</p>
<p></p>
<p>Always check for wrong case in if</p>
<p></p></th>
<th><p>![image1](../../resources/e6b260f399674b7a814a8ac3967587b5.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Intuition</strong>: <a href="https://leetcode.com/problems/longest-mountain-in-array/discuss/135593/C%2B%2BJavaPython-1-pass-and-O(1)-space">Link</a></p>
<p></p>
<p>We have already many 2-pass or 3-pass problems, like 821. Shortest Distance to a Character.</p>
<p>They have almost the same idea.</p>
<p>One forward pass and one backward pass.</p>
<p>Maybe another pass to get the final result, or you can merge it in one previous pass.</p>
<p></p>
<p><strong>Explanation</strong>:</p>
<p>In this problem, we take one forward pass to count up hill length (to every point).</p>
<p>We take another backward pass to count down hill length (from every point).</p>
<p>Finally a pass to find max(up[i] + down[i] + 1) where up[i] and down[i] should be positives.</p>
<p></p></td>
<td><p></p>
<p></p>
<p>Updated list of problems that involved 1 or 2 passes from left to right/right to left:</p>
<p></p>
<p>53 Maximum Subarray</p>
<p>121 Best Time to Buy and Sell Stock</p>
<p>152 Maximum Product Subarray</p>
<p>238 Product of Array Except Self</p>
<p>739 Daily Temperatures</p>
<p>769 Max Chunks to Make Sorted</p>
<p>770 Max Chunks to Make Sorted II</p>
<p>821 Shortest Distance to a Character</p>
<p>845 Longest Mountain in Array</p>
<p>581. Shortest Unsorted Continuous Subarray</p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/longest-mountain-in-array/">845. Longest Mountain in Array</a></p>
<p></p>
<ol type="1">
<li><p>inc + top + dec needed</p></li>
</ol>
<blockquote>
<p></p>
</blockquote>
<p>![image2](../../resources/95cf5e896c7a46608718e4aef73bb280.png)</p>
<p></p>
<p>corner case</p>
<p>[0,1,2,3,4,5,6,7,8,9] ans int_min</p>
<p>[0] if(n&lt;=2) return 0</p>
<p></p>
<p></p>
<p></p>
<p>![image3](../../resources/fb1035a91a324c8bac79749eb45d3647.png)</p>
<p></p></td>
<td><p></p>
<p>// approch with space sufix and prefix</p>
<p>![image4](../../resources/8f27f3c7efc8429fba496e1932d2af81.png)</p>
<p></p>
<p>with O(1) space</p>
<p>![image5](../../resources/da229330ba9d4ff78131607198430f64.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/find-good-days-to-rob-the-bank/">2100. Find Good Days to Rob the Bank</a></p>
<p></p>
<p>Prefix &amp; Suffix</p>
<p>find i index such that</p>
<p>2 ele to left should gre &amp;</p>
<p>2 ele to right should greater</p>
<p>![image6](../../resources/ecd4730dd7f34581bd7a820377b74984.png)</p>
<p></p>
<p>![image7](../../resources/79b714ebb1154b758afb043e932cdaa8.png)</p>
<p></p></td>
<td><p>![image8](../../resources/5a64dc1f8d57440ab2736e19a2e7a337.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>Hard :</p>
<p></p>
<p><a href="https://leetcode.com/problems/non-decreasing-array/">665. Non-decreasing Array</a></p>
<p></p>
<p>Given an arraynumswithnintegers, your task is to check if it could become non-decreasing by modifying<strong>at most one element</strong>.</p>
<p>We define an array is non-decreasing ifnums[i] &lt;= nums[i + 1]holds for everyi(<strong>0-based</strong>) such that (0 &lt;= i &lt;= n - 2).</p>
<p></p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> nums = [4,2,3]<br />
<strong>Output:</strong> true<br />
<strong>Explanation:</strong> You could modify the first 4 to 1 to get a non-decreasing array.</p>
<p><strong>Example 2:</strong></p>
<p><strong>Input:</strong> nums = [4,2,1]<br />
<strong>Output:</strong> false<br />
<strong>Explanation:</strong> You can't get a non-decreasing array by modify at most one element.</p>
<p></p>
<p>// [3,4,2,3]</p>
<p></p>
<p>![image9](../../resources/cd20eb33cd964b04a97bafa3210ef905.jpg)</p>
<p></p></td>
<td><p>![image10](../../resources/ff85aa95324b44598e89a3839240f5a6.png)</p>
<p></p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>when arr[i-1] &gt; arr[i]</p>
<p>then problem occer</p>
<p>.arr[i-1]</p>
<p>. arr[i]</p>
<p></p>
<p>2 ways to solve the problem</p>
<p></p>
<p>make arr[i-1] = arr[i]</p>
<p>or make arr[i] = arr[i-1]</p>
<p></p>
<p>Best thing we can do here is</p></td>
<td></td>
</tr>
</tbody>
</table>

