
<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 70%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Given a string arraywords, return<em>the maximum value of</em>length(word[i]) * length(word[j])<em>where the two words do not share common letters</em>. If no such two words exist, return0</p>
<p></p>
<p>Ex.</p>
<p>words = ["a","ab","d","cd"]</p>
<p>states = 1 3 8 12</p>
<p></p>
<p>states = ["a","ab","abc", "d", "ccd", "bcdd", "abcd"]</p>
<p>binery = 1 11 111 1000 1100 1110 1111</p>
<p>1 3 7 8 12 14 15</p>
<p></p>
<p>if( state[0] &amp; state[1] == val ) common char word</p>
<p>else don't have common char</p>
<p></p>
<p>1 3 7 8 12 14 15</p>
<p>a d</p>
<p>a ccd</p>
<p>a bcdd</p>
<p>ab d</p>
<p>ab ccd</p>
<p>abc d</p></th>
<th><p>![image1](../../resources/c7edf50eb80247fdb083aefe130f8668.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>

