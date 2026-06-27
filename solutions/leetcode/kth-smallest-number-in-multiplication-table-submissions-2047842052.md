# kth smallest number in multiplication table/submissions/2047842052

**Platform:** LeetCode  
**Date:** 2026-06-27  

## Solution

```
class Solution {
public:
int helper(int m,int n,int mid){
    int i=m,j=1,c=0;
    while(i>0&&j<=n){
        int target=i*j;
        if(target<=mid){
        c+=i;
        j++;
        }
        else
        i--;
    }
    return c;
    }
    int findKthNumber(int m, int n, int k) {
        int low=1,high=m*n,res=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            if(helper(m,n,mid)<k)
            low=mid+1;
            else
            {
                res=mid;
                high=mid-1;
            }
        }
        return res;
    }
};
```
