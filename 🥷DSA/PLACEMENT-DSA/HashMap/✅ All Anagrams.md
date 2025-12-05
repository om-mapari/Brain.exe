
![image1](../../resources/4ba3c49492c74eddac2ea008559f22f2.png)

<table>
<colgroup>
<col style="width: 19%" />
<col style="width: 80%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/permutation-in-string/">567. Permutation in String</a></p>
<p></p>
<p><strong>Input:</strong> s1 = "ab", s2 = "eid<u>ba</u>ooo"<br />
<strong>Output:</strong> true</p>
<p><strong>Input:</strong> s1 = "ab", s2 = "eidboaoo"<br />
<strong>Output:</strong> false</p>
<p></p>
<p>"abc" "bbbca" true</p>
<p></p>
<p>SC = len(s1) only</p></th>
<th><p>![image2](../../resources/9589e381fe124d8682bca8ef85bf1ad1.png)</p>
<p></p>
<p>Optimization VV I.M.P</p>
<p></p>
<p>class Solution</p>
<p>{</p>
<p>public:</p>
<p><em>  // TC = O(n) SC = (len(s1))</em></p>
<p>  bool checkInclusion(string s1, string s2)</p>
<p>  {</p>
<p>    <em>if</em> (s1.size() &gt; s2.size())</p>
<p>      <em>return</em> false;</p>
<p>    vector&lt;int&gt; s1Count(26, 0), s2Count(26, 0);</p>
<p>    int k = s1.size(); <em>// WinSize</em></p>
<p>    int n = s2.size(); <em>// s2 size</em></p>
<p>    <em>for</em> (int i = 0; i &lt; k; i++) <em>// Add first Window</em></p>
<p>    {</p>
<p>      s1Count[s1[i] - 'a']++;</p>
<p>      s2Count[s2[i] - 'a']++;</p>
<p>    }</p>
<p>    int match = 0;</p>
<p>    <em>for</em> (int i = 0; i &lt; 26; i++)</p>
<p>      match += (s1Count[i] == s2Count[i] ? 1 : 0);</p>
<p></p>
<p><em>    // matches count = Equal values in both Vector</em></p>
<p>    <em>if</em> (match == 26)</p>
<p>      <em>return</em> true;</p>
<p>    <em>for</em> (int i = k; i &lt; n; i++)</p>
<p>    {</p>
<p><em>      // ADD CHAR</em></p>
<p>      int index = s2[i] - 'a';</p>
<p>      s2Count[index]++;</p>
<p>      <em>if</em> (s1Count[index] == s2Count[index]) <em>// we created new match which was originally mismatch</em></p>
<p>        match += 1;</p>
<p>      <em>else if</em> (s1Count[index] == s2Count[index] - 1) <em>// we created new mismatch which was from originally match</em></p>
<p>        match -= 1;</p>
<p></p>
<p><em>      // REMOVE CHAR</em></p>
<p>      index = s2[i - k] - 'a';</p>
<p>      s2Count[index]--;</p>
<p>      <em>if</em> (s1Count[index] == s2Count[index]) <em>// we created new match which was originally mismatch</em></p>
<p>        match += 1;</p>
<p>      <em>else if</em> (s1Count[index] == s2Count[index] + 1) <em>// we created new mismatch which was originally match</em></p>
<p>        match -= 1;</p>
<p>      <em>if</em> (match == 26)</p>
<p>        <em>return</em> true;</p>
<p>    }</p>
<p>    <em>return</em> false;</p>
<p>  }</p>
<p>};</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>

