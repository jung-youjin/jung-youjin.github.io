---
layout: post
title: GFG-FIBONACCI-NUMBERS
---

`recursion` 이 아닌 `DP`를 활용한 Fibonacci 수열

``` cpp
#include<bits/stdc++.h>
using namespace std;
 
int fib(int n) {
    int f[n + 2];
    int i;

    f[0] = 0;
    f[1] = 1;
 
    for(i = 2; i <= n; i++) {
       f[i] = f[i - 1] + f[i - 2];
    }
    return f[n];
}

int main() {
    int n;
    cin >> n;
    cout << "fibonacci of n:" << fib(n);
    return 0;
}
 
```
