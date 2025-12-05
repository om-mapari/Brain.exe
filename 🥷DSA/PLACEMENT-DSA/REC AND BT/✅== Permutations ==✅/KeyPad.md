
[17.Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/)

![image1](../../../resources/bd1b138b51a94cb1aeedc80e8f2909db.png)

class Solution {
public:
  unordered_map\<char, vector\<string\> \> um;
  vector\<string\> ans;
  vector\<string\> letterCombinations(string digits) {
    *if* (digits.size() == 0) *return* {} ;
    um\['2'\] = {"a", "b", "c"};
    um\['3'\] = {"d", "e", "f"};
    um\['4'\] = {"g", "h", "i"};
    um\['5'\] = {"j", "k", "l"};
    um\['6'\] = {"m", "n", "o"};
    um\['7'\] = {"p", "q", "r", "s"};
    um\['8'\] = {"t", "u", "v"};
    um\['9'\] = {"w", "x", "y", "z"};
    string tem = "";
    solve(digits, 0, tem);
    *return* ans;
  }
  void solve(string digits, int i, string &tem)
  {
    *if* (i == digits.size()) {
      ans.push_back(tem);
      *return*;
    }
    vector\<string\> v = um\[digits\[i\]\];
    *for* (auto && j : v)
    {
      tem += j;
      solve(digits, i + 1, tem);
      tem.pop_back();
    }
  }
};

=======================================================================
