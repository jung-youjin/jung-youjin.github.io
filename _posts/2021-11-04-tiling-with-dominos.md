---
layout: post
title: TILING-WITH-DOMINOES
---

3xn 보드에 2x1 도미노로 채우는 방법 구하기!
```
 A_{n} = A_{n-2} + B_{n-1} + C_{n-1}  
 A_{n} = A_{n-2} + 2*(B_{n-1}) 
 B_{n} = A_{n-1} + B_{n-2} 
```

``` cpp

#include <iostream>
using namespace std;
  
int countWays(int n) {
    int A[n + 1], B[n + 1];
    A[0] = 1, A[1] = 0, B[0] = 0, B[1] = 1;
    for (int i = 2; i <= n; i++) {
        A[i] = A[i - 2] + 2 * B[i - 1];
        B[i] = A[i - 1] + B[i - 2];
    }
  
    return A[n];
}
  
int main() {
    int n = 8;
    cout << countWays(n);
    return 0;
}
```
