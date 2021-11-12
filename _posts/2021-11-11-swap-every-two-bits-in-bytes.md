---
layout: post
title: SWAP-EVERY-TWO-BITS-IN-BYTES
---

``` cpp
#include<bits/stdc++.h>
using namespace std;
 
unsigned int swapBitsInPair(unsigned int x) {
    return ((x & 0b10101010) >> 1) |
            ((x & 0b01010101) << 1);   
}
 
int main() {
    unsigned int x = 4;
    cout << swapBitsInPair(x);   
    return 0;
}
```
