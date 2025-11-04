AM

\> Problems on BFS/DFS
multisource dfs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/number-of-provinces/description/">547. Number of Provinces</a></p>
<p></p>
<p>// adj matrix</p>
<p>class Solution {</p>
<p>public:</p>
<p>  void dfs(vector&lt;vector&lt;int&gt;&gt; &amp;adj, int u,vector&lt;bool&gt; &amp;vis)</p>
<p>  {</p>
<p>    if(vis[u] == true) return;</p>
<p>    vis[u] = true;</p>
<p>    for(int v=0; v &lt; adj.size(); v++){</p>
<p>      if(adj[u][v] == 1){</p>
<p>        if(!vis[v]){</p>
<p>          dfs(adj, v, vis);</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>  }</p>
<p>  int findCircleNum(vector&lt;vector&lt;int&gt;&gt;&amp; conn) {</p>
<p>    int cn = 0;</p>
<p>    vector&lt;bool&gt; vis(conn.size(), false);</p>
<p>    for(int i=0;i&lt;conn.size();i++){</p>
<p>      if(!vis[i]){</p>
<p>        dfs(conn,i,vis);</p>
<p>        cn++;</p>
<p>      }</p>
<p>    }</p>
<p>    return cn;</p>
<p>  }</p>
<p>};</p>
<p></p></th>
<th><p>// Union Find<br />
class Solution {</p>
<p>public:</p>
<p>  vector&lt;int&gt; parent;</p>
<p>  int find(int x)</p>
<p>  {</p>
<p>    return x == parent[x] ? x : find(parent[x]);</p>
<p>  }</p>
<p>  int findCircleNum(vector&lt;vector&lt;int&gt;&gt;&amp; m) {</p>
<p>    parent.resize(m.size());</p>
<p>    for(int i=0;i&lt;m.size();i++) parent[i] = i;</p>
<p>    int comp = m.size();</p>
<p>    for(int i=0;i&lt;m.size();i++){</p>
<p>      for(int j=0;j&lt;m[0].size();j++){</p>
<p>        if(m[i][j]==1 &amp;&amp; i!=j){</p>
<p>          int x = find(i);</p>
<p>          int y = find(j);</p>
<p>          if(x!=y){</p>
<p>            parent[x] = y;</p>
<p>            comp--;</p>
<p>          }</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>    return comp;</p>
<p>  }</p>
<p>};</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/minimum-time-to-collect-all-apples-in-a-tree/description/">1443. Minimum Time to Collect All Apples in a Tree</a><br />
</p>
<p></p>
<p>class Solution {</p>
<p>public:</p>
<p>  int dfs(vector&lt;vector&lt;int&gt;&gt; &amp;adj,int u, int parent, vector&lt;bool&gt; &amp;hasApple)</p>
<p>  {</p>
<p>    int total = 0;</p>
<p>    for(auto &amp;v : adj[u])</p>
<p>    {</p>
<p>      if(v == parent) continue;</p>
<p>      total += dfs(adj,v,u,hasApple);</p>
<p>    }</p>
<p>    if(total &gt; 0 or hasApple[u]) total += 2;</p>
<p>    return total;</p>
<p>  }</p>
<p></p>
<p>  int minTime(int n, vector&lt;vector&lt;int&gt;&gt;&amp; edges, vector&lt;bool&gt;&amp; hasApple) {</p>
<p>    vector&lt;vector&lt;int&gt;&gt; adj(n);</p>
<p>    for(auto i: edges)</p>
<p>    {</p>
<p>      int u = i[0], v = i[1];</p>
<p>      adj[u].push_back(v);</p>
<p>      adj[v].push_back(u);</p>
<p>    }</p>
<p>    int res = dfs(adj, 0, -1, hasApple);</p>
<p>    return res? res - 2 : 0;</p>
<p>  }</p>
<p>};</p></td>
<td></td>
</tr>
</tbody>
</table>
