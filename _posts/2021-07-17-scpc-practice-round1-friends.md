---
layout: post
title: SCPC-PRACTICE-ROUND1-FRIENDS.md
---

Recursion을 사용해 아주 느린 코드... 🤦🏼‍♀️🤦🏼‍♀️

``` cpp
#include <iostream>

using namespace std;

int Answer, N;

void collect(int* arr, int* cmp, int j) {
    int i = arr[j];
    cmp[j] = 0;
    if (i+j>N) return;
    else if (cmp[i+j]==0) {
        Answer--;
        return;
    }
    else if (i<=N) {
        collect(arr, cmp, i+j);
    }
    else return;
}

int main(int argc, char** argv)
{
	int T, test_case;
    setbuf(stdout, NULL);
	
	cin >> T;
	for(test_case = 0; test_case  < T; test_case++)
	{

		Answer = 0;
		/////////////////////////////////////////////////////////////////////////////////////////////
        cin >> N;
        int *arr = new int[N+1];
        int *cmp = new int[N+1];
        arr[0] = 0; cmp[0] = 0;
        for (int i=1; i<=N; i++) {
            int num;
            cin >> num;
            if (num<=0 || num>N) return 0;
            else {
                arr[i] = num;
                cmp[i] = num;
            }
        }

        for (int i=1; i<=N; i++) {
            if (cmp[i]==0) continue;
            else {
                collect(arr, cmp, i);
                Answer++;
            }
        }
		/////////////////////////////////////////////////////////////////////////////////////////////
		
		// Print the answer to standard output(screen).
		cout << "Case #" << test_case+1 << endl;
		cout << Answer << endl;
        delete[] arr;
        delete[] cmp;
	}

	return 0;//Your program should return 0 on normal termination.
}
```

![image](https://user-images.githubusercontent.com/37402072/126030166-058528a0-d6e0-493b-acbe-821106e9d978.png)

오늘 3시까지 마감이었던 예선이었는데 깜빡하고 오늘 1시쯤 시작해서 한문제밖에 못 풀었다... 성능/테크닉 관점에서 고려도 못한채, 아직까진 실력이 부족하다는 것을 느끼고, 앞으로 체계적으로 난이도 있는 문제 위주로 공부를 시작해야겠다.