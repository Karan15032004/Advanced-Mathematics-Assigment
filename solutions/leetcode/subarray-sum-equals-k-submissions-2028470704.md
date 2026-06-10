# subarray sum equals k/submissions/2028470704

**Platform:** LeetCode  
**Date:** 2026-06-10  

## Solution

```
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        int sum=0,c=0;
        unordered_map<int,int>f;
        f[0]=1;
        for(int i=0;i<nums.size();i++){
            sum+=nums[i];
            int q=sum-k;
            int freq=f[q];
            c+=freq;
            f[sum]++;
        }
        return c;
    }
};
```
