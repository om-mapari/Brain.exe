
1.  Print Root to Node Path
class Solution
{
public:
  void answer(node \*root)
  {
    vector\<int\> path;
    int n = 8;
    cout\<\<root_to_any_node_path(root, path, n)\<\<endl;
    for(auto i: path) cout\<\<i\<\<" ";
    cout\<\<endl;
  }
*  // <https://www.geeksforgeeks.org/print-path-root-given-node-binary-tree/>*
  bool root_to_any_node_path(node \*root, vector\<int\> &path, int n)
  {
    if (!root) return false;
    path.push_back(root-\>val);
    if (root-\>val == n) return true;

    if(root_to_any_node_path(root-\>left, path, n) \|\|
    root_to_any_node_path(root-\>right, path, n)) return true;
    path.pop_back();
    return false ;
  }
};

![image1](../../resources/1e798c3c7cf243558a8f5605de725cbe.png)
