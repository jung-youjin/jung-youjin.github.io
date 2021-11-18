 ---
 layout: post
 title: GFG-SMALLEST-OF-THREE
 ---
 
 using bit operations!
 
 ``` cpp
#include <bits/stdc++.h>
using namespace std;

int smallest(int x, int y, int z) {
    int c = 0;
    while (x && y && z) {
        x--;
        y--;
        z--;
        c++;
    }
    return c;
}

int main() {
    int x = 12, y = 15, z = 5;
    cout << "Minimum of 3 numbers is " << smallest(x, y, z);
    return 0;
}
```
