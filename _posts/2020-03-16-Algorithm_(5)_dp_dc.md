---
layout: post
title: Algorithm - Dynamic Programming & Divide and Conqure (Concept and C++ examples)
description: (5) Understanding of DP & Divide and Conqure algorithm
modified: 2020-03-16
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---

## Dynamic Programming and Divide and Conquer

> <u>Dynamic Programming (often called <b>DP</b>)</u>  
> Algorithm that solves the problem of the small input size first  
> And then, solves the problem of the larger size, and finally solves the whole problem by using the solution of the partial problem


- **bottom-up** approach, find the lowest answer, save it, and solve the upper problem by using the result
- **Memoization** is the key concept
	- Memoization
		- A technique that utilize the previously calculated values when running a program  
		- It speeds up the overall execution by not recalculating
- When dividing datas, partial datas are duplicated and recycled
	- _Example: Fibonacci sequence_


> <u>Divide and Conquer</u>  
> Algorithm to solve the problems by dividing each other until the problem cannot be divided, and then merging again to get the answer to the problem  


- **Top-down** approach, descending downward to find the upper answer  
	- Generally implemented as a **recursive function**  
-  When dividing a problem, partial problems do not overlap with each other  
	- _Example: merge sort, quick sort, etc._

## Similarities and differences
- **Common points**
	- Split the problem into small pieces
- **Differences**
	- Dynamic programming
		- Partial problems are duplicated and recycled when solving high-level problems
		- Using the Memoization technique (used as an optimization technique to save and recycle answers to partial problems)
	- Split conquest
		- Partial problems do not overlap with each other
		- No Memoization technique

## Understanding Dynamic Programming  
> **Fibonacci**  
> Fibonacci sequence : each number is the sum of the two preceding one  
> *0,1,1,2,3,5,8,13,21,34,55,89,144,...*  


F_0=0  
F_1=1  
F_n=F_{n-1}+F_{n-2}\qquad(n\in\{2,3,4,\dots\})  


1. Divide and Conquer  
```cpp
#include<iostream>
#include<cstdio>

using namespace std;

int fibo(int n)
{
	if(n == 0)
		return 0;
	else if(n == 1)
		return 1;

	return fibo(n-1) + fibo(n-2);
}
int main()
{
	int n;
	cin >> n;
	
	cout << fibo(n) << endl;
	
	return 0;
}
```


2. Dynamic Programming

```cpp
#include<iostream>
#include<cstdio>

using namespace std;

int fibo(int n)
{
	int cache[n];
	
	cache[0] = 0;
	cache[1] = 1;
	
	for(int i = 2; i <= n; ++i)
	{
		cache[i] = cache[i-1] + cache[i-2];
	}
	
	return cache[n];
}
int main()
{
	int n;
	cin >> n;
	
	cout << fibo(n) << endl;
	
	return 0;
}
```
* Dynamic Programming algorithm is faster than Divide and Conqure algorithm  
