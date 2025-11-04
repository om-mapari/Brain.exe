AM

<table>
<colgroup>
<col style="width: 42%" />
<col style="width: 57%" />
</colgroup>
<thead>
<tr class="header">
<th><ol type="1">
<li><p>Next Grater Element to right</p></li>
</ol>
<blockquote>
<p></p>
<p>[ pop ans push ] [ - a + ]</p>
<p></p>
<p>3 2 2 6 4 1 5 4</p>
<p>6 6 6 -1 5 5 -1 -1</p>
<p></p>
<p>![image1](../../resources/3dc684007b4748eaa2bf412d6c93c68b.png)</p>
<p></p>
<p></p>
<p>Trick :</p>
<p>if you want next greater to right then start from right and look right</p>
<p></p>
<p>if you want prev smaller to left then start looking from left and look left</p>
<p></p>
</blockquote></th>
<th><p></p>
<p>vector&lt;int&gt; nextGreaterElement(vector&lt;int&gt;&amp; arr) {</p>
<p>  int n = arr.size(); stack&lt;int&gt; st;</p>
<p>  vector&lt;int&gt; ans(n); <em>// using index</em></p>
<p>  <em>for</em> (int i = n - 1; i &gt;= 0; i--)</p>
<p>  {</p>
<p><em>    // using st.top()] &lt;= arr[i] bcoz we need strictly next greater</em></p>
<p>    <em>while</em> (!st.empty() &amp;&amp; arr[i] &gt;= arr[st.top()]) st.pop();</p>
<p>    ans[i] = st.empty() ? -1 : arr[st.top()];</p>
<p>    st.push(i); <em>// push index</em></p>
<p>  }</p>
<p>  <em>for</em> (auto i : ans) cout &lt;&lt; i &lt;&lt; " ";</p>
<p>  <em>return</em> ans;</p>
<p>}</p>
<p></p>
<p>Top is my so :</p>
<p>// if we need next greater then pop arr[i] &gt;= arr[st.top()] loop n -&gt; 0</p>
<p>// if we need next smaller then pop arr[i] &lt;= arr[st.top()] loop n -&gt; 0</p>
<p>// if we need prev greater then pop arr[i] &gt;= arr[st.top()] loop 0 -&gt; n</p>
<p>// if we need prev smaller then pop arr[i] &lt;= arr[st.top()] loop 0 -&gt; n</p>
<p></p>
<p>We can store val = arr[i] at start of while loop to reduce space</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/largest-rectangle-in-histogram/">84. Largest Rectangle in Histogram</a></p>
<p></p>
<p></p>
<p>![image2](../../resources/5adc13ca33b34a6baa821779fc7f23e6.png)</p>
<p></p>
<p></p></td>
<td>![image3](../../resources/a506b0a714ea41fc882ce163cfae2657.png)</td>
</tr>
<tr class="even">
<td><p></p>
<p>Stock Span =</p>
<p></p>
<p>span (ith day) = uptill which prev day prize is less</p>
<p></p>
<p>ans = 7</p>
<p></p>
<p>![image4](../../resources/e15f3c228bc047f9ae648aa8746b61bb.png)</p>
<p></p>
<p>span(ith day) = prev Max se pahele ke stocks</p>
<p></p></td>
<td><p></p>
<p>![image5](../../resources/001bc6830017444589c77cc23478aec0.png)</p>
<p></p>
<p></p></td>
</tr>
<tr class="odd">
<td><ol type="1">
<li><p>Alternate Approch :</p></li>
</ol>
<blockquote>
<p>Looking greater right &amp; starting from left</p>
<p>[ ( pop ans sath me ) push ]</p>
<p></p>
<p>![image6](../../resources/667e4f18f12f40aeb1169a1b57c86664.png)</p>
<p></p>
<p></p>
<p></p>
</blockquote></td>
<td><p>![image7](../../resources/6682c4250fac4e8e9d00e32f346cfe01.png)</p>
<p></p></td>
</tr>
</tbody>
</table>

