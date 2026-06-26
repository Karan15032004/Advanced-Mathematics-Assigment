# search a 2d matrix ii/submissions/2046914549

**Platform:** LeetCode  
**Date:** 2026-06-26  

## Solution

```
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int n=matrix.size();
        int m=matrix[0].size();
        int i=n-1,j=0;
        while(i>=0&&j<m){
            if(matrix[i][j]==target)
            return true;
            else if(matrix[i][j]>target)
            i-=1;
            else
            j+=1;
        }
        return false;
    }
};
```
