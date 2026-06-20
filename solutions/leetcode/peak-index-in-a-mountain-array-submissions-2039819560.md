# peak index in a mountain array/submissions/2039819560

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    int peakIndexInMountainArray(vector<int>& arr) {
        int n=arr.size(),low=0,high=n-1,res=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            if(arr[mid]>arr[mid+1]){
                    res=mid;
                    high=mid-1;
            }
            else
            low=mid+1;
        }
        return res;
    }
};
```
