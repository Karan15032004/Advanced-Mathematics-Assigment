# kth smallest number in multiplication table/description

**Platform:** LeetCode  
**Date:** 2026-06-27  

## Solution

```
class Solution {
public:
int no_greater(vector<vector<int>>matrix,int mid,int m,int n){
    int i=m-1,j=0,c=0;
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
    int findKthNumber(int m, int n, int k) {
        vector<vector<int>>matrix(m,vector<int>(n));
        for(int i=0;i<m;i++){
            for(int j=0;j<n;j++){
                matrix[i+1][j+1]=(i+1)*(j*1);
            }
        }
        int low=1,high=m*n,res=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            if(no_greater(matrix,mid,m,n)<k)
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
