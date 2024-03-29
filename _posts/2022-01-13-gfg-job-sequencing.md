---
layout: post
title: GFG JOB SEQUENCING
---

Using Greedy!

``` cpp
#include<iostream>
#include<algorithm>

using namespace std;
  
struct Job {
   char id;     // Job Id
   int dead;    // Deadline of job
   int profit;  // Profit if job is over before or on deadline
};

// sorting all jobs according to profit
bool comparison(Job a, Job b) {
     return (a.profit > b.profit);
}
  
// Returns minimum number of platforms required
void printJobScheduling(Job arr[], int n) {
    // Sort all jobs according to decreasing order of profit
    sort(arr, arr+n, comparison);
  
    int result[n]; 
    bool slot[n]; 

    for (int i=0; i<n; i++)
        slot[i] = false;
    for (int i=0; i<n; i++) {
       for (int j=min(n, arr[i].dead)-1; j>=0; j--) {
          if (slot[j]==false) {
             result[j] = i;  // Add this job to result
             slot[j] = true; // Make this slot occupied
             break;
          }
       }
    }
  
    for (int i=0; i<n; i++)
       if (slot[i])
         cout << arr[result[i]].id << " ";
}
  
int main() {
    Job arr[] = { {'a', 2, 100}, {'b', 1, 19}, {'c', 2, 27},
                   {'d', 1, 25}, {'e', 3, 15}};
    int n = sizeof(arr)/sizeof(arr[0]);
    cout << "Following is maximum profit sequence of jobs 
    printJobScheduling(arr, n);
    return 0;
}
```
