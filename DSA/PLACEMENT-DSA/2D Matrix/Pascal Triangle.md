
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><p><mark>Given R &amp; C</mark></p>
<p><mark>Element at R=5 &amp; C=3</mark></p>
<p>ans=6</p>
<p></p>
<p></p>
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Formulae = <sup>r-1</sup>C<sub>c-1</sub></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
<p></p>
<p></p>
<p></p>
<p></p></th>
<th>![image1](../../resources/3e767d559f4e4babbc4de8962dfb40d2.png)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><mark>Calculate nCr</mark></p>
<p><sup>10</sup>C<sub>3</sub> = 10*9*8</p>
<p>3*2*1</p>
<p></p>
<p></p>
<p></p></td>
<td><p>long long nCr(int n, int r)</p>
<p>{</p>
<blockquote>
<p>long long res = 1;</p>
<p>for (int i = 0; i &lt; r; i++) {</p>
<p>res = res * (n - i);</p>
<p>res = res / (i + 1);</p>
<p>}</p>
<p>return res;</p>
</blockquote>
<p>}<br />
</p></td>
</tr>
<tr class="even">
<td><p><mark>Print nth Row of Pacal Triangle</mark></p>
<p></p>
<p>n = 6</p>
<p></p>
<p>![image2](../../resources/2263223211074d4cad812a68256872dc.png)</p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p></td>
<td><p>vector&lt;int&gt; nthRow(int n)</p>
<p>{</p>
<blockquote>
<p>vector&lt;int&gt; ans;</p>
<p>int res = 1;</p>
<p>ans.push_back(res);</p>
</blockquote>
<p></p>
<blockquote>
<p>for (int i = 1; i &lt; n; i++) {</p>
<p>res = res * (n - i);</p>
<p>res = res / (i);</p>
<p>ans.push_back(res);</p>
<p>}</p>
</blockquote>
<p></p>
<blockquote>
<p>return ans;</p>
</blockquote>
<p>}<br />
</p></td>
</tr>
<tr class="odd">
<td><p><mark>Print Entire Pacal triangle</mark><br />
</p>
<p>vector&lt;vector&lt;int&gt;&gt; generate(int numRows) {</p>
<blockquote>
<p>vector&lt;vector&lt;int&gt;&gt; r(numRows);</p>
<p>for (int i = 0; i &lt; numRows; i++) {</p>
<p>r[i].resize(i + 1);</p>
<p>r[i][0] = r[i][i] = 1;</p>
</blockquote>
<p></p>
<blockquote>
<p>for (int j = 1; j &lt; i; j++)</p>
</blockquote>
<p>r[i][j] = r[i - 1][j - 1] + r[i - 1][j];</p>
<p>  </p>
<blockquote>
<p>}</p>
<p></p>
<p>return r;</p>
</blockquote>
<p>}</p>
<p></p></td>
<td><p></p>
<p>  vector&lt;int&gt; nthRow(int n)</p>
<p>  {</p>
<p>    vector&lt;int&gt; ans;</p>
<p>    int res = 1;</p>
<p>    ans.push_back(res);</p>
<p>    for (int i = 1; i &lt; n; i++) {</p>
<p>      res = res * (n - i);</p>
<p>      res = res / (i);</p>
<p>      ans.push_back(res);</p>
<p>    }</p>
<p>    return ans;</p>
<p>  }</p>
<p>  vector&lt;vector&lt;int&gt;&gt; generate(int n) {</p>
<p>    vector&lt;vector&lt;int&gt;&gt; ans;</p>
<p>    for(int i=1;i&lt;=n;i++){</p>
<p>      ans.push_back(nthRow(i));</p>
<p>    }</p>
<p>    return ans;</p>
<p>  }</p>
<p></p>
<p></p></td>
</tr>
</tbody>
</table>

