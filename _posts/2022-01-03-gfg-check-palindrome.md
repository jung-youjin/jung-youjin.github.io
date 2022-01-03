---
layout: post
title: CHECK PALINDROME
---

``` cpp
#include<iostream>
using namespace std;

bool isKthBitSet(unsigned int x, unsigned int k) {
    return (x & (1 << (k - 1))) ? true : false;
}
 
bool isPalindrome(unsigned int x) {
    int l = 1; // Initialize left position
    int r = sizeof(unsigned int) * 8;
    while (l < r) {
        if (isKthBitSet(x, l) != isKthBitSet(x, r))
            return false;
        l++; r--;
    }
    return true;
}

int main() {
    unsigned int x = 1 << 15 + 1 << 16;
    cout << isPalindrome(x) << endl;
    x = 1 << 31 + 1;
    cout << isPalindrome(x) << endl;
    return 0;
}
```
