AM

• Set union A \| B
• Set intersection A & B
• Set subtraction A & ~B
• Set negation ALL_BITS ^ A or ~A
• Set bit A \|= 1 \<\< bit
• Clear bit A &= ~(1 \<\< bit)
• Test bit (A & 1 \<\< bit) != 0
• Extract last bit A&-A or A&~(A-1) or x^(x&(x-1))
• Remove last bit A&(A-1)
• Get all 1-bits ~0

x =14 01110
y = 9 01001
x & y 01000
x \| y 01111
x & ~y 00110
x ^ y 00111
3 = 00011 ~3 = 11100
1's compliment of 3 \[~3\] 11100
2's compliment of 3 \[~3 + 1 = -3\] 11101
============== SET CLEAR TEST ================
y 01001 SET 3rd bit \[y \|= 1 \<\< 2\] =\> 01101
y 01101 CLR 3rd bit \[y &= ~(1 \<\< 2)\] =\> 01001
y 01001 TST 4rd bit \[y & (1 \<\< 2)\] =\> 8
(A & 1 \<\< bit) != 0 bit is SET
===== RIGHT MOST SET BIT ======
x 01110 EXTRACT RMSB \[x & 2's com(x)\] \[x & -x\] 00010 IMP
x 01110 OFF RMSB \[ x & (x-1) \] 01100 IMP

==========================================================================================

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
string fun(int n);

int main()
{
  int x = 14, y = 9 ;
  cout \<\< "x =" \<\< x \<\< " " \<\< fun(x) \<\< endl;
  cout \<\< "y = " \<\< y \<\< " " \<\< fun(y) \<\< endl;
*  // Intersection Union Subtrection*
  cout \<\< "x & y " \<\< fun(x & y) \<\< endl;
  cout \<\< "x \| y " \<\< fun(x \| y) \<\< endl;
  cout \<\< "x & ~y " \<\< fun(x & ~y) \<\< endl;
  cout \<\< "x ^ y " \<\< fun(x ^ y) \<\< endl;
  cout \<\< "3 = " \<\< fun(3) \<\< " ~3 = " \<\< fun(~3) \<\< endl;
  cout \<\< "1's compliment of 3 \[~3\] " \<\< fun(~3) \<\< endl;
  cout \<\< "2's compliment of 3 \[~3 + 1 = -3\] " \<\< fun(-3) \<\< endl;
  cout \<\< "\n============== SET CLEAR TEST ================\n";
*  // SET A BIT*
  cout \<\< "y " \<\< fun(y) \<\< " " ;
  y \|= 1 \<\< 2;
  cout \<\< " SET 3rd bit \[y \|= 1 \<\< 2\] =\> " \<\< fun(y) \<\< endl;
*  // CLEAR A BIT*
  cout \<\< "y " \<\< fun(y) \<\< " " ;
  y &= ~(1 \<\< 2);
  cout \<\< " CLR 3rd bit \[y &= ~(1 \<\< 2)\] =\> " \<\< fun(y) \<\< endl;
*  // TEST A BIT 0 OR 1*
  cout \<\< "y " \<\< fun(y) \<\< " " ;
  cout \<\< " TST 4rd bit \[y & (1 \<\< 2)\] =\> " \<\< (y & (1 \<\< 3)) \<\< endl;
  cout \<\< "(A & 1 \<\< bit) != 0 bit is SET" \<\< endl;
  cout \<\< "\n===== RIGHT MOST SET BIT ======\n";
*  // EXTRACT RMSB : FIRST SET BIT*
  cout \<\< "x " \<\< fun(x) \<\< " ";
  int rmsb = x & -x;
  cout \<\< "EXTRACT RMSB \[x & 2's com(x)\] \[x & -x\] " \<\< fun(rmsb) \<\< endl;
*  // UNSET RMSB*
*  // way 1 : x ^ rmsb*
*  // way 2 : x & (x-1)*
*  // 12 = 01100*
*  // 11 = 01011 : -1 Flip all bits including rmsb*
*  // cout \<\< fun(12) \<\< " " \<\< fun(11) \<\< endl;*
  cout \<\< "x " \<\< fun(x) \<\< " ";
  cout \<\< "OFF RMSB \[ x & (x-1) \] " \<\< fun(x & (x - 1)) \<\< endl;

  *return* 0;
}

string fun(int n)
{
  *if* (n == 0) *return* "0";
  string ans = "";
  *for* (int i = 4; i \>= 0; i--) {
    int k = n \>\> i;
    *if* (k & 1)
      ans += "1";
    *else*
      ans += "0";
  }
  *return* ans;
}
