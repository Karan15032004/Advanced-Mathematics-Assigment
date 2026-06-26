# Kth Smallest Element in a Sorted Matrix

**Platform:** LeetCode  
**Date:** 2026-06-26  

## Solution

```
class Solution {
public:
int no_greater(vector<vector<int>>matrix,int mid){
    int n=matrix.size();
    int i=n-1,j=0,c=0;
    while(i>=0&&j<n){
        if(matrix[i][j]<=mid){
            c+=(i+1);
            j++;
        }
        else
        i--;
    }
    return c;
}
    int kthSmallest(vector<vector<int>>& matrix, int k) {
    int n=matrix.size();
    
    int low=matrix[0][0],high=matrix[n-1][n-1],res=-1;
    while(low<=high){
        int mid=low+(high-low)/2;
        if(no_greater(matrix,mid)<k)
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
