
1.  Base Code :

  int solve(node\* root,int &res){
    if(!root) return 0;
    int l = solve(root-\>left,d);
    int r = solve(root-\>right,d);
    int temp = condition ; * // case 1 : I will pass the best*
    int ans = max(temp,releation); *// case 2 : I am real ans*
    res = max(res,ans);
    return temp;
  }

![image1](../../resources/490562849ae54e739104400213d00568.png)

1.  Dimeter \| From leaf to leaf is dimeter
Longest Distence between any two nodes
  int dimeter(node\* root,int &d){
    if(!root) return 0;
    int l = dimeter(root-\>left,d);
    int r = dimeter(root-\>right,d);
    int temp = max(l,r) + 1; * // case 1 : I will pass the best*
    int ans = max(temp,l+r+1); *// case 2 : I am ans*
    d = max(d,ans);
    return temp;
  }

![image2](../../resources/68c148bfd30c4a4f8b370b346775456f.png)

2.  Maximum Path Sum \| From any Node to any
only problem with -ve value in tree

  int max_path_sum(node\* root,int &res){
    if(!root) return 0;
    int l = max_path_sum(root-\>left,res);
    int r = max_path_sum(root-\>right,res);
    int temp = max(max(l,r) + root-\>val,root-\>val);
*// it will choose best (but what if both are -ve therefor max(max used))*
    int ans = max(temp,l+r+root-\>val); *// case 2 : if I am ans*
    res = max(res,ans);
    return temp;
  }

![image3](../../resources/199e3fc413f144888d148f01f765a57a.png)

3.  Max Path Sum \| From leaf to leaf

![image4](../../resources/4501e38a0480434fbc0ba1ff0df4410e.png)

