
//Merge2sortedarrayswithoutusingExtraspace.Solution

TimeComplexity SpaceComplexity
1.  Sort NewA -O(n+m)log(n+m) O(n+m) or O(1)
2.  Merge Alog NewA -O(n+m)O(n+m)or O(1) (space given)
3.  NoIdea -O(n+m)log(n+m) O(1)(GapMethodorShellShortIntuition)

<table>
<colgroup>
<col style="width: 45%" />
<col style="width: 54%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/merge-sorted-array/">88. Merge Sorted Array</a></p>
<p></p>
<p>nums1 = [1,2,3,0,0,0]</p>
<p>nums2 = [2,5,6]</p>
<p>nums1 = [1,2,2,3,5,6] =&gt; result</p></th>
<th><p>![image1](../../resources/e5f29752b0cb4e1c87f0a37b64dcc50c.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>![image2](../../resources/973779ce54e94cae994efdcdbd7e097b.png)</p>
<p></p>
<p></p>
<p></p>
<p><strong>Input:</strong> list1 = [1,2,4], list2 = [1,3,4]<br />
<strong>Output:</strong> [1,1,2,3,4,4]</p></td>
<td>![image3](../../resources/8c6abf869afb416cbae7b17e59867661.png)</td>
</tr>
<tr class="even">
<td><p>follow up</p>
<p><a href="https://leetcode.com/problems/merge-k-sorted-lists/">23. Merge k Sorted Lists</a></p></td>
<td><p>![image4](../../resources/7a61e7fb6dc34d8aa58be7fae737abcf.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>

