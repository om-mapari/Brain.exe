
class Solution {
public:
  vector\<int\> frequencySort(vector\<int\>& nums) {
    unordered_map\<int,int\> um;
    *for*(auto i: nums) um\[i\]++;
    sort(nums.begin(),nums.end(),==\[&\](int a,int b)=={
      *return* um\[a\]==um\[b\]? a\>b : um\[a\]\<um\[b\];
    });
    *return* nums;
  }
};

that a & b consider that a comes before b in sorted

![image1](../../resources/cec3f180f0244da69a880f436392a9b7.png)

