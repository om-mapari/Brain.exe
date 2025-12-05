
[Triverse spiral matrix](https://leetcode.com/problems/spiral-matrix/description/)

class Solution {
public:
  vector\<int\> spiralOrder(vector\<vector\<int\>\>& m) {
    int left = 0, right = m\[0\].size()-1, top = 0, bot = m.size()-1;
    vector\<int\> ans;
    while(left \<= right && top \<= bot)
    {
      // left -\> right
      for(int i=left;i\<=right;i++){
        ans.push_back(m\[top\]\[i\]);
      }
      top++;
      // top -\> bot
      for(int i=top;i\<=bot;i++){
        ans.push_back(m\[i\]\[right\]);
      }
      right--;
      // right -\> left
      if(top \<= bot)
      {
        for(int i=right;i\>=left;i--){
          ans.push_back(m\[bot\]\[i\]);
        }
        bot--;
      }
      // bot -\> top
      if(left \<= right)
      {
        for(int i=bot;i\>=top;i--){
          ans.push_back(m\[i\]\[left\]);
        }
        left++;
      }
    }
    return ans;
  }
};

replace

![image1](../../resources/324b19a07b33412fb160490cfa771722.png)

