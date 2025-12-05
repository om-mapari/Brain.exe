
Types :
1.  [All](onenote:#Type%20II%20%20a%20Basic&section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&page-id={A4CC7B82-FC48-4B7E-8C49-64D8302D083A}&object-id={25DD83EB-B632-4E84-B4C7-9974318EF2EC}&14&base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one) = get All Valid subArr
2.  [AtMost](onenote:#Type%20II%20%20a%20Basic&section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&page-id={A4CC7B82-FC48-4B7E-8C49-64D8302D083A}&object-id={E4A57C57-164B-487C-83BF-AC90F0F58677}&CF&base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one) = get Atmost k Valid
3.  [Exactly](onenote:#Type%20II%20%20a%20Basic&section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&page-id={A4CC7B82-FC48-4B7E-8C49-64D8302D083A}&object-id={98A5B1E9-5A4F-4936-B7AF-CA99E0637487}&86&base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one) = Atmost(k) - Atmost(k-1)

<table>
<colgroup>
<col style="width: 52%" />
<col style="width: 47%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Repeatation Not Allowed</strong></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ol type="1">
<li><p>count substr without rep char</p></li>
</ol>
<blockquote>
<p></p>
</blockquote>
<table>
<colgroup>
<col style="width: 58%" />
<col style="width: 41%" />
</colgroup>
<thead>
<tr class="header">
<th>a valid</th>
<th>ans=a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>aa invalid -&gt; a</td>
<td>ans=a</td>
</tr>
<tr class="even">
<td>ab valid</td>
<td>ans=ab b</td>
</tr>
<tr class="odd">
<td>abc valid</td>
<td>ans=abc bc c</td>
</tr>
<tr class="even">
<td>abcb invalid -&gt; cb</td>
<td>ans=cb b</td>
</tr>
</tbody>
</table>
<blockquote>
<p></p>
<p></p>
<p>a</p>
<p>a</p>
<p>ab</p>
<p>abc</p>
<p>cb</p>
<p>count = 9</p>
<p></p>
<p>![image1](../../../resources/c210401f7e1d4e5bada54fe0d875b74e.png)</p>
</blockquote></td>
<td><p><em>#include</em> &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p><em>#include</em> &lt;bits/stdc++.h&gt;</p>
<p></p>
<p>void cntWithoutRep(string &amp;s)</p>
<p>{</p>
<p>  int n = s.size(), cnt = 0;</p>
<p>  unordered_map&lt;int, int&gt; freq;</p>
<p>  int j = 0;</p>
<p>  <em>for</em> (int i = 0; i &lt; n; i++)</p>
<p>  {</p>
<p>    char ch = s[i];</p>
<p>    freq[ch]++;</p>
<p><em>    // lets make valid</em></p>
<p>    <em>while</em> (freq[ch] &gt; 1)</p>
<p>    {</p>
<p>      <em>if</em> (freq[s[j]] == 1) freq.erase(s[j]);</p>
<p>      <em>else</em> freq[s[j]]--;</p>
<p>      j++;</p>
<p>    }</p>
<p>    cnt += (i - j + 1);</p>
<p>    cout &lt;&lt; s.substr(j, i - j + 1) &lt;&lt; endl;</p>
<p>  }</p>
<p>  cout &lt;&lt; "count = " &lt;&lt; cnt &lt;&lt; endl;</p>
<p>}</p>
<p>int main()</p>
<p>{</p>
<p>  string s = "aabcb";</p>
<p>  cntWithoutRep(s);</p>
<p>  <em>return</em> 0;</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><ol start="2" type="1">
<li><p>Longest subStr without rep char</p></li>
</ol>
<blockquote>
<p>aabcb ans = 3;</p>
<p></p>
</blockquote>
<table>
<colgroup>
<col style="width: 80%" />
<col style="width: 19%" />
</colgroup>
<thead>
<tr class="header">
<th>add - while</th>
<th>len</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>a valid</td>
<td>1</td>
</tr>
<tr class="even">
<td>aa invalid -&gt; a</td>
<td>2</td>
</tr>
<tr class="odd">
<td>ab valid</td>
<td>2</td>
</tr>
<tr class="even">
<td>abc valid</td>
<td>3</td>
</tr>
<tr class="odd">
<td>abcb invalid -&gt; cb</td>
<td>2</td>
</tr>
</tbody>
</table>
<blockquote>
<p></p>
</blockquote></td>
<td>![image2](../../../resources/760df032cf504f91ab262e39280eef98.png)</td>
</tr>
<tr class="odd">
<td><p></p>
<p><strong>Repeatation Allowed</strong></p></td>
<td></td>
</tr>
<tr class="even">
<td><ol type="1">
<li><p>count subStr at most k distinct char</p></li>
</ol>
<blockquote>
<p></p>
<p>"aabcb" ans = 11 k = 3</p>
<p>0k 1k 2k 3k allowed 4k not allowed</p>
<p></p>
</blockquote>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th>a valid</th>
<th>ans = a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>aa valid</td>
<td>ans = aa a</td>
</tr>
<tr class="even">
<td>aab valid</td>
<td>ans = aab ab b</td>
</tr>
<tr class="odd">
<td>aabc invalid bc</td>
<td>ans = bc c</td>
</tr>
<tr class="even">
<td>bcb valid</td>
<td>ans = bcb cb b</td>
</tr>
</tbody>
</table>
<blockquote>
<p></p>
<p>a</p>
<p>aa</p>
<p>aab</p>
<p>bc</p>
<p>bcb</p>
<p>count = 11</p>
<p></p>
<p>![image3](../../../resources/0d407424cbca4ce08a41322c06118855.png)</p>
<p></p>
</blockquote></td>
<td><p><em>#include</em> &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p><em>#include</em> &lt;bits/stdc++.h&gt;</p>
<p>void atMostK(string &amp;s, int k)</p>
<p>{</p>
<p>  int n = s.size(), cnt = 0;</p>
<p>  unordered_map&lt;int, int&gt; freq;</p>
<p>  int j = 0;</p>
<p>  <em>for</em> (int i = 0; i &lt; n; i++)</p>
<p>  {</p>
<p>    char ch = s[i];</p>
<p>    freq[ch]++;</p>
<p><em>    // lets make valid</em></p>
<p>    <em>while</em> (freq.size() &gt; k)</p>
<p>    {</p>
<p>      <em>if</em> (freq[s[j]] == 1) freq.erase(s[j]);</p>
<p>      <em>else</em> freq[s[j]]--;</p>
<p>      j++;</p>
<p>    }</p>
<p>    cnt += (i - j + 1);</p>
<p>    cout &lt;&lt; s.substr(j, i - j + 1) &lt;&lt; endl;</p>
<p>  }</p>
<p>  cout &lt;&lt; "count = " &lt;&lt; cnt &lt;&lt; endl;</p>
<p>}</p>
<p>int main()</p>
<p>{</p>
<p>  string s = "aabcb";</p>
<p>  atMostK(s, 2);</p>
<p>  <em>return</em> 0;</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><ol start="2" type="1">
<li><p>longest subStr at most k distinct c</p></li>
</ol>
<blockquote>
<p></p>
<p>"aabcb" ans = 3</p>
<p></p>
<p></p>
</blockquote>
<table>
<colgroup>
<col style="width: 47%" />
<col style="width: 52%" />
</colgroup>
<thead>
<tr class="header">
<th>a valid</th>
<th>len = 1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>aa valid</td>
<td>ans = aa a</td>
</tr>
<tr class="even">
<td>aab valid</td>
<td>ans = aab ab b</td>
</tr>
<tr class="odd">
<td>aabc invalid bc</td>
<td>ans = bc c</td>
</tr>
<tr class="even">
<td>bcb valid</td>
<td>ans = bcb cb b</td>
</tr>
</tbody>
</table></td>
<td><p>int lengthOfLongestSubstringAtMostKDistinct(string &amp;s, int k) {</p>
<p>  int n = s.size(),maxLen = 0;</p>
<p>  unordered_map&lt;int,int&gt; um;</p>
<p>  int j =0;</p>
<p>  <em>for</em>(int i=0;i&lt;n;i++)</p>
<p>  {</p>
<p>    um[s[i]]++;</p>
<p>    <em>while</em>(um.size()&gt;k){</p>
<p>      <em>if</em>(um[s[j]]==1) um.erase(s[j]);</p>
<p>      <em>else</em> um[s[j]]--;</p>
<p>      j++;</p>
<p>    }</p>
<p>    maxLen = max(maxLen,i-j+1);</p>
<p>  }</p>
<p>  <em>return</em> maxLen;</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p></p>
<p></p></td>
<td></td>
</tr>
<tr class="odd">
<td><ol type="1">
<li><p>Count subStr with Exactly k distinct char</p></li>
</ol>
<blockquote>
<p>At most k distinct with k = 3</p>
<p>0k 1k 2k 3k - 0k 1k 2k = 3k</p>
<p>atmost(k) - atmost(k-1) = exactly</p>
<p></p>
<p></p>
<p>![image4](../../../resources/ae9cc2a077fd46a7bbdc829e52090fb0.png)</p>
<p></p>
<p>other problems</p>
<p></p>
<p><a href="onenote:#Type%20II%20%20a%20Hard&amp;section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&amp;page-id={354B819C-4CFB-4CAC-ADE9-E3E5768F2F47}&amp;object-id={FCE3C327-20D2-40F7-A0CD-17C26A10022C}&amp;10&amp;base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one">Sliding Window + "At Most to Equal" trick To</a></p>
</blockquote></td>
<td><p><em>#include</em> &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p><em>#include</em> &lt;bits/stdc++.h&gt;</p>
<p><em>// the number of subarrays with at most K distinct elements</em></p>
<p>int most_k_chars(string &amp;s, int k) {</p>
<p>  int n = s.size(), anss = 0;</p>
<p>  unordered_map&lt;char, int&gt; um;</p>
<p>  int j = 0;</p>
<p>  <em>for</em> (int i = 0; i &lt; n; i++) {</p>
<p>    um[s[i]]++;</p>
<p> </p>
<p>    <em>while</em> (um.size() &gt; k) {</p>
<p>      <em>if</em>(um[s[j]]==1) um.erase(s[j]);</p>
<p>      <em>else</em> um[s[j]]--;</p>
<p>      j++;</p>
<p>    }</p>
<p>    anss += i - j + 1;</p>
<p>  }</p>
<p>  <em>return</em> anss;</p>
<p>}</p>
<p>int exact_k_chars(string &amp;s, int k) {</p>
<p>  <em>return</em> most_k_chars(s, k) - most_k_chars(s, k - 1);</p>
<p>}</p>
<p>int main() {</p>
<p>  string s1 = "pqpqs";</p>
<p>  cout &lt;&lt; "Answer should be 7: "</p>
<p>&lt;&lt; exact_k_chars(s1, 2) &lt;&lt; endl;</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><ol start="2" type="1">
<li><p>longest SubStr exactly k distinct char</p></li>
</ol>
<blockquote>
<p></p>
<p>Minor change in code</p>
<p></p>
</blockquote></td>
<td>![image5](../../../resources/7b5ba8ffabe645c8a68fa4de8fa0df79.png)</td>
</tr>
</tbody>
</table>

