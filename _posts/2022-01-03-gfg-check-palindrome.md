---
layout: post
title: CHECK PALINDROME
---

`palindrome` 은 역순으로 읽었을 때도 똑같은 의미를 지닌다는 것이다. 영단어로 예를들면 eye, deed 등의 단어가 있을거다!

``` cpp
#include<iostream>
using namespace std;

bool isKthBitSet(unsigned int x, unsigned int k) {
    return (x & (1 << (k - 1))) ? true : false;
}
 
bool isPalindrome(unsigned int x) {
    int l = 1;
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
