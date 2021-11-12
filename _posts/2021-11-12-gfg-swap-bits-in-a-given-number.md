---
layout: post
title: GFG-SWAP-BITS-IN-A-GIVEN-NUMBER
---

``` cpp
#include <iostream>
using namespace std;
 
int swapBits(unsigned int num, unsigned int p1, unsigned int p2, unsigned int n) {
    int shift1, shift2, value1, value2;
    while (n--) {
        shift1 = 1 << p1;
        shift2 = 1 << p2;
 
        value1 = ((num & shift1));
        value2 = ((num & shift2));
 
        if ((!value1 && value2) || (!value2 && value1)) {
            if (value1) {
                num = num & (~shift1);
                num = num | shift2;
            }
            else {
                num = num & (~shift2);
                num = num | shift1;
            }
        }
        p1++;
        p2++;
    }
    return num;
}
 
int main() {
    int res = swapBits(28, 0, 3, 2);
    cout << "Result = " << res;
    return 0;
}
```
