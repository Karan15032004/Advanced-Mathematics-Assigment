# interval list intersections/submissions/2033765088

**Platform:** LeetCode  
**Date:** 2026-06-15  

## Solution

```
class Solution {
public:
    vector<vector<int>> intervalIntersection(vector<vector<int>>& firstList, vector<vector<int>>& secondList) {
        int n=firstList.size(),m=secondList.size();
        int i=0,j=0;
        if(n==0||m==0)
        return {};
        vector<vector<int>>ans;
        while(i<n&&j<m){
            int start1=firstList[i][0],end1=firstList[i][1];
            int start2=secondList[j][0],end2=secondList[j][1];
            if(end2>=start1&&start2<=end1){
                ans.push_back({max(start1,start2),min(end1,end2)});
                if(end2==end1)
                {
                    i++;
                    j++;
                }
                else if(end2>end1)
                i++;
                else
                j++;
            }
            else{
                if(end2>end1)
                i++;
                else
                j++;
            }
        }
        return ans;
    }
};
```
