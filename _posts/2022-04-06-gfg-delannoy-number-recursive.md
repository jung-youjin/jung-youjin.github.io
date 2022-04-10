---
layout: post
title: GFG DELANNOY NUMBER (RECURSIVE)
---

``` cpp
#include <bits/stdc++.h>

using namespace std;
 
int dealnnoy(int n, int m) {
    if (m == 0 || n == 0)
        return 1;
 
    return dealnnoy(m - 1, n) + dealnnoy(m - 1, n - 1) + dealnnoy(m, n - 1);
}
 
int main() {
    int n = 3, m = 4;
    cout << dealnnoy(n, m) << endl;
    return 0;
}
```
