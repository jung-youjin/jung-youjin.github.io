---
layout: post
title: GFG FINDING NUMBER OF WAYS TO CONSTRUCT BUILDING
---

> modify for deploy fix

```
Let countB(i) be count of possible ways with i sections
              ending with a building.
    countS(i) be count of possible ways with i sections
              ending with a space.

// A space can be added after a building or after a space.
countS(N) = countB(N-1) + countS(N-1)

// A building can only be added after a space.
countB[N] = countS(N-1)

// Result for one side is sum of the above two counts.
result1(N) = countS(N) + countB(N)

// Result for two sides is square of result1(N)
result2(N) = result1(N) * result1(N) 
```

주어진 예시 조건에 맞게 구할 수 있는 방법의 갯수를 구한다...


``` cpp
#include<iostream>

using namespace std;

int countWays(int N) {
    if (N == 1) return 4;  // 2 for one side and 4 for two sides
    int countB=1, countS=1, prev_countB, prev_countS;
    for (int i=2; i<=N; i++) {
        prev_countB = countB;
        prev_countS = countS;
        countS = prev_countB + prev_countS;
        countB = prev_countS;
    }
    return ((countS + countB)*(countS + countB));
}

int main() {
    int N = 3;
    cout << "Count of ways for " << N << " sections is " << countWays(N);
    return 0;
}
```
