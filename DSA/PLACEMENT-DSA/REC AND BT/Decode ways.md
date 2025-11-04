
<table>
<colgroup>
<col style="width: 67%" />
<col style="width: 32%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/decode-ways/https:/leetcode.com/problems/decode-ways/">91. Decode Ways</a></p>
<p></p>
<p>![image1](../../resources/9d4cfbbfc75c48ef928a9de53024ed4c.png)</p>
<p></p></th>
<th><p></p>
<p></p>
<p>class Solution {</p>
<p>public:</p>
<p>  vector&lt;int&gt; dp;</p>
<p>  int solve(string &amp;s,int i)</p>
<p>  {</p>
<p>    <em>if</em>(i &gt;= s.size()) <em>return</em> 1;</p>
<p>    <em>if</em>(s[i] == '0') <em>return</em> 0;</p>
<p>    <em>if</em>(dp[i] != -1) <em>return</em> dp[i];</p>
<p>    int l = 0, r = 0;</p>
<p>   </p>
<p>    l = solve(s,i+1);</p>
<p>   </p>
<p>    <em>if</em>(i+2 &lt;= s.size() &amp;&amp; stoi(s.substr(i,2)) &lt;= 26)</p>
<blockquote>
<p>r = solve(s,i+2);</p>
</blockquote>
<p>   </p>
<p>    <em>return</em> dp[i] = l + r;</p>
<p>   </p>
<p>  }</p>
<p>  int numDecodings(string s) {</p>
<p>    dp.resize(s.size() + 1, -1);</p>
<p>    <em>return</em> solve(s,0);</p>
<p>  }</p>
<p>};</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

