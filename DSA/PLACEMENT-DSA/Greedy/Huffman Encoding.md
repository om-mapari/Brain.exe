
[Huffman Encoding](https://practice.geeksforgeeks.org/problems/huffman-encoding3345/1)

class TreeNode {
  public:
  TreeNode\* left;
  TreeNode\* right;
  int val = 0;
  TreeNode(int v)
  {
    left = right = NULL;
    val = v;
  }
};
class com{
  public:
  bool operator()(TreeNode\* a, TreeNode\* b)
  {
    *return* a-\>val \> b-\>val;
  }
};
class Solution
{
  public:
    vector\<string\> ans;
    void solve(TreeNode\* root,string tem)
    {
      *if*(!root) *return*;
      *if*(!root-\>left && !root-\>right)
      {
        ans.push_back(tem);
      }
      solve(root-\>left, tem+'0');
      solve(root-\>right, tem+'1');
    }
    vector\<string\> huffmanCodes(string S,vector\<int\> f,int N)
    {
      priority_queue\<TreeNode\*, vector\<TreeNode\*\>, com\> pq;
      *for*(auto i: f) pq.push(new TreeNode(i));
      *while*(pq.size()!=1){
        auto x = pq.top(); pq.pop();
        auto y = pq.top(); pq.pop();
        TreeNode\* n = new TreeNode(x-\>val + y-\>val);
        n-\>left = x;
        n-\>right = y;
        pq.push(n);
      }

      solve(pq.top(),"");
      *return* ans;
    }
};

