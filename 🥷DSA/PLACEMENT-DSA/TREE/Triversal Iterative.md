AM

void it_pre(node \*root)
{  
  if(!root) return ;
  stack\<node\*\> st; st.push(root);
  while (!st.empty())
  {
    node \*curr = st.top(); st.pop();
    cout\<\<curr-\>val\<\<" ";
    if(curr-\>right) st.push(curr-\>right);
    if(curr-\>left) st.push(curr-\>left);
  }
}
*//\* TC =\> O(N) && SC =\> O(h) or O(N) skew tree*
void it_in(node \*root)
{ 
  stack\<node\*\> st ;
  while (true)
  {
    if(root)
    {
      st.push(root);
      root=root-\>left; *// go to left most*
    }
    else *// if NULL*
    {
      if(st.empty()) break;
      root = st.top(); st.pop(); *// root point to parent*
      cout\<\<root-\>val\<\<" ";
      root = root-\>right; *// root point to its right*
    }
  } 
}
*//\* two stack*
*//\* TC =\> O(N) && SC =\> O(N) stack 2 space*
void it_post(node \*root)
{ 
  stack\<node\*\> s;
  vector\<int\> v;
  s.push(root);
  while(!s.empty())
  {
    node \*curr = s.top(); s.pop();
    v.push_back(curr-\>val);
    if(curr-\>left) s.push(curr-\>left);
    if(curr-\>right) s.push(curr-\>right);
  }
  reverse(v.begin(),v.end());
  for(auto i:v) cout\<\<i\<\<" ";
}
*//\* one stack*
void it_post_2(node \*root)
{
  stack\<node\*\> st ;
  while (true)
  {
    if(root)
    {
      st.push(root);
      root=root-\>left; *// (1) go to leftmost*
    }
    else
    {
      if(st.empty()) break;
      if(st.top()-\>right == NULL) *// (3) if both left and right NULL*
      {
        root = st.top(); st.pop();
        cout\<\<root-\>val\<\<" ";
        while (root==st.top()-\>right) *// special case (4) if root is right of its parent*
        {
          root=st.top();
          cout\<\<root-\>val\<\<" ";
          st.pop();
        }
      }
      if(!st.empty()) root=st.top()-\>right; *// (2) go to rightmost*
      else root = NULL;
    }
  }
}
void pre_in_post(node \*root) *//\* TC = O(3N) & SC = O(N)*
{
  stack\<pair\<node\*,int\>\> st;
  st.push({root,0});
  vector\<int\> pre,in,post;
  while (!st.empty())
  {
    node\* curr = st.top().first;
    int x = st.top().second; st.pop();

    if(x==0)
    {
      pre.push_back(curr-\>val);
      st.push({curr,++x});
      if(curr-\>left) st.push({curr-\>left,0});
    }
    else if (x==1)
    {
      in.push_back(curr-\>val);
      st.push({curr,++x});
      if(curr-\>right) st.push({curr-\>right,0});
    }
    else
    {
      post.push_back(curr-\>val);
    }
  }
  PrintV(pre);
  PrintV(in);
  PrintV(post);
  cout\<\<"End"\<\<endl;
*  // x order push*
*  // ------------------*
*  // 0 pre  left*
*  // 1 in   right*
*  // 2 post  nothing*
}
