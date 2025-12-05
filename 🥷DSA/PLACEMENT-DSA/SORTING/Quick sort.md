
Inplace sorting algo

using namespace std;
\#include \<bits/stdc++.h\>
int part(vector\<int\> &arr, int s, int e)
{
  int p = s;
  for (int i = s; i \< e; i++)
  {
    if (arr\[i\] \< arr\[e\])
    {
      swap(arr\[i\], arr\[p++\]);
    }
  }
  swap(arr\[e\], arr\[p\]);
  return p;
}
void Quick(vector\<int\> &arr, int s, int e)
{
  if (s \> e) return;
  int p = part(arr, s, e);
  Quick(arr, s, p - 1);
  Quick(arr, p + 1, e);
}
int main()
{
  vector\<int\> arr = {7, 2, 1, 6, 8, 5, 3, 4};
  int n = arr.size();
  Quick(arr, 0, n - 1);
  for (int atom : arr)
    cout \<\< atom \<\< " ";
  return 0;
}

