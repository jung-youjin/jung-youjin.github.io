---
layout: post
title: GFG LONGEST REPEATED SUBSEQUENCE
---

`DP` practice set from *Geeks for Geeks*

``` cpp
int findLongestRepeatingSubSeq(string str)
{
    int n = str.length();
  
    // Create and initialize DP table
    int dp[n+1][n+1];
  //initializing first row and column in dp table
    for(int i=0;i<=n;i++){
      dp[i][0] =0;
      dp[0][i] =0;
    }
   
  
    // Fill dp table (similar to LCS loops)
    for (int i=1; i<=n; i++)
    {
        for (int j=1; j<=n; j++)
        {
            // If characters match and indexes are
            // not same
            if (str[i-1] == str[j-1] && i != j)
                dp[i][j] =  1 + dp[i-1][j-1];         
                       
            // If characters do not match
            else
                dp[i][j] = max(dp[i][j-1], dp[i-1][j]);
        }
    }
    return dp[n][n];
}
```
