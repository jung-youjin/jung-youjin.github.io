---
layout: post
title: ROTATE-BITS
---

FW 단에서 중요한 bit shifting strategy

```
#include <bits/stdc++.h>
using namespace std;
 
#define SHORT_SIZE 16

unsigned short leftRotate(unsigned short x, short d) {
    return (x << d) | (x >> (SHORT_SIZE - d));
}
 
unsigned short rightRotate(unsigned short x, short d) {
    return (x >> d) | (x << (SHORT_SIZE - d));
}

int main() {
    unsigned short n = 28;
    short d = 2;
 
    cout << leftRotate(n, d) << endl;
    cout << rightRotate(n, d) << endl;
 
    return 0;
}
```
