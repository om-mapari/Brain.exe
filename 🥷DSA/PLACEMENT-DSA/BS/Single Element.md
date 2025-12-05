
[540. Single Element in a Sorted Array](https://leetcode.com/problems/single-element-in-a-sorted-array/)

Example 1:

Input: nums = \[1,1,2,3,3,4,4,8,8\]
Output: 2

Example 2:

Input: nums = \[3,3,7,7,10,11,11\]
Output: 10

class Solution {
public:
int singleNonDuplicate(vector\<int\>& arr) {
int n = arr.size();
if(n==1) return arr\[0\];
// First adjust corner cases
int s = 1, e = arr.size()-2; // 0 1 2 3
if(arr\[1\] != arr\[0\]) return arr\[0\];
if(arr\[n-1\] != arr\[n-2\]) return arr\[n-1\];
while(s\<=e)
{
int mid = s + (e-s)/2;
if(arr\[mid-1\] != arr\[mid\] and arr\[mid+1\] != arr\[mid\])
{
return arr\[mid\];
}
else {
if(arr\[mid+1\] == arr\[mid\])
{
if(mid%2 == 0) s = mid + 1;
else e = mid - 1;
} else {
if(mid%2 != 0) s = mid + 1;
else e = mid - 1;
}
}
}
return -1;
}
};

