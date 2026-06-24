# maximum candies allocated to k children/submissions/2044366952

**Platform:** LeetCode  
**Date:** 2026-06-24  

## Solution

```
class Solution {
public:
bool helper(vector<int>candies,long long k,long long mid){
    int count=0;
    for(int i=0;i<candies.size();i++){
        count+=candies[i]/mid;
    }
    if(count>=k)
    return true;
    else 
    return false;
}
    int maximumCandies(vector<int>& candies, long long k) {
        int maxi=INT_MIN;
        long long low=1,high=maxi,res=0;
        while(low<=high){
            long long mid=low+(high-low)/2;
            if(helper(candies,k,mid))
            {
                res=mid;
                low=mid+1;
            }
            else
            high=mid-1;
        }
        return res;
    }
};
```
