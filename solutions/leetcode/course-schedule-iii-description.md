# course schedule iii/description

**Platform:** LeetCode  
**Date:** 2026-07-17  

## Solution

```
class Solution {
public:
struct cmp{
    bool operator()(pair<int,int>&a,pair<int,int>&b){
        if(a.first!=b.first)
        return a.first>b.first;
        return a.second>b.second;
    }
};
    int scheduleCourse(vector<vector<int>>& courses) {
        priority_queue(pair<int,int>,vector<pair<int,int>>,cmp)      
        int n=courses.size();
        for(int i=0;i<n;i++){
            pq.push({courses[i][1]},{courses[i][0]});
        }
        int res=0;
        int time=0;
        while(!pq.empty()){
            if((time+pq.top().second)<pq.top().first){
                time+=pq.top().second;
                pq.pop();
                res++;
            }
            else
            pq.pop();
        }
        return res;
    }
};
```
