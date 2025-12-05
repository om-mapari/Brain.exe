AM

![image1](../../resources/398399dcce534cc6bae484fff1b80830.png)

![image2](../../resources/0460044eadbf4944ae796658a86bc72b.png)

LCD : 50 100 500 ( C = century )
M : Millennium 1000

Roman -\> Integer

class Solution {
public:
  int romanToInt(string s) {
    unordered_map\<char,int\> um ;
    um.insert({'M',1000});
    um.insert({'D',500});
    um.insert({'C',100});
    um.insert({'L',50});
    um.insert({'X',10});
    um.insert({'V',5});
    um.insert({'I',1});

    int ans = 0,i;
    *for*(i=0;i\<s.size()-1;i++)
    {
      um\[s\[i\]\]\>=um\[s\[i+1\]\] ? ans+= um\[s\[i\]\] : ans-=um\[s\[i\]\];
    }
    ans+= um\[s\[i\]\];

    *return* ans;
  }
};

