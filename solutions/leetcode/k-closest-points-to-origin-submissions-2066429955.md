# k closest points to origin/submissions/2066429955

**Platform:** LeetCode  
**Date:** 2026-07-13  

## Solution

```
    class Solution {
    public:
    int finddist(vector<int>a){
        return sqrt(a[0]*a[0]+a[1]*a[1]);
    }
    struct cmp{
        bool operator()(pair<int,int>&a,pair<int,int>&b){
            if(a.first!=b.first)
            return a.first<b.first;
            return a.second<b.second;
        }
    };
        vector<vector<int>> kClosest(vector<vector<int>>& points, int k) {
            unordered_map<int,int>f;
            priority_queue<pair<int,int>,vector<pair<int,int>>,cmp>p;
            for(int i=0;i<points.size();i++){
                f[i]=finddist(points[i]);
            }
            int count=0;
            for(auto it:f){
                if(count<k){
                p.push({it.second,it.first});
                count++;
                continue;
                }
                p.push({it.second,it.first});
                p.pop();
                count++;
            }       
            vector<vector<int>>ans;
            while(!p.empty()){
                ans.push_back(points[p.top().second]);
                p.pop();
            } 
            return ans;}
        };

```
