
*\#include* \<iostream\>

using namespace std;

*\#include* \<bits/stdc++.h\>

void permutations2(string &s, string &tem)

{

  *if* (tem.size() == s.size()) {

    cout \<\< tem \<\< endl;

    *return*;

  }

  *for* (int i = 0; i \< s.size(); ++i)

  {

    *if* (s\[i\] != '\*')

    {

      char ch = s\[i\];

      s\[i\] = '\*'; // to show it is used

      tem += ch;

      permutations2(s, tem);

      tem.pop_back();

      s\[i\] = ch;

    }

  }

}

int main()

{

  string s = "abc";

  string tem = "";

  permutations2(s, tem);

  *return* 0;

}

Ans =

abc

acb

bac

bca

cab

cba

![image1](../../resources/2d2c8c0959104f54873bb69ca04987bf.png)

1.  Permutation when ( All unique )

![image2](../../resources/4aa2f88388694a698eb0fec53836eafa.png)

2.  Permutation (Dublicate exist)

![image3](../../resources/ae78d7be060c4a95bcea985453c347ef.png)

![image4](../../resources/ee5f4f3962f94b1d9b58c91410514d9e.png)

permutations ( distinct integers )

TC = n!(as genrating premutation) \* n (for interating on arr every time)

SC = 0(n) tem for single result + 0(n) for visited

reduced space

