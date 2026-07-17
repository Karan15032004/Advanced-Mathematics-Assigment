# minimum number of refueling stops/submissions/2070952290

**Platform:** LeetCode  
**Date:** 2026-07-17  

## Solution

```
class Solution {
public:
    int minRefuelStops(int target, int startFuel, vector<vector<int>>& stations) {
        priority_queue<int>pq;
        sort(stations.begin(),stations.end());
        int i=0,n=stations.size();
        int current=startFuel,res=0;
        while(current<target){
            while(i<n&&current>=stations[i][0]){
                pq.push(stations[i][1]);
                i++;
            }
            if(pq.empty())
            return -1;
            int distance=pq.top();
            pq.pop();
            current+=distance;
            res++;
        }
        return res;
    }
};
```
