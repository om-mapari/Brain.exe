
\#include \<iostream\>
using namespace std;
\#include \<bits/stdc++.h\>
vector\<int\> dp;

// Energy ? to reach nth stair from 1st stair

int frogjump(vector\<int\> &arr, int i)
{
if (i == 0) return 0;
if (dp\[i\] != -1) return dp\[i\];
int left = frogjump(arr, i - 1) + abs(arr\[i\] - arr\[i - 1\]);
int right = INT_MAX;
if (i \> 1) right = frogjump(arr, i - 2) + abs(arr\[i\] - arr\[i - 2\]);
return dp\[i\] = min(left, right);
}
int main()
{

vector\<int\> arr = {10, 20 , 30 , 10};
int n = arr.size();
dp.resize(n, -1);
cout \<\< frogjump(arr, n - 1) \<\< endl;
return 0;
}
