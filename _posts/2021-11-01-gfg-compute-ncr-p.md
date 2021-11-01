---
layout: post
title: GFG-COMPUTE-nCr%p
---

전에 비슷한 방식을 정석대로 풀다보니, `timeout` 에러가 나거나 `range` 자릿수 추과 에러가 난 적이 있었다. `long long` 활용법과 어떤식으로 식을 풀어서 쉽게 정리할 수 있을지 알아봐야한다.

그러기 위해서는 파스칼의 삼각형 공식을 잊지 않고 있어야 한다!

```
   C(n, r) = C(n-1, r-1) + C(n-1, r)
   C(n, 0) = C(n, n) = 1
```

``` cpp
using namespace std;

long long moduloMultiplication(long long a, long long b, long long mod) {
    long long res = 0;
    a %= mod;
 
    while (b) {
        if (b & 1)  res = (res + a) % mod;
        a = (2 * a) % mod;
        b >>= 1; // b = b / 2
    }
    return res;
}

long long int modInverse(long long int b, long long int m) {
    long long int x, y;
    long long int g = gcdExtended(b, m, &x, &y);

    if (g != 1) return -1;
    return (x % m + m) % m;
}
 
// Euclidean Algorithm (used to find modular inverse)
long long int gcdExtended(long long int a, long long int b,  long long int* x, long long int* y) {
    if (a == 0) {
        *x = 0, *y = 1;
        return b;
    }
 
    long long int x1, y1;
    long long int gcd = gcdExtended(b % a, a, &x1, &y1);
    *x = y1 - (b / a) * x1;
    *y = x1;
    return gcd;
}
 
long long int modDivide(long long int a, long long int b, long long int m) {
    a = a % m;
    long long int inv = modInverse(b, m);
    if (inv == -1) return 0;
    else return (inv * a) % m;
}
 
int nCr(int n, int r, int p) {
    if (r > n) return 0;
    if (r > n - r) r = n - r;
    long long int x = 1;

    for (int i = 1; i <= r; i++) {
        x = moduloMultiplication(x, (n + 1 - i), p);
        x = modDivide(x, i, p);
    }
    return x;
}
 
int main() {
    long long int n = 5, r = 3, p = 1000000007;
    cout << "Value of nCr % p is " << nCr(n, r, p);
    return 0;
}
```
