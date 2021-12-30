---
layout: post
title: CHECK FOR POWER OF 4
---

1. 직관적인 방식

``` cpp
bool isPowerOfFour(unsigned int n) {
    int count = 0;
    if ( n && !(n&(n-1)) ) {
        while(n > 1) {
            n >>= 1;
            count += 1;
        }
        return (count%2 == 0)? 1 :0;
    }
    return 0;
}
```

2. bit 특성 이용 접근

``` cpp
#include<bits/stdc++.h>
using namespace std;
 
bool isPowerOfFour(unsigned int n) {
    return n !=0 && ((n&(n-1)) == 0) && !(n & 0xAAAAAAAA);
}
 
int main() {
    int test = 64;
    if (isPowerOfFour(test))
        cout << test << " is a power of 4" ;
    else
        cout << test << " is not a power of 4";
}
```
