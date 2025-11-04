AM

- Detect cycle
  - undirected - DFS, BFS
  - directed - DFS, BFS

==================================================================

For undirect graph \[ DFS \]

1 --- 2 -- 3 IMP POINT = don't go back to parent

\| \|

5 -- 4

dfs(1) -\> dfs(2) -\> dfs(3) -\> dfs(4) -\> dfs(5) -\> dfs(2)

returns true

bool DFS (adj, int u, vis, int parent)

{

vis\[u\] = true;

for(auto &v: adj\[u\])

{

if( v == parent ) continue;

if( vis\[v\] == true ) return true; // cycle detected

if( DFS(adj,v,vis,u) ) return true;

}

return false;

}

do this for all compoenent

vector\<bool\> vis(V, false);

for(int i=0;i\<V;i++){

if(vis\[i\] == false)

{

if(dfs(adj, i, vis, -1)) return true;

}

}

return false;

==================================================================

class Solution {

 public:

*  // undirected graph. \[ BFS \]*

  bool bfs(vector\<int\> adj\[\], int u, vector\<bool\> &vis)

  {

    queue\<pair\<int,int\>\> q;

    q.push({u,-1}); vis\[u\] = true;

   

    *while*(!q.empty())

    {

      auto fr = q.front(); q.pop();

      int u = fr.first;

      int parent = fr.second;

     

      *for*(auto &v : adj\[u\])

      {

        *if*(v == parent) *continue*;

       

        *if*(vis\[v\] == true) *return* true;

       

        q.push({v, u}); vis\[v\] = true;

      }

     

    }

    *return* false;

  }

  bool isCycle(int V, vector\<int\> adj\[\]) {

    vector\<bool\> vis(V, false);

   

    *for*(int i=0;i\<V;i++){

      *if*(vis\[i\] == false)

      {

        *if*(dfs(adj, i, vis)) *return* true;

      }

    }

    *return* false;

  }

};

==================================================================

//not done = HARD = for DIRECTED [graph](https://practice.geeksforgeeks.org/problems/detect-cycle-in-an-undirected-graph/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)

class Solution {

public:

bool dfs(vector\<int\> adj\[\], int u, vector\<bool\> &vis ,vector\<bool\> &path)

{

vis\[u\] = true;

path\[u\] = true;

for(auto &v: adj\[u\])

{

if(!vis\[v\]){

if(dfs(adj,v,vis,path)) return true;

}

else { // if node vis on the same path return true

if(path\[v\] == true) return true;

}

}

path\[u\] = false;

return false;

}

bool isCyclic(int V, vector\<int\> adj\[\]) {

vector\<bool\> vis(V, false);

vector\<bool\> path(V, false);

for(int i=0;i\<V;i++)

{

if(vis\[i\] == false)

{

if(dfs(adj, i, vis, path)) return true;

}

}

return false;

}

};

