# last stone weight/submissions/2067481328

**Platform:** LeetCode  
**Date:** 2026-07-14  

## Solution

```
class Solution {
public:
    int lastStoneWeight(vector<int>& stones) {
        priority_queue<int>pq;
        for(int i=0;i<stones.size();i++)
        pq.push(stones[i]);
        while(!pq.empty()){
            int p1=pq.top();
            pq.pop();
            if(pq.empty())
            return p1;
            int p2=pq.top();
            pq.pop();
            if(p1==p2)
            continue;
            else 
            pq.push(abs(p1-p2));
        }
        return 0;
    }
};
```
