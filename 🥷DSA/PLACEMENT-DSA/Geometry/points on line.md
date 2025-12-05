
[149. Max Points on a Line](https://leetcode.com/problems/max-points-on-a-line/description/)

class Solution {
public:
  int maxPoints(vector\<vector\<int\>\>& p) {
    if(p.size() == 1 or p.size()==2) return p.size();
    int n = p.size();
    int res = INT_MIN;
    for(int i=0;i\<n;i++){
      for(int j=i+1;j\<n;j++)
      {
        float x1,y1,x2,y2;
        int dy = p\[i\]\[1\] - p\[j\]\[1\];
        int dx = p\[i\]\[0\] - p\[j\]\[0\];
        int pnt = 2;
        for(int k=j+1;k\<n;k++)
        {
          int \_dy = p\[i\]\[1\] - p\[k\]\[1\]; // y2-y1
          int \_dx = p\[i\]\[0\] - p\[k\]\[0\]; // x2-x1
          if(dy \* \_dx == dx \* \_dy) pnt++;
        }
        res = max(res, pnt);
      }
    }
    return res;
  }
};

Optimized

class Solution {
public:
  int maxPoints(vector\<vector\<int\>\>& p) {
    if(p.size() == 1 or p.size()==2) return p.size();
    int n = p.size(), res = 0;
    for(int i=0;i\<n;i++){
      unordered_map\<double,int\> mp; // slope, cnt
      for(int j=0;j\<n;j++)
      {
        if(i==j) continue; // VVV IMP // not work j=i+1
                 // as theta is diff for both
        auto dy = p\[i\]\[1\] - p\[j\]\[1\];
        auto dx = p\[i\]\[0\] - p\[j\]\[0\];
        auto theta = atan2(dy,dx);
        mp\[theta\]++;
      }
      for(auto &it: mp) res = max(res,it.second+1);
    }
    return res;
  }
};

Better way to Use string "1#2"
class Solution {
public:
  int maxPoints(vector\<vector\<int\>\>& p) {
    if(p.size() == 1 or p.size()==2) return p.size();
    int n = p.size(), res = 0;
    for(int i=0;i\<n;i++){
      unordered_map\<string,int\> mp; // slope, cnt
      for(int j=0;j\<n;j++)
      {
        if(i==j) continue; // VVV IMP // not work j=i+1
                 // as theta is diff for both
        auto dy = p\[i\]\[1\] - p\[j\]\[1\];
        auto dx = p\[i\]\[0\] - p\[j\]\[0\];
        int gcd = \_\_gcd(dy,dx);
        dy = dy/gcd; dx = dx/gcd;
        mp\[to_string(dy) + "#" + to_string(dx)\]++;
      }
      for(auto &it: mp) res = max(res,it.second+1);
    }
    return res;
  }
};

