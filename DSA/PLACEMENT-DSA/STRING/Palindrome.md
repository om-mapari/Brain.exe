
<table>
<colgroup>
<col style="width: 49%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/valid-palindrome/">125. Valid Palindrome</a></p>
<p>char and num allowed : rest ignore</p>
<p></p>
<p>![image1](../../resources/55111d509ae648f8b043c5742264aa00.png)</p>
<p></p></th>
<th>![image2](../../resources/67a61101d3e645fda856f7b4176a6fdb.png)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/valid-palindrome-ii/">680. Valid Palindrome II</a></p>
<p></p>
<p>Can Remove one char:</p>
<p></p>
<p>![image3](../../resources/67f50fbce87c4f4a85dbbfd2f58ddf22.png)</p>
<p></p>
<p>if d = skiped ae is not pal</p>
<p>if e = skiped de is not pal</p>
<p></p>
<p>return false</p>
<p></p>
<p>"abca" allowed</p>
<p></p></td>
<td><p>![image4](../../resources/cc76d8296b8c461dbd7c466afe5be39f.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/remove-palindromic-subsequences/">1332. Remove Palindromic Subsequences</a></p>
<p></p>
<p>Aim = make string empty</p>
<p>: Can Remove pal only -&gt; count as one operation</p>
<p></p>
<p>In a single step you can remove one palindromic subsequence from s.</p>
<p></p>
<p>so there can be only three ans</p>
<p>0 - empty</p>
<p>1 - if pal : abcba direct remove</p>
<p>2 - not pal to make pal - expalnation : substring</p>
<p></p>
<p>![image5](../../resources/61b0382a7fb742e6972f2cc4f3e0a8da.png)</p></td>
<td><p>![image6](../../resources/97ac0619021347d987d34a9cb7a3edbc.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td>Can pal substring possible</td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/palindromic-substrings/">647. Palindromic Substrings</a></p>
<p></p>
<ol type="1">
<li><p>BF : O(N^3)</p></li>
<li><p>OT : O(N^2) with odd &amp; even substring seprate</p></li>
</ol>
<p></p>
<p>![image7](../../resources/c37774330b7f46499a447bf4006ef4ef.png)</p>
<p></p>
<p></p>
<p></p></td>
<td><p>![image8](../../resources/5e9d206ff8bc40d2a661886d47d6e0a6.png)</p>
<p></p>
<p>![image9](../../resources/7a8ac63a0d4b445d8e9660d5578b5b83.png)</p>
<p>can make more readable by : DRY</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/longest-palindromic-substring/">5. Longest Palindromic Substring</a></p>
<p></p>
<p>![image10](../../resources/97dab93191e3478382fb12ca7833bb1c.png)</p>
<p>![image10](../../resources/97dab93191e3478382fb12ca7833bb1c.png)</p>
<p></p></td>
<td></td>
</tr>
</tbody>
</table>

