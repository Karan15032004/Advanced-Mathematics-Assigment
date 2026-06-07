# Why the input number cannot go to infinity (an explanation/proof that fits the context of a technical interview)

**Platform:** LeetCode  
**Date:** 2026-06-07  

## Solution

```
class Solution {
public:
    int funsum(int N){
        int sum=0;
        while(N!=0){
            int d=N%10;
            sum+=d*d;
            N/=10;
        }
        return sum;
    }
    bool isHappy(int n) {
        int slow=n,fast=n;
        while(fast!=1){
            slow=funsum(slow);
            fast=funsum(fast);
            fast=funsum(fast);
            if(slow==fast&&slow!=1){
                return false;
            }
        }
        return true;
    }
    };

```
