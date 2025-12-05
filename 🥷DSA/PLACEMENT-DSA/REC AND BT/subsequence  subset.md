
--------------------------------------------
Print Subset

![image1](../../resources/192d186427ea49dc8a0f099afa86adcc.png)

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void subsequence(string &s, int idx, string tem)
{
  *if* (idx == s.size()) {
    cout \<\< tem \<\< endl;
    *return*;
  }
  subsequence(s, idx + 1, tem + s\[idx\]); // included
  subsequence(s, idx + 1, tem); // not included
}
int main()
{
  string s = "abc";
  string tem = ".";
  subsequence(s, 0, tem);
  *return* 0;
}

Ans (8) = .abc .ab .ac .a .bc .b .c .
---------------------------------------------

*// modified space reduced*

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void subsequence(string &s, int idx, string &tem)
{
  *if* (idx == s.size()) {
    cout \<\< tem \<\< endl;
    *return*;
  }
  tem += s\[idx\]; // space reduced
  subsequence(s, idx + 1, tem );
  tem.pop_back();
  subsequence(s, idx + 1, tem);
}
int main()
{
  string s = "abc";
  string tem = ".";
  subsequence(s, 0, tem);
  *return* 0;
}

Ans (8) = .abc .ab .ac .a .bc .b .c .
---------------------------------------------

![image2](../../resources/e349e314cce04a529ce57ab546acd5a8.png)
*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void subsets(vector\<int\> &arr, vector\<int\> &tem, int idx)
{
  *if* (idx == arr.size()) {
    cout \<\< "\[";
    *for* (auto i : tem) cout \<\< i ;
    cout \<\< "\], ";
    *return*;
  }
  tem.push_back(arr\[idx\]);
  subsets(arr, tem, idx + 1);
  tem.pop_back();
  subsets(arr, tem, idx + 1);
}
int main()
{
  vector\<int\> arr = {1, 2, 3};
  vector\<int\> tem ;
  int sum = 0;
  subsets(arr, tem, 0);
  *return* 0;
}

Ans = \[123\], \[12\], \[13\], \[1\], \[23\], \[2\], \[3\], \[\],
==================================================
Target Sum = 3;

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void subsets(vector\<int\> &arr, vector\<int\> &tem, int &sum, int idx, int &target)
{
  *if* (idx == arr.size()) {
    *if* (target == sum) {
      cout \<\< "\[";
      *for* (auto i : tem) cout \<\< i ;
      cout \<\< "\], ";
    }
    *return*;
  }
  sum += arr\[idx\];
  tem.push_back(arr\[idx\]);
  subsets(arr, tem, sum, idx + 1, target);
  sum -= arr\[idx\];
  tem.pop_back();
  subsets(arr, tem, sum, idx + 1, target);
}
int main()
{
  vector\<int\> arr = {1, 2, 3};
  vector\<int\> tem ;
  int sum = 0, target = 3;
  subsets(arr, tem, sum, 0, target);
  *return* 0;
}

Ans = \[12\], \[3\],
==================================================

