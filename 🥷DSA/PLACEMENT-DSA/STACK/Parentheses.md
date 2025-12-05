AM

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><ol start="2" type="1">
<li><p>Duplicate Brackets</p></li>
</ol>
<blockquote>
<p></p>
<p>string is bal : just check if extra pair of bracket is present or not</p>
<p></p>
<p>![image1](../../resources/490b0ab7c17c4b7ea95d43fe4b9849ee.png)</p>
<p></p>
<p>![image2](../../resources/0c81f11b329344d8a1aa358b5c08c62d.png)</p>
</blockquote></th>
<th><p><em>for</em>(auto i: str)</p>
<p>{</p>
<p>  <em>if</em>(i == closing) {</p>
<p>    <em>if</em> top is opening : <em>return</em> true;</p>
<p>    <em>else</em> {</p>
<p>      remove all uptill opening</p>
<p>      &amp; remove closing</p>
<p>    }</p>
<p>  }</p>
<p>  <em>else</em> {</p>
<p>    st.push(i);</p>
<p>  }</p>
<p>  <em>return</em> false;</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ol start="3" type="1">
<li><p><a href="https://leetcode.com/problems/remove-outermost-parentheses/">Remove OuterMost parentheses - easy</a></p></li>
</ol>
<blockquote>
<p></p>
<p>// primitive decomposition concept when cnt == 0</p>
<p>// it means string of paren decomposed</p>
<p></p>
<p>![image3](../../resources/ee9e11874d804c7285eafc22bc0dfd44.png)</p>
<p></p>
</blockquote></td>
<td><p>![image4](../../resources/12cbccd6a62f4bbeb64e7ee14200b745.png)</p>
<p></p></td>
</tr>
</tbody>
</table>

D
