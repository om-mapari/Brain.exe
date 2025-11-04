AM

type of problems:

- Type I : fixed size k win = lar/small ask
- Type II: variable size win = given condi
find subarray
================================================

Useful calculations

- if Size of window = k
- then no. of windows = n-k+1

================= BF apparoch ===================

BF apparoch
= window size k = 2
= 1 2 3 4 5 6 // 6 - 2 + 1
for( i = 0 --\> i \< n - k + 1 )
for( j = i --\> j \< i + k )

*// Returns maximum sum in a subarray of size k.*
*// TC = O(n\*k)*
void maxSum(vector\<int\> &arr, int k)
{
  int n = arr.size(), mx = INT_MIN;
*  // total Wins = n-k+1*
  *for* (int i = 0; i \< n - k + 1; i++) {
    int sum = 0;
*    // j=i --\> j\<(i+k)*
    *for* (int j = i; j \< i + k; j++)
      sum = sum + arr\[j\];
    mx = max(sum, mx);
  }
  cout \<\< mx \<\< endl;
}

int k = 3 , n = 5; // 0 1 2 3 4
for (int i = 0; i \< n - k + 1; i++)
{
for (int j = i; j \< i + k ; j++) {

cout \<\< i \<\< " " \<\< j \<\< endl;
}
cout \<\< endl;
}

0 0
0 1
0 2

1 1
1 2
1 3

2 2
2 3
2 4

================= Optimization ===================
Max Win Sum

*// Tc = O(n)*
void SildingWin(vector\<int\> &arr, int k)
{
  int n = arr.size(), mx = INT_MIN;
  int sum = 0;

  *for* (int i = 0; i \< k; i++) {
    sum += arr\[i\]; *// first window*
  }
  mx = max(mx, sum);

  *for* (int i = k; i \< n; i++)
  {
    sum += arr\[i\]; *// aquire*
    sum -= arr\[i - k\]; *// release*
    mx = max(mx, sum);
  }
  cout \<\< mx \<\< endl;
}

================ Variable size ===================

