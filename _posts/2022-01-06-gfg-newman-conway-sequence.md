---
layout: post
title: GFG NEWMAN CONWAY SEQUENCE
---
```
P(n) = P(P(n - 1)) + P(n - P(n - 1)) 
```

> 1 1 2 2 3 4 4 4 5 6 7 7…
**Recurence Correlation**

``` cpp
#include <bits/stdc++.h>
using namespace std;
 
int sequence(int n) {

    int f[n + 1];
    int i;
    f[0] = 0;
    f[1] = 1;
    f[2] = 1;
 
    for (i = 3; i <= n; i++)
        f[i] = f[f[i - 1]] + f[i - f[i - 1]];   
 
    return f[n];
}
 
int main() {
    int n = 10;
    cout << sequence(n);
    return 0;
}
```
