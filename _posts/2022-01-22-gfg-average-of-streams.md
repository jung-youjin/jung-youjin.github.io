 ---
 layout: post
 title: GFG AVERAGE OF STREAMS
 ---
 
 ``` cpp
 #include <iostream>
 
using namespace std;
 
float getAvg(float prev_avg, int x, int n) {
    return (prev_avg * n + x) / (n + 1);
}
 
void streamAvg(float arr[], int n) {
    float avg = 0;
    for (int i = 0; i < n; i++) {
        avg = getAvg(avg, arr[i], i);
        cout <<"Average of " <<i+1 << " numbers is " << avg << endl;
    }
    return;
}

int main() {
    float arr[] = { 10, 20, 30, 40, 50, 60, 70, 80, 90 };
    int n = sizeof(arr) / sizeof(arr[0]);
    streamAvg(arr, n);
    return 0;
}
```
