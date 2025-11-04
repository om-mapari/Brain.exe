
<table>
<colgroup>
<col style="width: 54%" />
<col style="width: 45%" />
</colgroup>
<thead>
<tr class="header">
<th><p>![image1](../../resources/9607778b313e4e22a28d83c29e1219a0.png)</p>
<p></p>
<p></p>
<p>O(nlog(n))</p></th>
<th><p>class Solution {</p>
<p>public:</p>
<p><em>  // num   = 2 3 4 5 6 7 8 9 10</em></p>
<p><em>  // isprime = t t t t t t t t t</em></p>
<p><em>  // 2    = t  f  f  f</em></p>
<p><em>  // 3    = t t f  f   f</em></p>
<p><em>  // 4    = -</em></p>
<p><em>  // 5    = t t f t f  f f f</em></p>
<p><em>  // 6..7  = t t f t f t f f f</em></p>
<p>  int countPrimes(int n) {</p>
<p><em>    // intially all are prime</em></p>
<p>    vector&lt;bool&gt; isprime(n,true);</p>
<p>    int count = 0;</p>
<p>    <em>for</em> (int i = 2; i &lt; n; i++) {</p>
<p>      <em>if</em> (isprime[i] == true) {</p>
<p>        count++;</p>
<p>        <em>for</em> (int j = 2; i*j &lt; n; j++) {</p>
<p><em>     // mark all multiple if i to not prime</em></p>
<p>          isprime[i*j] = false;</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>    cout&lt;&lt;"Is 7 prime : "&lt;&lt;isprime[7]&lt;&lt;endl;</p>
<p>    <em>return</em> count;</p>
<p>  }</p>
<p>};</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

