
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>BFS use to find Minimum path</p>
<p></p>
<p><a href="https://leetcode.com/problems/rotting-oranges/description/">994. Rotting Oranges</a></p>
<p></p>
<p>class Solution {</p>
<p>public:</p>
<p>  int orangesRotting(vector&lt;vector&lt;int&gt;&gt;&amp; g) {</p>
<p>    queue&lt;vector&lt;int&gt;&gt; q; // i, j, time of rotton oranges</p>
<p>    int freshCnt = 0;</p>
<p>    for(int i=0;i&lt;g.size();i++){</p>
<p>      for(int j=0;j&lt;g[0].size();j++){</p>
<p>        if(g[i][j]==2){</p>
<p>          q.push({i,j,0});</p>
<p>        }</p>
<p>        if(g[i][j]==1){</p>
<p>          freshCnt++;</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>    int ans = 0;</p>
<p>    vector&lt;int&gt; d = {1,0,-1,0,1};</p>
<p>    while(!q.empty()){</p>
<p>      vector&lt;int&gt; node = q.front(); q.pop();</p>
<p>      int i = node[0], j = node[1], time = node[2];</p>
<p>      for(int x=0;x&lt;4;x++)</p>
<p>      {</p>
<p>        int ii = i+d[x], jj = j+d[x+1];</p>
<p>        if(ii&gt;=0 &amp;&amp; jj&gt;=0 &amp;&amp; ii&lt;g.size() &amp;&amp; jj&lt;g[0].size() &amp;&amp; g[ii][jj] == 1)</p>
<p>        {</p>
<p>          g[ii][jj] = 2; // use visited vec</p>
<p>          freshCnt--;</p>
<p>          ans = max(ans,time+1);</p>
<p>          q.push({ii,jj,time+1});</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>   </p>
<p>    if(freshCnt != 0) return -1;</p>
<p>    return ans;</p>
<p>  }</p>
<p>};</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/01-matrix/description/">542. 01 Matrix</a> same as Rotting oranges :</p>
<p>Just Always create own mat don't use given data</p>
<p></p>
<p>class Solution {</p>
<p>public:</p>
<p>  vector&lt;vector&lt;int&gt;&gt; updateMatrix(vector&lt;vector&lt;int&gt;&gt;&amp; m) {</p>
<p>    queue&lt;vector&lt;int&gt;&gt; q;</p>
<p>    for(int i=0;i&lt;m.size();i++){</p>
<p>      for(int j=0;j&lt;m[0].size();j++){</p>
<p>        if(m[i][j]==0){</p>
<p>          q.push({i,j,0});</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>    vector&lt;vector&lt;bool&gt;&gt; vis(m.size(), vector&lt;bool&gt; (m[0].size(), false));</p>
<p>    vector&lt;vector&lt;int&gt;&gt; ans(m.size(), vector&lt;int&gt; (m[0].size(), 0));</p>
<p>    vector&lt;int&gt; d = {-1,0,1,0,-1};</p>
<p>    while(!q.empty())</p>
<p>    {</p>
<p>      auto fr = q.front(); q.pop();</p>
<p>      int i = fr[0], j = fr[1], dis = fr[2];</p>
<p>      for(int x=0;x&lt;4;x++){</p>
<p>        int ii = d[x] + i, jj = d[x+1] + j;</p>
<p>        if(ii &gt;= 0 and jj &gt;=0 and ii&lt;m.size() and jj&lt;m[0].size() and vis[ii][jj] == false and m[ii][jj] != 0)</p>
<p>        {</p>
<p>          vis[ii][jj] = true;</p>
<p>          q.push({ii,jj,dis + 1});</p>
<p>          ans[ii][jj] = dis + 1;</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>    return ans;</p>
<p>  }</p>
<p>};</p></td>
</tr>
<tr class="even">
<td></td>
</tr>
</tbody>
</table>
