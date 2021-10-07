---
layout: post
title: GFG-TILING-PROBLEM
---

Number of ways to place 2x1 size tiles in 2xn size board using `DP`

- Basic theory
```
 count(n) = n if n = 1 or n = 2 
 count(n) = count(n-1) + count(n-2)
```

``` cpp
#include <iostream>
using namespace std;
 
int getNoOfWays(int n){
    if (n == 0)
        return 0;
    if (n == 1)
        return 1;

    return getNoOfWays(n - 1) + getNoOfWays(n - 2);
}

int main() { 
    int n;
    cin >> n;
    cout << getNoOfWays(n) << endl;
    return 0;
}
```
