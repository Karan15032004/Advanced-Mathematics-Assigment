# search a 2d matrix/submissions/2046189903

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
        int i=0;
        
        int low=0,high=n-1,res=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
           if(matrix[mid][0]<target){
            res=mid;
            low=mid+1;
           }
          else if(matrix[mid][0]==target)
          return true;
          else 
          high=mid-1;
        }
        if(res!=-1)
        return binarysearch(matrix[res],target);
        else
        return false;
        }
    };
```
