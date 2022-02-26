---
layout: post
title: GFG RUSSIAN PEASANT
---

``` cpp
#include <iostream>
using namespace std;
 
// A method to multiply two numbers using Russian Peasant method
unsigned int russianPeasant(unsigned int a, unsigned int b) {
    int res = 0;
    while (b > 0) {
        if (b & 1)
            res = res + a;
        a = a << 1;
        b = b >> 1;
    }
    return res;
}
 
int main() {
    cout << russianPeasant(18, 1) << endl;
    cout << russianPeasant(20, 12) << endl;
    return 0;
}
```
