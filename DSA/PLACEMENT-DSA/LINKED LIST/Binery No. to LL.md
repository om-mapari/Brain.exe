AM

Soluation :

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><ol type="1">
<li><p>Reverse the ll</p></li>
</ol></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ol start="2" type="1">
<li><p>Find Length of ll</p></li>
</ol>
<blockquote>
<p>first node = val * (2&lt;&lt;(len-1))</p>
<p>![image1](../../resources/ece75ee934234ed489fe2cfa8cb3e923.png)</p>
<p></p>
</blockquote></td>
<td><p>![image2](../../resources/0c2f316576fe48d6aa0d95f6a279d014.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><ol start="3" type="1">
<li><p>consider first node head as the last node As last node</p></li>
</ol>
<blockquote>
<p>value = 2^0 * val</p>
<p></p>
<p>So when we move next we see that our assumtion was wrong</p>
<p>So we multiply prev one by 2 as it becomes 2nd last and consider curr as last node so add 2^0 * val and add both of them</p>
<p></p>
<p>![image3](../../resources/e089bcc4774340189075ad5550d7d047.png)</p>
</blockquote></td>
<td><p>![image4](../../resources/1d40909248e24422b856b3d84f67ca80.png)</p>
<p></p></td>
</tr>
</tbody>
</table>

