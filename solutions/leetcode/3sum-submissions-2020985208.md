# 3sum/submissions/2020985208

**Platform:** LeetCode  
**Date:** 2026-06-03  

## Solution

```
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        vector<vector<int>> ans;
        for(int i=0;i<nums.size()-2;i++){
            int l=i+1,r=nums.size()-1;
            while(l<r){
                if(nums[l]+nums[r]==-1*nums[i]){
                ans.push_back({nums[i],nums[l],nums[r]});
                r--;
                l++;
                }
                else if(nums[l]+nums[r]<-1*nums[i]){
                    l++;
                }
                else{
                    r++;
                }

            }
            continue;
        }
        return ans;
    }
};
```
