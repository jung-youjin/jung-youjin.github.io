---
layout: post
title: GFG-GOLOMB-SEQUENCE
---

**Golomb sequence** with recursion
```
a(1) = 1 
a(n + 1) = 1 + a(n + 1 – a(a(n)))
```

``` cpp
#include <bits/stdc++.h>
using namespace std;

int findGolomb(int n) {
    if (n == 1) return 1;
        
    return 1 + findGolomb(n - findGolomb(findGolomb(n - 1)));
}
 
void printGolomb(int n) {
    for (int i = 1; i <= n; i++)
        cout << findGolomb(i) << " ";
}

int main() {
    int n = 9;
    printGolomb(n);
    return 0;
}
```
