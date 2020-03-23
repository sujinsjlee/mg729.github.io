---
layout: post
title: Algorithm - Sequential Search and Binary Search (Concept and C++)
description: (8) Understanding of quick sort algorithm
modified: 2020-03-23
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---

## Sequential Search
> **Search** means finding the desired data among the data list  
> **Sequential Search**: Find the data you want by comparing the list one by one from the front  


* Time complexity  
	* Worst case: when list length is n, it should be compared n times  
	* $O(n)$  

* C++ example   

```cpp
#include<iostream>
#include<cstdio>

using namespace std;

bool sequentialSearch(int* data, int size, int key)
{
	for(int i = 0; i < size; ++i)
	{
		if(data[i] == key)
		{
			return true;
		}
	}
	return false;
}

int main()
{
	int list_s[] = {5,4,3,2,1};
	
	int len = sizeof(list_s) / sizeof(list_s[0]);
	
	if(sequentialSearch(list_s, len, 3))
		cout << "search success" << endl;
	else
		cout << "search fail" << endl;
}
```

## Binary Search 
> **Binary Search**: Divide the data to be searched into **half** to search for the desired data  
> Divide and Conqure



<center>
	<a href="https://en.wikipedia.org/wiki/Binary_search_algorithm">
		<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Binary_Search_Depiction.svg/1920px-Binary_Search_Depiction.svg.png"/>
	</a>
</center>

* Binary search
	* ** Divide **: Divide the data list into two sublists
	* ** Conqure **
		* data > Medium value: Search for the number to search in the sub-list at the back
		* data < Medium value: Search for the number to search in the previous sub-list

## Time Complexity
* Divide n lists in half every times and perform comparison operations k times until 1  
	- n X $\frac { 1 }{ 2 }$ X $\frac { 1 }{ 2 }$ X $\frac { 1 }{ 2 }$ ... = 1  
	- n X $\frac { 1 }{ 2 }^k$ = 1  
	- n = $2^k$ = $log_2 n$ = $log_2 2^k$  
	- $log_2 n$ = k  
	- In big O notation, k + 1 is the final time complexity (even when it becomes 1, comparison operation is performed once)    
		- Eventually, $O(log_2 n + 1)$, 2 and 1, constant are deleted so, $O(log n)$  

## C++

```cpp
#include<iostream>
#include<cstdio>

using namespace std;

void binarySearch(int* data, int left, int right, int key)
{
	if(right < left)
	{
		cout << "search fail" << endl;
		return;
	}
	
	int mid = left + (right-left)/2;
	
	if(data[mid] == key)
	{
		cout << "search success" << endl;
		return;
	}
	
	if(data[mid] < key)
		binarySearch(data, mid+1, right, key);
	else
		binarySearch(data, left, mid-1, key);
}

int main()
{
	int list_s[] = {2,5,8,12,16,23,38,56,72,91};
	
	int len = sizeof(list_s) / sizeof(list_s[0]);
	
	binarySearch(list_s, 0, len-1, 23);
	binarySearch(list_s, 0, len-1, 10);
	
	return 0;

}
```