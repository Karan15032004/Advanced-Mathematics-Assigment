# search a 2d matrix/submissions/2046140283

**Platform:** LeetCode  
**Date:** 2026-06-25  

## Solution

```
class Solution {
public:
bool binarysearch(vector<int>matrix,int target){
    int low=0,high=matrix.size()-1;
    while(low<=high){
        int mid=low+(high-low)/2;
        if(matrix[mid]==target)
        return true;
        else if(matrix[mid]>target)
        high=mid-1;
        else
        low=mid+1;
    }
    return false;
}
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int n = matrix.size();      // Number of rows
       int m = matrix[0].size();   // Number of columns
        for(int i=0;i<n;i++){
            if(binarysearch(matrix[i],target))
            return true;
            else 
            continue;
        }
        return false;
    }
};
```
