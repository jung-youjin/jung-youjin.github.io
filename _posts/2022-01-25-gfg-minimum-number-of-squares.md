---
layout: post
title: GFG MINIMUM NUMBER OF SQUARES
---

예를들면,
`100 = 10^2 = 5^2 + 5^2 + 5^2 + 5^2` 인데,
이런 식의 minimum number of 제곱을 구해볼 수 있다.
=> recursive 방식

``` cpp
#include <bits/stdc++.h>
using namespace std;

int getMinSquares(unsigned int n) {
    if (sqrt(n) - floor(sqrt(n)) == 0)
        return 1;
    if (n <= 3)
        return n;
        
    int res = n;
    for (int x = 1; x <= n; x++) {
        int temp = x * x;
        if (temp > n)
            break;
        else
            res = min(res, 1 + getMinSquares(n - temp));
    }
    return res;
}
 
int main() {
    cout << getMinSquares(6);
    return 0;
}
```
