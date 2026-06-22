# O(log(n)) SOLUTION:

**Platform:** GeeksForGeeks  
**Date:** 2026-06-22  

## Solution

```
class Solution {
  public:
    int findKRotation(vector<int> &arr) {
        // Code Here
        int n=arr.size();\
        if(n==0)
        return -1;
        if(n==1)
        return 0;
        int low=0,high=n-1,res=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            if(arr[mid]<=arr[n-1])
            {
                res=mid;
                high=mid-1;
                
            }
            else{
                low=mid+1;
            }
        }
        return res ;
    }
};

```
