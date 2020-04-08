---
layout: post
title: Algorithm - Greedy algorithm (Concept, Coin Exchange Problem and C++)
description: (11) Understanding of Greedy algorithm
modified: 2020-04-04
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---

## ## 1. What is the greed algorithm?
> Problem solving method for getting a value close to the optimal solution  
> Whenever you need to decide between one of several cases, **select the case that you think is the best every moment** and get the final value  
> **Selecting the best case for each step when there are multiple cases**  


## 2. Limitations of the greed algorithm
- The greed algorithm is used for **approximation estimation**    
- Because it is not always possible to find the optimal solution  
- It is one of the methods to find the value **close to** the optimal solution  

<center>
	<a href="https://en.wikipedia.org/wiki/Greedy_algorithm">
		<img src="https://upload.wikimedia.org/wikipedia/commons/8/8c/Greedy-search-path-example.gif"/>
	</a>
</center>



- When starting finding the path from the root node to the leaf node for finding the largest value  
   - 7-> 12-> 6 is selected when the Greedy algorithm is applied, so 7 + 12 + 6 = 25  
   - However, the actual largest value is 7 -> 3 -> 99, and 7 + 3 + 99 = 109   


## 3. 탐욕 알고리즘 예  

### 동전 문제   
- When the value to be paid is 4720 won, pay the lowest number of coins with 1 won, 50 won, 100 won, and 500 won coins  
	- It can be implemented by filling in the value that requires **maximum payment from the largest coin**  
	- You can select the case that you think is optimal every moment with the greed algorithm  
 
#### C++

```cpp
#include<iostream>
#include<cstdio>
#include<algorithm>

using namespace std;

bool compare(int a, int b)
{
	return a > b;
}
int main()
{
	int n;
	scanf("%d", &n);
	
	int answer = 0;
	int coins[] = {1, 100, 50, 500};
	int length = sizeof(coins)/sizeof(coins[0]);
	
	sort(coins, coins+4, compare);
	
	for(int i = 0; i < length; ++i)
	{
		int balance = n % coins[i];
		answer += (n/coins[i]);
		printf("%d %d %d \n", coins[i], n/coins[i], balance);
		n = balance;
	}
	
	printf("%d", answer);
	return 0;
}
```
