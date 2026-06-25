# split array largest sum/submissions/2046119754

**Platform:** LeetCode  
**Date:** 2026-06-25  

## Solution

```
class Solution {
public:
  bool splits(vector<int>&nums,int k,int ans){
    int s=0,st=1;
    for(int i=0;i<nums.size();i++){
      if(s+nums[i]<=ans)
      s+=nums[i];
      else{
        s=nums[i];
        st++;
        if(st>k)
        return false;
      }
    }
    return true;
  }
    int splitArray(vector<int>& nums, int k) {
        int max=INT_MIN,sum=0;
        for(int i=0;i<nums.size();i++){
          sum+=nums[i];
          if(nums[i]>max)
          max=nums[i];
       }
       if(k==1)
       return sum;
       if(k==nums.size())
       return max;
       int low=max,high=sum,res=-1;
       while(low<=high){
        int mid=(low+high)/2;
        if(!splits(nums,k,mid))
        low=mid+1;
        else{
            res=mid;
        high=mid-1;
        }
       }
       return res;
    }
};
```
