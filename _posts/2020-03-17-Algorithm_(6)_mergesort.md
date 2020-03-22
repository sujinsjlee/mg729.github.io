---
layout: post
title: Algorithm - merge sort (Concept, Analysis and C++ code)
description: (6) Understanding of mergesort algorithm
modified: 2020-03-17
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---

## Merge sort
> **Merge sort**: Merge sort is implemented through a Divide-and-Conquer algorithm  
> * Algorithm that separates, sorts, and merges(collects) large problems into smaller problems    
> * After dividing the elements, merging them again by sorting them  


<center>
	<a href="https://en.wikipedia.org/wiki/Merge_sort">
		<img src="https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif"/>
	</a>
</center>


*not a Dynamic Programming*  
Using **Recursive call**  
1. Split the list in half  
	* divide the data list into two equally sized partial lists  
2. Sort each partial list recursively using merge sort  
3. Merging(Collecting) two sub-lists back into one sorted list  


## Analysis
* When there are four datas  
   - data_list = **[1, 9, 3, 2]**  
     - First, divide by **[1, 9]**, **[3, 2]**  
     - The front part is divided into **[1]** and **[9]**  
     - Sort and merge **[1, 9]**  
     - Next **[3, 2]** is divided into **[3]** and **[2]**  
     - Sort and merge **[2, 3]**  
     - Now merge **[1, 9]** and **[2, 3]** together  
       - Since 1 <2 **[1]**  
       - Since 9> 2 **[1, 2]**  
       - Since 9> 3 **[1, 2, 3]**  
       - Since there are only 9, **[1, 2, 3, 9]**  

## Time Complexity
> **$O(n log n)$**  

## C++ code implementation

```cpp
#include<iostream>
#include<cstdio>

using namespace std;

void merge(int * data, int * left, int * right, int medium, int size)
{
	int left_point = 0;
	int right_point = 0;
	int data_point = 0;
	// when left and right both have datas
	while(left_point < medium && right_point < size-medium)
	{
		if(left[left_point] > right[right_point])
		{
			data[data_point] = right[right_point];
			right_point++;
			data_point++;
		}
		else
		{
			data[data_point] = left[left_point];
			left_point++;
			data_point++;
		}
	}
	// only left has data
	while(left_point < medium)
	{
		data[data_point] = left[left_point];
		left_point++;
		data_point++;
	}
	// only right has data
	while(right_point < size-medium)
	{
		data[data_point] = right[right_point];
		right_point++;
		data_point++;
	}
}

void mergeSort(int * data, int size)
{
	if(size == 1)
		return;
	
	int medium = size/2;
	int leftData[medium];
	int rightData[size - medium];
	
	for(int i = 0; i < medium; ++i)
	{
		leftData[i] = data[i];
	}
	
	for(int i = 0; i < size - medium; ++i)
	{
		rightData[i] = data[medium + i];
	}
	
	//Divide
	mergeSort(leftData, medium); 
	mergeSort(rightData, size - medium);
	//Merge
	merge(data, leftData, rightData, medium, size);
	
}
int main()
{
	int list_s[] = {1,9,3,2};
	
	int len = sizeof(list_s) / sizeof(list_s[0]);
	cout  << len << endl;
	
	for(int i = 0; i < len; ++i)
		cout << list_s[i]<< " ";
	cout << endl;
	
	mergeSort(list_s, len);
	
	for(int i = 0; i < len; ++i)
		cout << list_s[i] <<" ";
	cout <<endl;	
		
	return 0;
	
}
```
  