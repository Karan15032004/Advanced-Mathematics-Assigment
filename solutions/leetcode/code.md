# Code

**Platform:** LeetCode  
**Date:** 2026-06-23  

## Solution

```
class Solution {
public:
    bool isValid(vector<int>&bloomDay,int m,int k,int mid){
        int c=0,ct=0;
        for(int i=0;i<bloomDay.size();i++){
            if(bloomDay[i]<=mid){
                c++;
            }
            else 
            c=0;
            if(c==k){
             ct++;
             c=0;   
            }
            if(ct==m)
            return true;
        }
        return false;
    }
    int minDays(vector<int>& bloomDay, int m, int k) {
        int min=INT_MAX,max=INT_MIN;
        for(int i=0;i<bloomDay.size();i++){
            if(bloomDay[i]<min)
            min=bloomDay[i];
            if(bloomDay[i]>max)
            max=bloomDay[i];
        }
        int low=min;
        int high=max,ans=-1;
        while(low<=high){
            int mid=(low+high)/2;
            if(isValid(bloomDay,m,k,mid)){
                ans=mid;
                high=mid-1;
            }
            else
            low=mid+1;

        }
        return ans;
    }
};
```
