 ---
 layout: post
 title: 2022-02-15 TOKENIZING STRING
 ---
  
 tokenizing string with stringstream! 🙆🏼‍♀️
 ``` cpp
#include <bits/stdc++.h>
 
using namespace std;
 
int main() {
    string line = "Hello World !! !!";
    vector <string> tokens;
    stringstream check(line);
    string s;

    while(getline(check, s, ' '))
        tokens.push_back(s);
     
    for(int i = 0; i < tokens.size(); i++)
        cout << tokens[i] << '\n';
}
```
