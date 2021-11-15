---
layout: post
title: GFG-FLOOR-IN-SORTED-ARRAY
---

``` cpp
#include <iostream>
using namespace std;

int floorSearch(int arr[], int n, int x) {
    if (x >= arr[n - 1])
        return n - 1;
 
    if (x < arr[0])
        return -1;

    for (int i = 1; i < n; i++)
        if (arr[i] > x)
            return (i - 1);
 
    return -1;
}
 
int main() {
    int arr[] = { 1, 2, 4, 6, 10, 12, 14 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int x = 7;
    int index = floorSearch(arr, n - 1, x);
    if (index == -1)
        cout<<"Floor of "<<x <<" doesn't exist in array ";
    else
        cout<<"Floor of "<< x <<" is " << arr[index];
    return 0;
}
```
