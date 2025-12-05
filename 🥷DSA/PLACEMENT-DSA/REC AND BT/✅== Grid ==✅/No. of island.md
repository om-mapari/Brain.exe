AM

<table>
<colgroup>
<col style="width: 37%" />
<col style="width: 62%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/number-of-islands/">200. Number of Islands</a></p>
<p></p>
<p></p>
<p><strong>Input:</strong> grid = [<br />
["1","1","0","0","0"],<br />
["1","1","0","0","0"],<br />
["0","0","1","0","0"],<br />
["0","0","0","1","1"]<br />
]</p>
<p><strong>Output:</strong> 3</p>
<p></p>
<p></p>
<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 83%" />
</colgroup>
<thead>
<tr class="header">
<th><p>TC =</p>
<p>0(n)</p></th>
<th>bcoz in worst case we traverse a cell 5 times once while processing and 4 time while coming back from adjecent cell calls</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SC = 0(m*n)</td>
<td><p>stack space =</p>
<p>so at max it will be no of m*n as we can triverse like snake</p></td>
</tr>
</tbody>
</table>
<p></p></th>
<th><p>![image1](../../../resources/fed4776412c841faad4414c1f73d83fd.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/island-perimeter/">463. Island Perimeter</a></p>
<p></p>
<p>find water area</p>
<p></p>
<p>Input: grid = [[0,1,0,0],</p>
<p>[1,1,1,0],</p>
<p>[0,1,0,0],</p>
<p>[1,1,0,0]]</p>
<p>Output: 16</p>
<p></p>
<p></p>
<p>![image2](../../../resources/fbfe03ae97b34eb6b155225f0e0c8f4b.png)</p>
<p></p>
<p>Ans = 16</p></td>
<td><p>![image3](../../../resources/95066dd90ad04ae69b0e9ed2d7835f5f.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/max-area-of-island/">695. Max Area of Island</a></p>
<p>![image4](../../../resources/d977008b394c4a21b623ac0ffe986c92.png)</p>
<p></p>
<p></p>
<p>Area = 6; problem occer at but i hendle it</p></td>
<td><p>![image5](../../../resources/7b6cd32c2de24fa58b123fe715b58c5e.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/surrounded-regions/">130. Surrounded Regions</a></p>
<p></p>
<p>Approch 1 = Move on boundry and mark them as 'M'</p>
<p></p>
<p></p>
<p>![image6](../../../resources/b6e78abc97d74d1cad98662cf966dd41.jpg)</p>
<p></p>
<p></p></td>
<td><p>Run on Boundery</p>
<p>if(i * j == 0 || i == b.size() - 1 || j == b[i].size() - 1)</p>
<p></p>
<p>![image7](../../../resources/adc06bd026cb4c459dd2d375d81bb20c.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/out-of-boundary-paths/">576. Out of Boundary Paths</a></p>
<p></p>
<p>![image8](../../../resources/27769a40ce87418eb4ec7e0aecca3aa1.png)</p>
<p></p></td>
<td><p>![image9](../../../resources/7c42ca1683a244de9cf2484dee77d1e3.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/number-of-closed-islands/">1254. Number of Closed Islands</a></p>
<p></p>
<p>![image10](../../../resources/1a82ec4351054737a7bb2f12b59482ea.png)</p>
<p></p></td>
<td><p></p>
<p>class Solution {</p>
<p>public:</p>
<p>  vector&lt;int&gt; v = {-1,0,1,0,-1};</p>
<p>  void dfs(vector&lt;vector&lt;int&gt;&gt; &amp;grid, int i, int j,bool &amp;check)</p>
<p>  {</p>
<p>    if(i &lt; 0 or j &lt; 0 or i &gt;= grid.size() or j &gt;=grid[0].size()) {</p>
<p>      check = false;</p>
<p>      return;</p>
<p>    }</p>
<p>    if(grid[i][j] == 1) return ;</p>
<p>    grid[i][j] = 1;</p>
<p>    for(int x=0;x&lt;4;x++){</p>
<p>      int ni = i + v[x], nj = j + v[x+1];</p>
<p>      dfs(grid,ni,nj,check);</p>
<p>    }</p>
<p>  }</p>
<p>  int closedIsland(vector&lt;vector&lt;int&gt;&gt;&amp; grid) {</p>
<p>    int cnt = 0;</p>
<p>    for(int i=0;i&lt;grid.size();i++){</p>
<p>      for(int j=0;j&lt;grid[0].size();j++){</p>
<p>        if(grid[i][j] == 0){</p>
<p>          bool check = true;</p>
<p>          dfs(grid,i,j,check);</p>
<p>          if(check) cnt++;</p>
<p>        }</p>
<p>      }</p>
<p>    }</p>
<p>    return cnt;</p>
<p>  }</p>
<p>};</p></td>
</tr>
</tbody>
</table>

![image11](../../../resources/ec44b3f0153348c1a78f278c717cd0cb.png)

![image12](../../../resources/8710f6333fdf43c991abc68798e7e1f0.png)![image13](../../../resources/1b66d9074f3d4a9995c1cb45cff6fe9f.png)

![image14](../../../resources/35f39bb9e3014e9881e282335148ee2f.png)
