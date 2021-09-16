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

int getQNum(queue<pair<string, int>> q) {
  int qsize = q.size();
  int num = q.front().second;
  for (int i=qsize; i>0; i--) {
    int dnum = q.front().second * pow(10, i-1);
    q.pop();
    if (q.empty()) break;
    num = dnum + q.front().second;
  }
  return num;
}

int getNqNum(queue<int> nq) {
  int num = nq.front();
  int size = nq.size();
  for (int i=size; i>0; i--) {
    int dnum = nq.front() * pow(10, i-1);
    nq.pop();
    if (nq.empty()) break;
    num = dnum + nq.front();
  }
  return num;
}

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

void StringChallenge(string str) {
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
    if (q.front().second == 10 || q.front().second == 11) {   
      num = getNqNum(nq);
      if (q.front().second == 10) {
        q.pop();
        int temp = getQNum(q);
        resultNum = num + temp;
      }
      else {
        q.pop();
        int temp = getQNum(q);
        resultNum = num - temp;
      }
    }
    else {
      nq.push(q.front().second);
    }
    q.pop();
  }

  int digit = NumDigits(resultNum);
  word = "";
  ostringstream os;
  os << resultNum;
  string digits = os.str();
  if (digits[0]=='-') digit++;
  for (int i=0; i<digit; i++) {
    if (digits[i]=='-') cout << "negative";
    else {
      int s = stoi(string(1, digits[i]));
      cout << listNum[s];
    }
  }
}

int main(void) { 
  // keep this function call here
  StringChallenge(coderbyteInternalStdinFunction(stdin));
  return 0;
    
}
```
