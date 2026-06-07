# find the duplicate number/submissions/2025032445

**Platform:** LeetCode  
**Date:** 2026-06-07  

## Solution

```
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
        if(nums.size()==0||nums.size()==1)
        return -1;
        int slow=0,fast=0;
        while(fast!=nums.size()||nums[fast]!=nums.size()){
            slow=nums[slow];
            fast=nums[fast];
            fast=nums[fast];
            if(slow==fast){
                slow=0;
                while(slow!=fast){
                    slow=nums[slow];
                    fast=nums[fast];
                }
                return slow;
            }
        }
        return -1;
    }
};
```
