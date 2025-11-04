
*// Use to place Element at correct position in Unsorted arr*
*// all ele left \< arr\[p\] \< all ele right*

int part(vector\<int\> &arr, int s, int e)
{
  int p = s;
  *for* (int i = s; i \< e; i++)
    *if* (arr\[i\] \< arr\[e\]) swap(arr\[p++\], arr\[i\]);
  swap(arr\[e\], arr\[p\]);
  *return* p;
}

int n = arr.size();
int s = 0 , e = n - 1;
*while* (s \<= e) {
  int p = part(arr, s, e);
  *if* (p == k) *return* arr\[k\];
  *else if* (p \> k) e = p - 1;
  *else* s = p + 1;
}
