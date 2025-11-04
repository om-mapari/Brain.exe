
![image1](../../resources/f5529d9f532d427497619a1fc0a955b0.png)

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void coinChange(vector\<int\> &arr, vector\<int\> &tem, int sum, int idx)
{
  *if* (sum \< 0) *return*;
  *if* (sum == 0) {
    *for* (auto i : tem) cout \<\< i \<\< " ";
    cout \<\< endl;
    *return*;
  }
  *if* (idx == arr.size()) *return*;
  tem.push_back(arr\[idx\]);
  coinChange(arr, tem, sum - arr\[idx\], idx + 1);
  tem.pop_back();
  coinChange(arr, tem, sum, idx + 1);
}
void coinChange2(vector\<int\> &arr, vector\<int\> &tem, int sum, int idx)
{
  *if* (sum \< 0) *return*;
  *if* (sum == 0) {
    *for* (auto i : tem) cout \<\< i \<\< " ";
    cout \<\< endl;
    *return*;
  }
  *if* (idx == arr.size()) *return*;
  tem.push_back(arr\[idx\]);
  coinChange2(arr, tem, sum - arr\[idx\], idx);
  tem.pop_back();
  coinChange2(arr, tem, sum, idx + 1);
}
int main()
{
  vector\<int\> arr = {2, 3, 5, 6, 7};
  vector\<int\> tem ;
  cout \<\< "== single time take ==" \<\< endl;
  coinChange(arr, tem, 12, 0);
  cout \<\< "== multiple time take ==" \<\< endl;
  coinChange2(arr, tem, 12, 0);
  *return* 0;
}

== single time take ==
2 3 7
5 7
== multiple time take ==
2 2 2 2 2 2
2 2 2 3 3
2 2 2 6
2 2 3 5
2 3 7
2 5 5
3 3 3 3
3 3 6
5 7
6 6
