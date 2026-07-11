# Intuition

**Platform:** LeetCode  
**Date:** 2026-07-11  

## Solution

```
class Solution {
public:
    struct cmp{
        bool operator()(pair<int,int>&a,pair<int,int>&b){
            if(a.first==b.first)
            return a.second>b.second;
            return a.first>b.first;
        }
    };
    vector<int> topKFrequent(vector<int>& nums, int k) {
        unordered_map<int, int> freq;
        // Count frequencies
        for (int& num : nums)
            freq[num]++; // Increment frequency count for each number
        
        priority_queue<pair<int,int>,vector<pair<int,int>>,cmp>pq;
        for(auto i:freq){
            int el=i.first;
            int f=i.second;
            if(pq.size()<k)
            pq.push({f,el});
            else{
                if(f>pq.top().first){
                    pq.push({f,el});
                    pq.pop();
                }
                else continue;
            }
        }
        vector<int> res;
        while(!pq.empty()){
            res.push_back(pq.top().second);
            pq.pop();
        }
        return res;
    }
};
```
