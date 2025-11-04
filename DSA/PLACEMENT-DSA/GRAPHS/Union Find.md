
Time complexity:
1.  For regular union and find, each operation takes O(logn) in average, and O(n) in worst case.
2.  For union by rank, it takes at most O(logn) time since the height of tree-like structure is restricted in O(logn).
3.  For path compression, the time complexity is reduced to O(1) in average and worst case, since the structure is flattened.
So the total time complexity can be reduced from O(n^2)(worst case), O(nlogn)(average case) to O(n) in both cases.

<table>
<colgroup>
<col style="width: 42%" />
<col style="width: 57%" />
</colgroup>
<thead>
<tr class="header">
<th><p>if two node belongs to same component ?</p>
<p>this ds will give ans</p>
<p></p>
<p></p></th>
<th><p>Union By Rank and Path Compression</p>
<ol type="1">
<li><p>Normal</p></li>
<li><p>Union by Rank</p></li>
<li><p>Path Compression</p></li>
</ol></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>There is tree and one edge just added. find that last edge added</p>
<p></p>
<p>![image1](../../resources/c584c8a781d04350be7049ad6d4ae81b.png)</p>
<p></p></td>
<td><p></p>
<p></p>
<p></p>
<p>![image2](../../resources/1a369336d2544f1e983e53808981d7cc.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>ON Matrix : find no of component</p>
<p></p>
<p>![image3](../../resources/93e24cab46bc46a389c6aa1c96d8fc14.png)</p>
<p></p></td>
<td><p></p>
<p>![image4](../../resources/bf4aa80eb1f24c28bf8cefa68d643721.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p></p>
<p></p>
<p></p></td>
</tr>
</tbody>
</table>

