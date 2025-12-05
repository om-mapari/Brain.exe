✅== 2 choice ==✅

abc =\> subset = powerset = sub sequence
= { a, b, c, ab, ac , bc , abc , \$}
= \[\[1,2,3\],\[1,2\],\[1,3\],\[1\],\[2,3\],\[2\],\[3\],\[\]\]

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><ul>
<li><p>subset is</p></li>
</ul></th>
<th><ul>
<li><p>same as sub-sequence but</p></li>
</ul></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>order not matter</td>
<td>order matter</td>
</tr>
<tr class="even">
<td><p>ex. ca is also subset</p>
<p>which is equivalent to ac</p></td>
<td>ex. ca is not sub-sequence ac is</td>
</tr>
</tbody>
</table>

- sub-string
sub string = a b c ab bc abc = for for loop //
sub-string ⊆ sub-sequence

========================================================

TC = for every index we have 2 option 0(2^n)
SC = stack space 0(n)

there are N numbers and 2 decision ( whether to include or leave a number )

Example:
\[1,2,3\]
\[1(include/leave), 2(include/leave), 3(include/leave)\] = 2\*2\*2 = 2^3
so 2^n
