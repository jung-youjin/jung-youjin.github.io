---
layout: post
title: SCPC6-PRACTICE-NUMBER-OF-INVERSION
---

보자마자 이렇게 풀면 안되는걸 알았는데, 혹시나 수행 시간을 보니 **광탈**이다... 0.000xx초도 이렇게 critical함을 깨닫는다... Number of Inversion을 구하는 가장 대표적인 알고리즘 문제 유형같다... 처음 접해보는 것에 의의를 두자...(^_^);;

inversion 문제를 접근할 수 있는 방법은 크게 3가지다!
1. for loop iteration - 광탈
2. merge sort
3. AVL tree
3. set with upper bound (아직 이해를 못함)

``` c
// TimeLimit Exceed 5.00037초 - 0점
#include <vector>
#include <iostream>

using namespace std;

int Answer;

int main(int argc, char** argv)
{
	int T, test_case;
	setbuf(stdout, NULL);

	cin >> T;
	for(test_case = 0; test_case < T; test_case++)
	{
		Answer = 0;
		
         int N; int num;
         scanf("%d", &N);
         if (N<2 || N>100000) return 0;                   
         vector<int> numbers;
         for (int i=0; i<N; i++) {
             scanf("%d", &num);
             numbers.push_back(num);
         }
         for (vector<int>::iterator it=numbers.begin(); it!=numbers.end(); ++it) 
            for (vector<int>::iterator jt=it; jt!=numbers.end(); ++jt) 
                if (*it>*jt) Answer++;

		/////////////////////////////////////////////////////////////////////////////////////////////
	
        // Print the answer to standard output(screen).
		cout << "Case #" << test_case+1 << endl;
		cout << Answer << endl;

	}

	return 0;//Your program should return 0 on normal termination.
}
```

우선 내가 가장 처음에 냈던 답안...(~~쓰레기 답안~~) 으로 올리지만, 나머지 방법도 내일 한번 구현해봐야겠다! 시간이 늦어서 우선 자야겠다 ;ㅅ; 갈길이 정말 정말 멀었음을 제대로 깨닫는다! 머리 꽝 🔨🔨🔨
