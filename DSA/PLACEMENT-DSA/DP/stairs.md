AM

<table>
<colgroup>
<col style="width: 42%" />
<col style="width: 57%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/climbing-stairs/">70. Climbing Stairs</a></p>
<p></p>
<p>![image1](../../resources/018e92fe4f034c21ab03a0997a640c13.png)</p>
<p></p>
<table>
<colgroup>
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 15%" />
</colgroup>
<thead>
<tr class="header">
<th>X</th>
<th>1</th>
<th>2</th>
<th>3</th>
<th>5</th>
</tr>
</thead>
<tbody>
</tbody>
</table></th>
<th><p>![image2](../../resources/640edab871ca4f21b397a2217aa638fb.png)</p>
<p></p>
<p>![image3](../../resources/701213e48a4548129b4a2d573b332c6d.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/house-robber/submissions/">198. House Robber</a></p>
<p></p>
<p>if 1 house</p>
<p>if 2 house will rob max one</p>
<p></p>
<p>for any house : choice :</p>
<p>Rob : arr[i] + rob(till i-2)</p>
<p>not rob : rob(till i-1)</p>
<p>max(Rob,not rob)</p>
<p></p>
<table>
<colgroup>
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 15%" />
</colgroup>
<thead>
<tr class="header">
<th>7</th>
<th>2</th>
<th>9</th>
<th>3</th>
<th>1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>7</td>
<td>7</td>
<td>16</td>
<td>16</td>
<td>17</td>
</tr>
</tbody>
</table></td>
<td><p>![image4](../../resources/881f899ba83e4b8788594962c81d0698.png)</p>
<p>dp[i] = robbery till house i</p>
<p>![image5](../../resources/4ba20eb472ce41658b5d3c198784fd01.png)</p>
<p></p></td>
</tr>
</tbody>
</table>
