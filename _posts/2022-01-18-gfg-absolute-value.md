---
layout: post
title: GFG ABSOLUTE VALUE
---

`abs` 함수 없이 비트 성질로 절대값 취하기!

``` cpp
#include <bits/stdc++.h>
using namespace std;
#define CHARBIT 8
 
unsigned int getAbs(int n) {
    int const mask = n >> (sizeof(int) * CHARBIT - 1);
    return ((n + mask) ^ mask);
}

int main() {
    int n = -6;
    cout << "Absolute value of " << n << " is " << getAbs(n);
    return 0;
}
```
