---
layout: post
title: GFG SWAP TWO NUMBERS - #2 ARITHMETIC
---

``` cpp
#include <bits/stdc++.h>

using namespace std;
 
int main() {
    int x = 10, y = 5;
    x = x + y; // x now becomes 15
    y = x - y; // y becomes 10
    x = x - y; // x becomes 5
    cout << "After Swapping: x =" << x << ", y=" << y;
}
```
