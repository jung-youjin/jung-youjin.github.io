---
layout: post
title: GFG NEXT POWER OF TWO
---

``` cpp
#include <bits/stdc++.h>
using namespace std;
 
unsigned int nextPowerOf2(unsigned int n) {
    unsigned count = 0;
    if (n && !(n & (n - 1)))
        return n;
     
    while( n != 0) {
        n >>= 1;
        count += 1;
    }
     
    return 1 << count;
}
 
int main() {
    unsigned int n = 0;
    cout << nextPowerOf2(n);
    return 0;
}
```
