
1.  Largest subArray with contigious element

TC = O(n^2)

max - min = i - j

find all subArray

check max-min = i-j then it's Largest subArray

*\#include* \<iostream\>

using namespace std;

*\#include* \<bits/stdc++.h\>

void LargestSubArrContiEle(vector\<int\> &arr)

{

  int n = arr.size(), maxLen = 0;

  *for* (int i = 0; i \< n; i++)

  {

    int mx = arr\[i\], mn = arr\[i\];

    unordered_set\<int\> set; *// slight optimization*

   

    *for* (int j = i ; j \< n; j++)

    {

      *if* (set.count(arr\[j\])) *break*;

      set.insert(arr\[j\]); *// slight ..*

      mx = max(arr\[j\], mx);

      mn = min(arr\[j\], mn);

      *if* (mx - mn == j - i) {

        maxLen = max(maxLen, j - i + 1);

      }

    }

  }

  cout \<\< maxLen \<\< endl;

}

int main()

{

  vector\<int\> v = {

    3, 2, 1, 19, 17, 16, 18, 20, 39, 0

  };

  LargestSubArrContiEle(v);

  *return* 0;

}

