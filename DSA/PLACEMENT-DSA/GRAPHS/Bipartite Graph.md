
[785. Is Graph Bipartite?](https://leetcode.com/problems/is-graph-bipartite/description/)

Bipartite Graph is a graph =\>

if graph colored with 2 color such that two adj nodes don't have same color

class Solution {
public:
  bool isBipartite(vector\<vector\<int\>\> &g, int u,int col, vector\<int\> &color)
  {
    color\[u\] = col;
    for(auto &&v: g\[u\])
    {
      if(color\[v\] == -1)
      {
        int newCol = (col == 1) ? 0 : 1;
        if(isBipartite(g,v,newCol, color) == false) return false;
      } else {
        if(color\[v\] == col) return false;
      }
    }
    return true;
  }
  bool isBipartite(vector\<vector\<int\>\>& graph) {
    vector\<int\> color(graph.size(),-1);
    for(int i=0;i\<graph.size();i++)
    {
      if(color\[i\] == -1)
      {
        if(isBipartite(graph,i,1,color) == false) return false;
      }
    }
    return true;
  }

  bool is(vector\<vector\<int\>\> &g, int s,vector\<int\> &color)
  {
    queue\<int\> q;
    q.push(s); color\[s\] = 1;
    while(!q.empty())
    {
      auto u = q.front(); q.pop();
      int col = color\[u\];
      for(auto &&v: g\[u\])
      {
        if(color\[v\] == -1){
          int newCol = (col == 1)? 0 : 1;
          color\[v\] = newCol;
          q.push(v);
        } else {
          if (col == color\[v\]) return false;
        }
      }
    }
    return true;
  }
  bool isBipartiteBFS(vector\<vector\<int\>\>& g) {
    vector\<int\> color(g.size(), -1);
    for(int i=0;i\<g.size();i++){
      if(color\[i\] == -1)
      {
        if(is(g,i,color) == false) return false;
      }
    }
    return true;
  }
};

