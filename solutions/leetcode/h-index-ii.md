# h index ii

**Platform:** LeetCode  
**Date:** 2026-06-24  

## Solution

```
class Solution {
public:
bool helper(vector<int>citations,int mid){
    int count=0;
    for(int i=0;i<citations.size();i++){
        if(citations[i]>=mid)
        count++;
    }
    if(count>=mid)
    return true;
    else return false;
}
    int hIndex(vector<int>& citations) {
        int n=citations.size(),mini=INT_MAX,maxi=INT_MIN;
        for(int i=0;i<n;i++){
            mini=min(mini,citations[i]);
            maxi=max(maxi,citations[i]);
        }
        int low=mini,high=maxi,res=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            if(helper(citations,mid)){
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
