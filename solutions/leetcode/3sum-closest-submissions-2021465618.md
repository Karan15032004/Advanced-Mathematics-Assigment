# 3sum closest/submissions/2021465618

**Platform:** LeetCode  
**Date:** 2026-06-03  

## Solution

```
class Solution {
public:
    int threeSumClosest(vector<int>& nums, int target) {
        sort(nums.begin(),nums.end());
        int diff=INT_MAX,ans_sum;
        for(int i=0;i<nums.size()-2;i++){
            int l=i+1,r=nums.size()-1;
            while(l<r){
                int sum=nums[i]+nums[l]+nums[r];
                if(abs(sum-target)<diff){
                    diff=abs(sum-target);
                    ans_sum=sum;
                }
                if(sum<target){
                    l++;
                }
                else if(sum>target)
                r--;
                else
                return sum;
            }
            continue;
        }
        return ans_sum;
    }
};
```
