# 4sum/submissions/2021513755

**Platform:** LeetCode  
**Date:** 2026-06-03  

## Solution

```
class Solution {
public:
    vector<vector<int>> fourSum(vector<int>& nums, int target) {
        if(nums.size()<=3)
        return {};
        vector<vector<int>>ans;
        sort(nums.begin(),nums.end());
        for(int i=0;i<nums.size()-3;i++){
            while(i>0&&nums[i]==nums[i-1]&&i<nums.size()-3)
            i++;
            for(int j=i+1;j<nums.size()-2;j++){
                while(j>1&&nums[j]==nums[j-1]&&j<nums.size()-2)
                j++;
                int l=j+1,r=nums.size()-1;
                while(l<r){
                    int sum=nums[i]+nums[j]+nums[l]+nums[r];
                    if(sum<target)
                    l++;
                    else if(sum>target)
                    r--;
                    else{
                        ans.push_back({nums[i],nums[j],nums[l],nums[r]});
                        l++;
                        r--;
                        while(l<nums.size()&&nums[l]==nums[l-1])
                        l++;
                        while(r>=0&&nums[r]==nums[r+1])
                        r--;
                    }
                }
                continue;
            }
        }
        return ans;
    }
};
```
