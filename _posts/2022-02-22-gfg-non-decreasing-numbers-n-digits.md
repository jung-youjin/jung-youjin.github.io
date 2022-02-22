---
layout: post
title: GFG NON DECREASING NUMBERS OF N DIGITS
---

``` cpp
#include<bits/stdc++.h>

using namespace std;
 
long long int countNonDecreasing(int n) {
    memset(dp, 0, sizeof dp);

    for (int i = 0; i < 10; i++)
        dp[i][1] = 1;
 
    // Fill the table in bottom-up manner
    for (int digit = 0; digit <= 9; digit++) {
        for (int len = 2; len <= n; len++) {
            for (int x = 0; x <= digit; x++)
                dp[digit][len] += dp[x][len-1];
        }
    }
 
    long long int count = 0;
    for (int i = 0; i < 10; i++)
        count += dp[i][n];
 
    return count;
}

int main() {
    int n = 3;
    cout << countNonDecreasing(n);
    return 0;
}
```
