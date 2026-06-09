# Kadane's Algorithm Inverted | Minimum Subarray Sum | O(N) | 100% Correct

**Platform:** GeeksForGeeks  
**Date:** 2026-06-09  

## Solution

```
// User function Template for C++

class Solution {
  public:
    int smallestSumSubarray(vector<int>& a) {
        // Code here
        int bestending=a[0];
        int ans=a[0];
        if(a.size()==0)
        return 0;
        if(a.size()==1)
        return a[1];
        
        for(int i=1;i<a.size();i++)
        {
            int c1=a[i];//-4,2,-3,-1
            int c2=a[i]+bestending;//-1,-2,-5,-6
            bestending=min(c1,c2); //-4,-2,-5,-6
            ans=min(ans,bestending);//-4,-4,-5,-6
        }
        return ans;
    }
};

```
