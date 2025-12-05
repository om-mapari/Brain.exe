
*// Find the Union and Intersection of the two sorted arrays. Solution*
*// Sorted =  O(m+n) O(1)*
*// un-sorted = O(m+n) O(m+n) unordered set*

int doUnion(int a\[\], int n, int b\[\], int m) *// un-sorted*
{
  unordered_set\<int\> s;
  *for* (int i = 0; i \< n; i++)
    s.insert(a\[i\]);
  *for* (int i = 0; i \< m; i++)
    s.insert(b\[i\]);
  *return* s.size();
}
vector\<int\> intersection(vector\<int\>& nums1, vector\<int\>& nums2) {
  unordered_set\<int\> m(nums1.begin(), nums1.end());
  vector\<int\> res;
  *for* (auto a : nums2)
    *if* (m.count(a)) {
      res.push_back(a);
      m.erase(a); *// Importentd*
    }
    *return* res;
  }
}

void printUnion(int arr1\[\], int arr2\[\], int n, int m) *// Sorted*
{
  int i, j;
  i = j = 0;
  vector\<int\> v;
  *while* (i \< n && j \< m)
  {
    *if* (arr1\[i\] \< arr2\[j\])
    {
      v.push_back(arr1\[i++\]);
    }
    *else if* (arr1\[i\] \> arr2\[j\])
    {
      v.push_back(arr2\[j++\]);
    }
    *else if* (arr1\[i\] == arr2\[j\])
    {
      v.push_back(arr1\[i++\]);
      j++;
    }
  }
  *while* (i \< n)
  {
    v.push_back(arr1\[i++\]);
  }
  *while* (j \< m)
  {
    v.push_back(arr2\[j++\]);
  }
  cout \<\< i \<\< j \<\< endl;
  *for* (auto &&i : v)
  {
    cout \<\< i \<\< " ";
  }
}
void printInter(int arr1\[\], int arr2\[\], int n, int m) *// Sorted*
{
  int i, j;
  i = j = 0;
  vector\<int\> v;
  *while* (i \< n && j \< m)
  {
    *if* (arr1\[i\] \< arr2\[j\])
    {
      i++;
    }
    *else if* (arr1\[i\] \> arr2\[j\])
    {
      j++;
    }
    *else if* (arr1\[i\] == arr2\[j\])
    {
      v.push_back(arr1\[i++\]);
      j++;
    }
  }
  cout \<\< i \<\< j \<\< endl;
  *for* (auto &&i : v)
  {
    cout \<\< i \<\< " ";
  }
}
int main()
{
  int arr1\[\] = {1, 2, 4, 5, 6};
  int arr2\[\] = {2, 3, 5, 7};
  int n = sizeof(arr1) / sizeof(arr1\[0\]);
  int m = sizeof(arr2) / sizeof(arr2\[0\]);
*  // Function calling*
  printUnion(arr1, arr2, n, m);
  printInter(arr1, arr2, n, m);

  *return* 0;
}
