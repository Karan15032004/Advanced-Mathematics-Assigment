# container with most water/submissions/2053470950

**Platform:** LeetCode  
**Date:** 2026-07-02  

## Solution

```
class Solution {
public:
    int maxArea(vector<int>& height) {
        int ans=0,i=0,n=height.size(),j=n-1;
        while(i<j){
            ans=max(ans,(j-i)*min(height[i],height[j]));
            if(height[j]>height[i])
            i++;
            else j--;
        }
        return ans;
    }
};
```
