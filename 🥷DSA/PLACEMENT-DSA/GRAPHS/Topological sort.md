AM

\> Will always possible in Drected Acyclic graph ( without cycle )
\> Topological Sort -
  Liner Ordering of Vertices such that
  *if (* there is an edge between u & v )
    than u appears before v
\> Multiple possible

u ---\> v \<--- x

topo = u, x, v \| u, x, v

![image1](../../resources/e7e8f74926a74b07a020cd40e3e50841.png)

dfs(0) -\> dfs(3) -\> dfs(1) -\> dfs(4)
fill stack \<---

stack ( 4,1,3 )

dfs(0) -\> dfs(2) -\>
fill stack \<---
stack (4,1,3,2,0)

dfs(5) -\>
fill stack \<---
stack (4,1,3,2,0,5)

ans = 5, 0, 2, 3, 1, 4

class Solution
{
  public:
  void dfs(vector\<int\> adj\[\],int u,stack\<int\> &st, vector\<bool\> &vis)
  {
    vis\[u\] = true;
    *for*(auto &&v: adj\[u\]){
      *if*(!vis\[v\]){
        dfs(adj,v,st,vis);
      }
    }
    st.push(u); *// add my V first then me*
  }

  vector\<int\> topoSort(int V, vector\<int\> adj\[\])
  {
    vector\<bool\> vis(V,false);
    stack\<int\> st;
    *for*(int i=0;i\<V;i++){
      *if*(!vis\[i\]){
        dfs(adj, i, st, vis);
      }
    }
    vector\<int\> ans;
    *while*(!st.empty()){
      ans.push_back(st.top());
      st.pop();
    }
    *return* ans;
  }
};

\- TC = (V+E) worst case
\- SC = 0(n) stack + 0(n) recursion

------------------------------------------------------------------------
Kahn's Algorithm (using BFS)

![image2](../../resources/c090ee11fbe449ae80188d86ccafb73f.png)

