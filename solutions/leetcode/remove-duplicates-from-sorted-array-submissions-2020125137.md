# remove duplicates from sorted array/submissions/2020125137

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if(nums.size()==0)
        return 0;
        if(nums.size()==1)
        return 1;
        int c=1;
        int i=0,j=1;
        while(j<nums.size()){
            if(nums[j]==nums[j-1]){
                j++;
            }
            else{
                c++;
                nums[++i]=nums[j];
                j++;
            }
        }
        return c;

    }
};
```
