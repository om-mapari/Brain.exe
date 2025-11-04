AM

<table>
<colgroup>
<col style="width: 23%" />
<col style="width: 76%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/jump-game/">55. Jump Game</a></p>
<p></p>
<p>Input: nums = [2,3,1,1,4]</p>
<p>Output: true</p>
<p>Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.</p>
<p></p>
<p>Input: nums = [3,2,1,0,4]</p>
<p>Output: false</p>
<p>Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.</p></th>
<th><p>![image1](../../resources/9b7aec1b11964564b0e5711e60bed037.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/jump-game-ii/https:/leetcode.com/problems/jump-game-ii/">45. Jump Game II</a> <a href="https://youtu.be/A-Mc_0WsoaM">Video</a></p>
<p></p>
<p>from i==0 can reach to 2 which cnt as J1</p>
<p>so till 2 i will track my max reach for J2</p>
<p></p>
<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 17%" />
</colgroup>
<thead>
<tr class="header">
<th>2</th>
<th>3</th>
<th>1</th>
<th>1</th>
<th>4</th>
</tr>
</thead>
<tbody>
</tbody>
</table>
<p>|------J1------|----J2---|</p>
<p></p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> nums = [2,3,1,1,4]<br />
<strong>Output:</strong> 2<br />
<strong>Explanation:</strong> The minimum number of jumps to reach the last index is 2. Jump 1 step from index 0 to 1, then 3 steps to the last index.</p>
<p><strong>Example 2:</strong></p>
<p><strong>Input:</strong> nums = [2,3,0,1,4]<br />
<strong>Output:</strong> 2</p>
<p></p></td>
<td><p>![image2](../../resources/3fd99def6b7e4685b359692fe441e3b3.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/jump-game-iii/">1306. Jump Game III</a> Use DFS</p>
<p></p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> arr = [4,2,3,0,3,1,2], start = 5<br />
<strong>Output:</strong> true<br />
<strong>Explanation:</strong><br />
All possible ways to reach at index 3 with value 0 are:<br />
index 5 -&gt; index 4 -&gt; index 1 -&gt; index 3<br />
index 5 -&gt; index 6 -&gt; index 4 -&gt; index 1 -&gt; index 3</p>
<p></p>
<p><strong>Input:</strong> arr = [3,0,2,1,2], start = 2<br />
<strong>Output:</strong> false<br />
<strong>Explanation:</strong> There is no way to reach at index 1 with value 0.</p>
<p></p></td>
<td><p>![image3](../../resources/7923ff966c1e4030aa203137d17e7591.png)</p>
<p></p></td>
</tr>
</tbody>
</table>
