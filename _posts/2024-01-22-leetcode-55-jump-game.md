---
layout: post
title: BOJ-2750
---

1. Iterate from the beginning
   
```c
bool canJump(vector<int>& nums) {
    int pivot = nums[0];
    bool result = true;
    if (nums.size() == 1) return true;
    if (nums[0] == 0) return false;
    for (int i = 1; i < nums.size(); i++) {
        pivot--;
        if (nums[i] >= pivot) pivot = nums[i];
        if (nums[i] == 0 && pivot == 0 && i != nums.size() - 1) {
            result = false;
            break;
        }
    }
    return result;
}
```

2. Iterate from the back (my solution)
Sum up the element's index and element value to determine if it satisifies the condition

```c
bool canJump(vector<int>& nums) {
    int last_index = nums.size() - 1;
    if (nums.size() == 1) return true;
    for (int i = nums.size() - 1; i >= 0; --i)
        if (i + nums[i] >= last_index) last_index = i;
    if (last_index == 0) return true;
    else return false;
}
```
