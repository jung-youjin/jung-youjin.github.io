---
layout: post
title: REVERSE-BITS-STANDARD
---

`C`를 이용한 Bit reversion

``` C 
#include <bits/stdc++.h>

unsigned int reverseBits(unsigned int num) {
    unsigned int  NO_OF_BITS = sizeof(num) * 8;
    unsigned int reverse_num = 0, i, temp;
  
    for (i = 0; i < NO_OF_BITS; i++) {
        temp = (num & (1 << i));
        if(temp)
            reverse_num |= (1 << ((NO_OF_BITS - 1) - i));
    }
   
    return reverse_num;
}
  
int main() {
    unsigned int x = 2; 
    printf("%u", reverseBits(x));
    getchar();
}
```
