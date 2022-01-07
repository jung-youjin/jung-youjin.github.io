---
layout: post
title: GFG MOSER DE BRUJIN SEQUENCE
---

해당 시퀀스의 룰

```
1) S(2 * n) = 4 * S(n)
2) S(2 * n + 1) = 4 * S(n) + 1
with S(0) = 0 and S(1) = 1
```

``` cpp
#include <bits/stdc++.h>
using namespace std;

int gen(int n) {
    int S[n+1];
    S[0] = 0;
    S[1] = 1;
    for (int i = 2; i <= n; i++) {   
        // S(2 * n) = 4 * S(n)
        if (i % 2 == 0)
           S[i] = 4 * S[i / 2];
     
        // S(2 * n + 1) = 4 * S(n) + 1
        else
           S[i] = 4 * S[i / 2] + 1;
    }
    return S[n];
}

void moserDeBruijn(int n)  {
    for (int i = 0; i < n; i++)
        cout << gen(i) << " ";
    cout << endl;
}
 
int main() {
    int n = 7;
    cout << "First " << n << " terms of " << "Moser-de Bruijn Sequence : " << endl;
    moserDeBruijn(n);
    return 0;
}
```
