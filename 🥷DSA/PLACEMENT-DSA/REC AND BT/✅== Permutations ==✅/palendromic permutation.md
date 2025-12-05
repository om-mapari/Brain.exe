
![image1](../../../resources/ab68b95350cc47ec8c0cb3e4bd73120f.png)

a4b4c1=\> permutation(a2b2c0) + c + rev(permutation(a2b2c0)

a2b2c0 = fac(4)/fac(2)\*fac(2) = 5\*2\*3=30

permutation possible if
1.  every char count is even
2.  or only one char count is odd

*\#include* \<iostream\>

using namespace std;

*\#include* \<bits/stdc++.h\>

vector\<string\> permut;

void permutation(unordered_map\<char, int\> &um, int len, string asf)

{

  *if* (len == 0) {

    permut.push_back(asf);

  }

  *for* (auto &i : um)

  {

    *if* (i.second != 0) {

      i.second--;

      permutation(um, len - 1, asf + i.first);

      i.second++;

    }

  }

}

void solve(string s)

{

  unordered_map\<char, int\> um;

  *for* (auto i : s) um\[i\]++;

  int oddcnt = 0;

  char oddChar = '0';

  int len = 0;

  *for* (auto && i : um)

  {

    *if* (i.second & 1) {

      oddcnt++;

      oddChar = i.first;

    }

    i.second = i.second / 2;

    len += i.second;

  }

  *if* (oddcnt \> 1) *return*; *// condition*

  permutation(um, len, "");

  *for* (auto &i : permut) {

    string revStr = "";

    *for* (int j = i.size() - 1; j \>= 0; j--) revStr += i\[j\]; *// revStr*

    *if* (oddChar != '0') i = i + oddChar + revStr;

    *else* i += revStr;

  }

  *for* (auto i : permut)

  {

    cout \<\< i \<\< endl;

  }

}

int main()

{

  string s = "aaaabbbbc";

  solve(s);

  *return* 0;

}

Ans :

aabbcbbaa

ababcbaba

abbacabba

baabcbaab

babacabab

bbaacaabb

9!/ 4!\*4!

(9\*8\*7\*6)/(4\*3\*2)=126

