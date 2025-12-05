
<table>
<colgroup>
<col style="width: 49%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>combination</th>
<th>permutation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ways to place:</p>
<p>r items (similer) in n boxes</p>
<p>= nCr</p></td>
<td><p>Ways to place:</p>
<p>r item (distinct) n boxes</p>
<p>= nPr</p></td>
</tr>
<tr class="even">
<td><p>4C2</p>
<p></p>
<p>Placing 2 item in 4 boxes is similar to == selecting 2 boxes out of 4</p>
<p></p>
<p></p>
<p>![image1](../../../resources/1ec22afbb7ac42728dba11178e6ce1c2.png)</p>
<p></p>
<p>![image2](../../../resources/5a5b5221dbc54c269f14369f1dd169e7.png)</p>
<p></p>
<p>==============================================</p>
<p></p>
<p><em>#include</em> &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p><em>#include</em> &lt;bits/stdc++.h&gt;</p>
<p></p>
<p>void combination(string s, int curr_n, int curr_r, </p>
<p>int nboxes, int ritems)</p>
<p>{</p>
<p>  <em>if</em> (curr_n == nboxes) {</p>
<p>    <em>if</em> (curr_r == ritems) cout &lt;&lt; s &lt;&lt; endl;</p>
<p><em>// extra step in subset code</em></p>
<p>    <em>return</em>;</p>
<p>  }</p>
<p>  combination(s + 'i', curr_n + 1, curr_r + 1, nboxes, ritems);</p>
<p>  combination(s + '*', curr_n + 1, curr_r, nboxes, ritems);</p>
<p>}</p>
<p>int main()</p>
<p>{</p>
<p>  string s = "";</p>
<p>  int idx = 0;</p>
<p>  int nboxes = 4, ritems = 2;</p>
<p>  int curr_n = 0, curr_r = 0;</p>
<p>  combination(s, curr_n, curr_r, nboxes, ritems);</p>
<p>  <em>return</em> 0;</p>
<p>}</p>
<p></p>
<p>Ans :</p>
<p>ii**</p>
<p>i*i*</p>
<p>i**i</p>
<p>*ii*</p>
<p>*i*i</p>
<p>**ii</p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p>![image3](../../../resources/2ec0c12165f14aecb0c7c346fd80a2d0.png)</p>
<p></p></td>
<td><p>4P2 = selection + arrebgement</p>
<p></p>
<ol type="1">
<li><p>first boxes get selected</p></li>
<li><p>item get placed</p></li>
<li><p>item get permuted</p></li>
</ol>
<p></p>
<p>![image4](../../../resources/d69114a959fa4101b9e9534060b8f7e0.png)</p>
<p></p>
<p>![image5](../../../resources/4af7dad217a84b468e8e2965640a80f6.png)</p>
<p></p>
<p>==============================================</p>
<p></p>
<p><em>#include</em> &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p><em>#include</em> &lt;bits/stdc++.h&gt;</p>
<p></p>
<p>void permutation(string s, int curr_r, int r_item)</p>
<p>{</p>
<p>  <em>if</em> (curr_r &gt; r_item) {</p>
<p>    cout &lt;&lt; s &lt;&lt; endl;</p>
<p>    <em>return</em>;</p>
<p>  }</p>
<p>  <em>for</em> (int i = 0; i &lt; s.size(); i++)</p>
<p>  {</p>
<p>    <em>if</em> (s[i] == '*')</p>
<p>    {</p>
<p>      s[i] = '0' + curr_r;</p>
<p>      permutation(s, curr_r + 1, r_item);</p>
<p>      s[i] = '*';</p>
<p>    }</p>
<p>  }</p>
<p>}</p>
<p>int main()</p>
<p>{</p>
<p>  string s = "****"; <em>// nboxes = 4</em></p>
<p>  permutation(s, 1, 2);</p>
<p>  <em>return</em> 0;</p>
<p>}</p>
<p>Ans :</p>
<p>12**</p>
<p>1*2*</p>
<p>1**2</p>
<p>21**</p>
<p>*12*</p>
<p>*1*2</p>
<p>2*1*</p>
<p>*21*</p>
<p>**12</p>
<p>2**1</p>
<p>*2*1</p>
<p>**21</p>
<p></p>
<p>First level 4 option second level 3 option</p>
<p></p>
<p>n*(n-1)*(n-2) / (n-r)!</p>
<p></p>
<p>![image6](../../../resources/b588973d0ab74e1cbe9a404285c2339b.png)</p>
<p></p>
<p>The one we solve is perviously is that where we have to premute all items i.e =&gt; n!</p></td>
</tr>
</tbody>
</table>

