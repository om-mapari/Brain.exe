
<table>
<colgroup>
<col style="width: 43%" />
<col style="width: 56%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/sliding-window-maximum/">239. Sliding Window Maximum</a></p>
<p></p>
<p></p>
<p></p>
<p>![image1](../../../resources/fdb7d427060e4dfa938b8d76cbefcc03.png)</p>
<p></p>
<ol type="1">
<li><p>triverse all window = (n-k+1)*k = find max</p></li>
<li><p>multiset = n*(2log(n))</p></li>
<li><p>deque = O(n)</p></li>
</ol>
<p></p>
<p>--------------------------------------------</p>
<p>// max should be at front : to acieve this</p>
<p>// for this maintain dq in dec order</p>
<p></p>
<p>to insert curr ele</p>
<ol type="1">
<li><p>pop front if its idx outside win &amp; also</p></li>
<li><p>pop from back dir : if ( back &lt; curr )</p></li>
<li><p>add curr</p></li>
</ol></th>
<th><p>![image2](../../../resources/9ee0cd9de5404ddbb0b438219e1e9a41.png)</p>
<p></p>
<p>![image3](../../../resources/fa7a29248099408c8eabdbf1e184b356.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sliding Window concept used here</p>
<p></p>
<p><a href="https://leetcode.com/problems/maximum-points-you-can-obtain-from-cards/">1423. Maximum Points You Can Obtain from Cards</a></p>
<p></p>
<p>![image4](../../../resources/6d42f7696daf4986b29096f7ddcf3f28.png)</p>
<p></p></td>
<td><p>Using Sliding Window</p>
<p></p>
<p>![image5](../../../resources/2659b1f1ae9243059eef6c0d751a5361.png)</p>
<p></p>
<p>operastions = arrSize - winSize with req sum</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/minimum-operations-to-reduce-x-to-zero/https:/leetcode.com/problems/minimum-operations-to-reduce-x-to-zero/">1658. Minimum Operations to Reduce X to Zero</a></p>
<p></p>
<p>![image6](../../../resources/4105ac37c99e49459b4842aa15b45f0e.png)</p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p></td>
<td><ol type="1">
<li><p>Using Prefix sum</p></li>
</ol>
<blockquote>
<p></p>
<p>![image7](../../../resources/a42e09b59f8942ffa51d96c84b120dad.png)</p>
<p></p>
</blockquote>
<ol start="2" type="1">
<li><p>Using Sliding Window</p></li>
</ol>
<blockquote>
<p></p>
<p>![image8](../../../resources/da5b6487a18a40f783f4379eea19ab64.png)</p>
</blockquote></td>
</tr>
</tbody>
</table>

