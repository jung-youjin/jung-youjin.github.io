---
layout: post
title: GFG-BINOMIAL-COEFFICIENT
---

Study log of Binomial Coeffiecent using memoization method technique from Geeks for Geeks `DP`

``` cpp
#include <bits/stdc++.h>
using namespace std;

int binomialCoeffUtil(int n, int k, int** dp) {
    if (dp[n][k] != -1)
        return dp[n][k];
    if (k == 0) {
        dp[n][k] = 1;
        return dp[n][k];
    }
    if (k == n) {
        dp[n][k] = 1;
        return dp[n][k];
    }
    dp[n][k] = binomialCoeffUtil(n - 1, k - 1, dp) + binomialCoeffUtil(n - 1, k, dp);
    return dp[n][k];
}
 
int binomialCoeff(int n, int k) {
    int** dp;
    dp = new int*[n + 1];
 
    for (int i = 0; i < (n + 1); i++) {
        dp[i] = new int[k + 1];
    }

    for (int i = 0; i < (n + 1); i++) {
        for (int j = 0; j < (k + 1); j++) {
            dp[i][j] = -1;
        }
    }
    return binomialCoeffUtil(n, k, dp);
}

int main() {
    int n = 5, k = 2;
    cout << "Value of C(" << n << ", " << k << ") is "
         << binomialCoeff(n, k) << endl;
    return 0;
}
```

First day of internship!🐻

![yay](https://c.tenor.com/DAEpv02_u8EAAAAC/first-day-jonah-hill.gif)

![yay](https://i.imgur.com/ICmJCIY.gif)

![yay](https://c.tenor.com/YwnmxTFUkkIAAAAM/internship-intern.gif)

![yay](https://qrter.com/assets/Uploads/gif-1.gif)
