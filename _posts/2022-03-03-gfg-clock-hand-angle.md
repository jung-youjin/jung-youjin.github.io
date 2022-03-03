---
layout: post
title: GFG CLOCK HAND ANGLE
---

시침과 분침 사이의 각도 재기! 📐

``` cpp
#include <bits/stdc++.h>
using namespace std;
 
int min(int x, int y) {
    return (x < y)? x: y;
     
}
 
int calcAngle(double h, double m) {
    if (h <0 || m < 0 || h >12 || m > 60)
        printf("Wrong input");
 
    else if (h == 12) h = 0;
    else if (m == 60) {
      m = 0;
      h += 1;
      if(h>12) h = h-12;
     }

    float hour_angle = 0.5 * (h * 60 + m);
    float minute_angle = 6 * m;
    float angle = abs(hour_angle - minute_angle);
    angle = min(360 - angle, angle);
 
    return angle;
}
 
int main() {
    cout << calcAngle(9, 60) << endl;
    cout << calcAngle(3, 30) << endl;
    return 0;
}
```
