---
layout: post
title: GFG CHECK INTEGER OVERFLOW
---

``` cpp
#include <bits/stdc++.h>

using namespace std;

int addOvf(int* result, int a, int b) {
    *result = a + b;
    if(a > 0 && b > 0 && *result < 0)
        return -1;
    if(a < 0 && b < 0 && *result > 0)
        return -1;
    return 0;
}

int main() {
    int *res = new int[(sizeof(int))];
    int x = 2147483640;
    int y = 10;
 
    cout << addOvf(res, x, y);
 
    cout << endl << *res;
    return 0;
}
```
