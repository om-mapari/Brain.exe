
<table>
<colgroup>
<col style="width: 55%" />
<col style="width: 44%" />
</colgroup>
<thead>
<tr class="header">
<th><ol type="1">
<li><p>days in month = 31</p></li>
</ol>
<blockquote>
<p></p>
<p>If first day is Tuesday</p>
<p>Find How many time each day occer</p>
<p></p>
<p></p>
<p></p>
</blockquote></th>
<th><p></p>
<p>as we know all days occer 4 time in 28 days</p>
<p></p>
<p>31-28=3</p>
<p>3 extra days</p>
<ul>
<li><p>29th day tuesday</p></li>
<li><p>30th day wednesday</p></li>
<li><p>31th day thursday</p></li>
</ul></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ol start="2" type="1">
<li><p>leap year</p></li>
</ol>
<blockquote>
<p>Normal year = 365 days</p>
<p>= 52 weeks + 1 extra day</p>
<p>365/7 = 52.1429</p>
<p>365mod7 = 1</p>
<p></p>
</blockquote></td>
<td><p></p>
<p>Leap year = 366 days</p>
<p>= 52 weeks + 2 extra day</p>
<p>366/7 = 52.2857</p>
<p>366mod7 = 2</p></td>
</tr>
<tr class="even">
<td><ol start="3" type="1">
<li><p>Check leap</p>
<ul>
<li><p>All Year % 4 are Leap Year</p></li>
<li><p>Except Century years ( means end with 00 )</p></li>
<li><p>Century years are leap year only if they are div by 400</p></li>
</ul></li>
</ol>
<blockquote>
<p></p>
</blockquote></td>
<td><p></p>
<p>If( year % 4 == 0 ) {</p>
<blockquote>
<p>// Century year</p>
<p>if ( year % 100 == 0 ) {</p>
<p>if( year % 400 ) leap year</p>
<p>else not leap year</p>
<p>}</p>
<p>else {</p>
<p>leap year</p>
<p>}</p>
</blockquote>
<p>}</p>
<p>else {</p>
<blockquote>
<p>not leap</p>
</blockquote>
<p>}</p>
<p></p></td>
</tr>
<tr class="odd">
<td><ol start="4" type="1">
<li><p></p></li>
</ol></td>
<td></td>
</tr>
</tbody>
</table>
