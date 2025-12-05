AM

<table>
<colgroup>
<col style="width: 53%" />
<col style="width: 46%" />
</colgroup>
<thead>
<tr class="header">
<th>stack</th>
<th>Heap</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>stack is used for static memory allocation</td>
<td>Heap is used for dynamic memory allocation</td>
</tr>
<tr class="even">
<td><p>When the fun A calls another fun B the fun A pause and wait till fun B exicute.</p>
<p>every time a function exits, all the variables transferred to the stack by that function are deleted</p></td>
<td></td>
</tr>
<tr class="odd">
<td>you do not have to <mark>manage</mark> the memory. Memory is allocated automatically</td>
<td>We have to take care memory allocation and deallocation</td>
</tr>
<tr class="even">
<td>object created in stack are not golabally accessable</td>
<td>Object stored in heap are golabally accessable</td>
</tr>
<tr class="odd">
<td><p>Stack contain refrence to the object created in heap</p>
<p>int *p = new int();</p></td>
<td></td>
</tr>
<tr class="even">
<td>When stack is full -&gt; StackOverFlowError</td>
<td>When heap is full -&gt; OutOfMemoryError</td>
</tr>
</tbody>
</table>

![image1](../../resources/05c34f44566f4e83a5aa2627dab427d4.png)

![image2](../../resources/0b27d94592bc4497a4d73370ab7d0dce.png)

