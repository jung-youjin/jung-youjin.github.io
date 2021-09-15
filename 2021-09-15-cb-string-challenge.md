---
layout: post
title: CODERBYTE STRING CHALLENGE
---

``` cpp
#include <iostream>
#include <string>
#include <queue>
#include <utility>
#include <math.h>
#include <sstream>
using namespace std;

int NumDigits(int x) {  
    x = abs(x);  
    return (x < 10 ? 1 :   
        (x < 100 ? 2 :   
        (x < 1000 ? 3 :   
        (x < 10000 ? 4 :   
        (x < 100000 ? 5 :   
        (x < 1000000 ? 6 :   
        (x < 10000000 ? 7 :  
        (x < 100000000 ? 8 :  
        (x < 1000000000 ? 9 :  
        10)))))))));  
}

string StringChallenge(string str) {
  queue<pair<string, int>> q;
  queue<int> nq;
  string listNum[12] = {"zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "plus", "minus"};
  string word;
  int num = 0;
  int resultNum;
  string result;
  for (int i=0; i<str.length(); i++) {
    word.push_back(str[i]);
    for (int j=0; j<12; j++) {
      if (/*!word.compare(listNum[i])*/word==listNum[j]) {
        q.push(make_pair(word, j));
        word = "";
        break;
      }
    }
  }
  while (!q.empty()) {
    // int num1 = q.front().second;
    // while (!(q.front().second==10 || q.front().second==11)) {
    //   cout << q.front().second << endl;
    //  q.pop();
    // }
    nq.push(q.front().second);
    q.pop();
    if (q.front().second == 10 || q.front().second == 11) {
      int size = nq.size();
      for (int i=0; i<size; i++) {
        num = nq.front() * pow(10, (nq.size()-1));
        cout << "power " << pow(10, nq.size()-1) << endl;
        nq.pop();
        num = num + nq.front();
      }
      cout << "num" << " " << num << endl;
      if (q.front().second == 10) {
        q.pop();
        resultNum = num + q.front().second;
        cout << resultNum << endl;
      }
      else {
        q.pop();
        resultNum = num - q.front().second;
        cout << resultNum << endl;
      }
    }
  }
  int digit = NumDigits(resultNum);
  word = "";
  ostringstream os;
  os << resultNum;
  string digits = os.str();
  cout << digits << endl;

  
  
  // code goes here  
  return str;

}

int main(void) { 
   
  // keep this function call here
  cout << StringChallenge(coderbyteInternalStdinFunction(stdin));
  return 0;
    
}
```
