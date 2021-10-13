---
layout: post
title: GFG-FRIENDS-PAIRING
---

```
f(n) = ways n people can remain single 
       or pair up.

For n-th person there are two choices:
1) n-th person remains single, we recur 
   for f(n - 1)
2) n-th person pairs up with any of the 
   remaining n - 1 persons. We get (n - 1) * f(n - 2)

Therefore we can recursively write f(n) as:
f(n) = f(n - 1) + (n - 1) * f(n - 2)
```

``` cpp
#include <bits/stdc++.h>

using namespace std;

int countFriendsPairings(int n) {
    int dp[n + 1];
    
    for (int i = 0; i <= n; i++) {
        if (i <= 2)
            dp[i] = i;
        else
            dp[i] = dp[i - 1] + (i - 1) * dp[i - 2];
    }
 
    return dp[n];
}

int main() {
    int n = 7;
    cout << countFriendsPairings(n) << endl;
    return 0;
}
```
