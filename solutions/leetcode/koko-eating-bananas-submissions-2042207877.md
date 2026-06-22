# koko eating bananas/submissions/2042207877

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class Solution {
public:
    int helper(vector<int>piles,int h,int speed){
        int time=0,n=piles.size();
        int i=0;
        while(i<n){
            int el=piles[i];
            while(el>0){
                el-=speed;
                time++;
            }
            i++;
        }
        return time;
    }
    int minEatingSpeed(vector<int>& piles, int h) {
        int mini=piles[0],maxi=piles[0];
        for(int i=1;i<piles.size();i++){
            mini=min(mini,piles[i]);
            maxi=max(maxi,piles[i]);
        }
        int n=piles.size();
        if(n==h)
        return maxi;
        int low=1,high=maxi,k=mini,res=-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            k=helper(piles,h,mid);//4,
            if(k==h){
                res=mid;
                high=mid-1;
            }
            else if(k>h){
                low=mid+1;
            }
            else
            high=mid-1;
        }
        return res;
    }
};
```
