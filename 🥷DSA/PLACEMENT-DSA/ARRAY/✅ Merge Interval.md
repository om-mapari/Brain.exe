
<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 65%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/merge-intervals/">56. Merge Intervals</a></p>
<p></p>
<p></p>
<p><strong>Input:</strong> intervals = [[1,3],[2,6],[8,10],[15,18]]<br />
<strong>Output:</strong> [[1,6],[8,10],[15,18]]<br />
<strong>Explanation:</strong> Since intervals [1,3] and [2,6] overlap, merge them into [1,6].</p>
<p></p>
<p></p>
<p>class Solution {</p>
<p>public:</p>
<p>  vector&lt;vector&lt;int&gt;&gt; merge(vector&lt;vector&lt;int&gt;&gt;&amp; arr) {</p>
<p>    sort(arr.begin(),arr.end());</p>
<p>    vector&lt;vector&lt;int&gt;&gt; ans;</p>
<p>    ans.push_back(arr[0]);</p>
<p>    int n = arr.size();</p>
<p>    for(int i=1;i&lt;n;i++)</p>
<p>    {</p>
<p>      auto curr = arr[i];</p>
<p>      int e = ans.size()-1;</p>
<p>      if(curr[0]&lt;=ans[e][1])</p>
<p>      {</p>
<p>        ans[e] = { min(ans[e][0],curr[0]),</p>
<blockquote>
<p>max(ans[e][1], curr[1]) };</p>
</blockquote>
<p>      }</p>
<p>      else ans.push_back(curr);</p>
<p>    }</p>
<p>    return ans;</p>
<p>  }</p>
<p>};</p>
<p>// curr  0-----</p>
<p>// prev----1</p>
<p></p>
<p></p></th>
<th><p>![image1](../../resources/8f1073e95bd046969c52ca8e8938d85f.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/insert-interval/">57. Insert Interval</a></p>
<p></p>
<p></p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> intervals = [[1,3],[6,9]], newInterval = [2,5]<br />
<strong>Output:</strong> [[1,5],[6,9]]</p>
<p></p>
<p><strong>Example 2:</strong></p>
<p><strong>Input:</strong> intervals = [[1,2],[3,5],[6,7],[8,10],[12,16]], newInterval = [4,8]<br />
<strong>Output:</strong> [[1,2],[3,10],[12,16]]<br />
<strong>Explanation:</strong> Because the new interval [4,8] overlaps with [3,5],[6,7],[8,10].</p>
<p></p></td>
<td><p>aclass Solution {</p>
<p>public:</p>
<p>  void insersion(vector&lt;vector&lt;int&gt;&gt; &amp;arr)</p>
<p>  {</p>
<p>    int n = arr.size();</p>
<p>    for(int i = n-1; i&gt;=1 ;i--)</p>
<p>    {</p>
<p>      if(arr[i][0] &lt; arr[i-1][0]) swap(arr[i],arr[i-1]);</p>
<p>      else break;</p>
<p>    }</p>
<p>  }</p>
<p>  vector&lt;vector&lt;int&gt;&gt; insert(vector&lt;vector&lt;int&gt;&gt;&amp; arr, vector&lt;int&gt;&amp; add) {</p>
<p>    arr.push_back(add);</p>
<p>    insersion(arr);</p>
<p>    vector&lt;vector&lt;int&gt;&gt; ans;</p>
<p>    ans.push_back(arr[0]);</p>
<p>    for(int i=1;i&lt; arr.size();i++){</p>
<p>      int e = ans.size()-1;</p>
<p>      if(arr[i][0] &lt;= ans[e][1])</p>
<p>      {</p>
<p>        ans[e] = {min(ans[e][0],arr[i][0]) , max(ans[e][1],arr[i][1])};</p>
<p>      } else ans.push_back(arr[i]);</p>
<p>    }</p>
<p>    return ans;</p>
<p>  }</p>
<p>};</p>
<p>// arr     0------1</p>
<p>// ans   0-----1</p>
<p></p>
<p></p></td>
</tr>
<tr class="even">
<td><p>Please see and vote for my solutions for similar problems.</p>
<p><a href="https://leetcode.com/problems/meeting-rooms-ii/discuss/322622/Simple-Python-solutions">253. Meeting Rooms II</a></p>
<p><a href="https://leetcode.com/problems/my-calendar-ii/discuss/323479/Simple-C%2B%2B-Solution-using-built-in-map-(Same-as-253.-Meeting-Rooms-II)">731. My Calendar II</a></p>
<p><a href="https://leetcode.com/problems/my-calendar-iii/discuss/302492/Simple-C%2B%2B-Solution-using-built-in-map-(Same-as-253.-Meeting-Rooms-II)">732. My Calendar III</a></p>
<p><a href="https://leetcode.com/problems/car-pooling/discuss/319088/Simple-Python-solution">1094. Car Pooling</a></p>
<p><a href="https://leetcode.com/problems/corporate-flight-bookings/discuss/328949/Simple-Python-solution">1109. Corporate Flight Bookings</a></p>
<p><a href="https://leetcode.com/problems/the-skyline-problem/discuss/325070/SImple-Python-solutions">218. The Skyline Problem</a></p>
<p></p>
<p></p>
<p></p>
<p></p></td>
<td><table>
<colgroup>
<col style="width: 44%" />
<col style="width: 55%" />
</colgroup>
<thead>
<tr class="header">
<th><p>![image2](../../resources/66269c261fb3480e9b778a41ce1faa76.png)</p>
<p></p></th>
<th><p>![image3](../../resources/c8aa89094c1540f5a390ce490eaf1054.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
</tbody>
</table>
