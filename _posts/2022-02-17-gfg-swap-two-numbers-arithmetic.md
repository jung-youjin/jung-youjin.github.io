---
layout: post
title: GFG SWAP TWO NUMBERS - #1 BIT XOR
---

swapping numbers without temporary variable

``` cpp
#include <bits/stdc++.h>
 
using namespace std;
 
int main() {
    int x = 10, y = 5; // 10=1010, 5=0101
    x = x ^ y; // x now becomes 15 (1111)
    y = x ^ y; // y becomes 10 (1010)
    x = x ^ y; // x becomes 5 (0101)
    cout << "After Swapping: x =" << x << ", y=" << y;
    return 0;
}
```
