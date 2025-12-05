
vis\[u\] = visited
!vis\[u\] = not visited

void DFS (adj, int u, vis)
{ 
  vis\[u\] = true; ans.push_back(u);

  *for* (auto &v : adj\[u\])
  {
    *if*( vis\[v\] ) DFS (adj, v, vis)
  }
}

void BFS (adj, int u, vis)
{
  queue\<int\> q;
  q.push(u); vis\[u\] = ture; ans.push_back(u);

  *while*(!q.empty())
  {
    int u = q.front(); q.pop();

    *for*(auto &v : adf\[u\])
    {
      *if*( !vis\[v\] ) {
        q.push(v); vis\[v\] = true; ans.push_back(u);
      }
    }
  }
}

\> BFS = shortest path
\> PUSH -\> VISIT -\> RESULT PVR
\> use "*for* loop" *for* More than 1 component

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>

*// \*\*\*\*\*\* BFS \*\*\*\*\*\* //*

*// 1 component*
void bfs(vector\<vector\<int\>\> &adj, int src)
{
  queue\<int\> q;
  vector\<int\> vis(adj.size(), false);
q.push(src);
  vis\[src\] = true;
  *while* (!q.empty()) {
    int u = q.front(); q.pop();
    cout \<\< u \<\< " ";
    *for* (auto v : adj\[u\]) {
      *if* (!vis\[v\]) {
        vis\[v\] = true; *//\*forgotten*
        q.push(v);
      }
    }
  }
}

*// more than 1 component*

void bfs2(vector\<vector\<int\>\> &adj, int src, vector\<int\> &vis)
{
  queue\<int\> q;
  q.push(src);
 vis\[src\] = true;
  *while* (!q.empty()) {
    int u = q.front(); q.pop();
    cout \<\< u \<\< " ";
    *for* (auto v : adj\[u\]) {
      *if* (!vis\[v\]) {
        q.push(v);
vis\[v\] = true; *//\*forgotten*
      }
    }
  }
}

void bfs2(vector\<vector\<int\>\> &adj)
{
  vector\<int\> vis(adj.size(), false);
  int component = 0;
  *for* (int i = 0; i \< adj.size(); i++) {
    *if* (!vis\[i\]) {
      bfs2(adj, i, vis);
      component++;
    }
  }
  cout \<\< endl \<\< component \<\< endl;
}

*// \*\*\*\*\*\* DFS \*\*\*\*\*\* //*

void dfs(vector\<vector\<int\>\> &adj, int s, vector\<int\> &vis)
{
  vis\[s\] = true;
  cout \<\< s \<\< " ";
  *for* (auto i : adj\[s\])
    *if* (!vis\[i\]) dfs(adj, i, vis);
}

void dfsRun(vector\<vector\<int\>\> &adj)
{
*  // component = 1 TC = stack space*
*// SC = O(N) + O(N) + O(N) nodes in rec + vis + rec stack space*
*// TN = O(N) visiting every node + 2 \* E (for loop inside)*
  vector\<int\> vis(adj.size());
*  // dfs(adj, 0, vis);*

*  // component \> 1*
  int component = 0;
  *for* (int i = 0; i \< adj.size(); i++) {
    *if* (!vis\[i\]) {
      dfs(adj, i, vis);
      component++;
    }
  }
  cout \<\< endl \<\< component \<\< endl;
}
int main()
{
  vector\<vector\<int\>\> v(5);
  v\[0\] = {1, 2};
  v\[1\] = {2, 3};
  v\[2\] = {0, 1, 3, 4};
  v\[3\] = {1, 2, 4};
  v\[4\] = {2, 3};
*  // bfs(v, 0);*
*  // dfsRun(v);*

  vector\<vector\<int\>\> v2(9);
  v2\[0\] = {1, 2};
  v2\[1\] = {0, 2};
  v2\[2\] = {0, 1};
  v2\[3\] = {4};
  v2\[4\] = {3};

  v2\[5\] = {6, 7};
  v2\[6\] = {5};
  v2\[7\] = {5, 8};
  v2\[8\] = {7};
*  // bfs2(v2);*
  dfsRun(v2);
  *return* 0;
}
