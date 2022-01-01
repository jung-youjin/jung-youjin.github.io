---
layout: post
title: MULTIPLY WITH 7
---

7=2^3-1 을 활용한 간단한 비트 연산 문제

``` cpp
# include<bits/stdc++.h>
using namespace std;

long multiplyBySeven(long n){
    return (n<<3)-n;
}
   
int main() {
    long n = 4; 
    cout<<multiplyBySeven(n); 
    return 0;
}
```
