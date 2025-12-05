
<table>
<colgroup>
<col style="width: 42%" />
<col style="width: 57%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/minimum-size-subarray-sum/">209. Minimum Size Subarray Sum</a></p>
<p></p>
<p><strong>While reducing window there is possiblity of answer</strong></p>
<p></p>
<p>While(Valid) // make it invalid</p>
<p>{</p>
<blockquote>
<p>update ans;</p>
<p>decrease window;</p>
</blockquote>
<p>}</p>
<p></p>
<p>// dosen't works for -ve integer <a href="onenote:#Type%20II%20%20b%20Invalid&amp;section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&amp;page-id={89A235C9-683A-4A97-BA88-E5B749C59FD0}&amp;object-id={688FFE5F-AB03-45AD-925C-C75E58563479}&amp;3E&amp;base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one">Link</a></p>
<p>// coz while(sum&gt;=t) when j-- then there is possiblity</p>
<p>// [84,-37,32,40,95] t = 167</p></th>
<th><p>![image1](../../../resources/7c1a9c382b434c3990bb786716d6864c.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/number-of-substrings-containing-all-three-characters/">1358. Number of Substrings Containing All Three Characters</a></p>
<p></p>
<ol type="1">
<li><p>always aquire value</p></li>
<li><p>release untill become invalid</p></li>
</ol>
<blockquote>
<p>: while(valid) count ans : untill = invalid</p>
</blockquote>
<p></p>
<p>char = abc find no of substr contain all three</p>
<p></p>
<p>![image2](../../../resources/c20d02b17be44fe6a5f6111b2a1ec81f.png)</p></td>
<td><p></p>
<p></p>
<p></p>
<p>![image3](../../../resources/6adaedfd30124e0eb8db29488640d0be.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/minimum-window-substring/">76. Minimum Window Substring</a></p>
<p>Hard to make it in O(m+n)</p>
<p></p>
<p>aim = find min substr such that all char in t must be in s including dublicate</p>
<p></p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> s = "ADOBECODEBANC", t = "ABC"<br />
<strong>Output:</strong> "BANC"<br />
<strong>Explanation:</strong> The minimum window substring "BANC" includes 'A', 'B', and 'C' from string t.</p>
<p><strong>Example 2:</strong></p>
<p><strong>Input:</strong> s = "a", t = "a"<br />
<strong>Output:</strong> "a"<br />
<strong>Explanation:</strong> The entire string s is the minimum window.</p>
<p><strong>Example 3:</strong></p>
<p><strong>Input:</strong> s = "a", t = "aa"<br />
<strong>Output:</strong> ""<br />
<strong>Explanation:</strong> Both 'a's from t must be included in the window.<br />
Since the largest window of s only has one 'a', return empty string.</p>
<p></p>
<table>
<colgroup>
<col style="width: 39%" />
<col style="width: 60%" />
</colgroup>
<thead>
<tr class="header">
<th>win increase</th>
<th>win decrease</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ADOBEC valid</td>
<td><p>ADOBEC ans = min(6,INT_MAX)</p>
<p>DOBEC invalid</p></td>
</tr>
<tr class="even">
<td>DOBECODEBA valid</td>
<td><p>DOBECODEBA ans = min(6,10)</p>
<p>OBECODEBA ans = 6</p>
<p>BECODEBA --</p>
<p>ECODEBA --</p>
<p>CODEBA ans = 6</p>
<p>ODEBA invalid</p></td>
</tr>
<tr class="odd">
<td>ODEBANC</td>
<td><p>ODEBANC ans = 6</p>
<p>DEBANC --</p>
<p>EBANC ans = 5</p>
<p>BANC ans = 4</p>
<p>ANC invalid</p></td>
</tr>
</tbody>
</table>
<p></p></td>
<td>![image4](../../../resources/8ccbdfec12094ec5a35f3b414cf6511c.png)</td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/">862. Shortest Subarray with Sum at Least K</a></p>
<p></p>
<p>"What makes this problem hard is that we have negative values.</p>
<p>If you haven't already done the problem with positive integers only,</p>
<p>I highly recommend solving it first"</p>
<p><a href="onenote:#Type%20II%20%20b&amp;section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&amp;page-id={89A235C9-683A-4A97-BA88-E5B749C59FD0}&amp;object-id={688FFE5F-AB03-45AD-925C-C75E58563479}&amp;19&amp;base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one">Minimum Size Subarray Sum</a></p>
<p></p></td>
<td></td>
</tr>
</tbody>
</table>

