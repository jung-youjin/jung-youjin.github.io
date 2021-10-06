---
layout: post
title: GFG-PERMUTATION-COEFFICIENT
---

시간복잡도 `O(n)` study material from **Geeks for Geeks**

``` cpp
#include<bits/stdc++.h>
using namespace std;

int permutationCoeff(int n, int k) {
    int fact[n + 1];
    fact[0] = 1;
 
    for(int i = 1; i <= n; i++)
      fact[i] = i * fact[i - 1];
 
    // P(n,k) = n! / (n - k)!
    return fact[n] / fact[n - k];
}
 
int main() {
    int n = 10, k = 6;
    cout << "Value of P(" << n << ", " << k << ") is: " << permutationCoeff(n, k);
    return 0;
}
```
