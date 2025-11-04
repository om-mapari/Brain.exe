
(1 \<\< 31 or 2^31) =\> -2147483648
INT_MAX  =\> 2147483647
INT_MAX+1 =\> -2147483648

=================================================

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
int main()
{
  int y = (1 \<\< 31);
  int x = INT_MAX;
  cout \<\< "(1 \<\< 31 or 2^31) =\> " \<\< y \<\< endl;
  cout \<\< "INT_MAX =\> " \<\< x \<\< endl;
  x++;
  cout \<\< "INT_MAX+1 =\> " \<\< x \<\< endl;
  *return* 0;
}
