---
layout: post
title: Algorithm - memoization
description: "About memoization"
modified: 2021-07-06
tags: [Algorithm]
categories: [Algorithm]
---
## memoization
- **Memoization** is a technique that speeds up program execution by eliminating duplicate execution of the same calculation by storing previously calculated values in memory when a computer program needs to repeat the same calculations.
- Example 
    - **binomial coefficient**
    - **nCr = n-1Cr + n-1Cr-1**
    - **nCn == nC0** : **1**
		- *Number of cases of selecting all n out of n* 
		- *Number of cases of selecting none of n* 
			- Since above there is only 1 case for each, nCn and nC0 have a value of 1.
    - Utilize the result of the combination already calculated so that it is not redunduntly calculated twice

- binomial coefficient <!--이항 계수-->

```c++
#include<bits/stdc++.h>
using namespace std;

int memoi[22][22];

int dfs(int n, int r) {
	if(memoi[n][r]) return memoi[n][r];
	if(n == r || r == 0) return 1;
	else return memoi[n][r] = dfs(n-1, r) + dfs(n-1, r-1); // dfs(n-1, r) + dfs(n-1, r-1) 怨꾩궛??寃곌낵瑜?memoi[n][r] ????낇븯怨? memoi[n][r] ??return 
}

int main() {
	ios::sync_with_stdio(false);
	cin.tie(nullptr);
	
	freopen("input.txt", "rt", stdin);
	
	int n, r;
	cin >> n >> r;
	
	// nCr = n-1Cr + n-1Cr-1
	cout << dfs(n, r);	

 	return 0;
}
```

