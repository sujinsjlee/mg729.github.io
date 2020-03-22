---
layout: post
title: Algorithm - quick sort (Concept and C++ implementation)
description: (7) Understanding of quick sort algorithm
modified: 2020-03-18
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---


## Quick sort  
> **Quick! Sort** Algorithm is fast - low time complexity  
> Set **pivot** among the data, and divide data smaller than the pivot to the left and data larger than the pivot to the right  
> For each left and right, repeat the above operation by calling the same function again using **recursive call**  


[![quick_sort](https://upload.wikimedia.org/wikipedia/commons/thumb/a/af/Quicksort-diagram.svg/800px-Quicksort-diagram.svg.png)](https://en.wikipedia.org/wiki/Quicksort)


* Main Point : There is a **pivot** and divides data to the left and right based on the pivot  
* And **recursively** do the above  

* The pivot is set according to the rule. 
	* Usually, the first data or the last data is set as the pivot.

## Analysis
1. Select last data as pivot
2. Going from left (i) to right, finding a data smaller than the pivot
3. Exchange the elements for each index i, j
4. Repeat steps 2 and 3
5. If it is impossible to proceed 2 or 3 , exchange it with the current pivot.
6. Now, based on the exchanged pivot, there are only smaller values on the left and larger values on the right.
{: .notice--info}

## Time Complexity
**$O(nlogn)$**  

## C++ code implementation  
```cpp
#include<iostream>
using namespace std;

void swap(int* a, int* b);

int quickSplit(int* data, int low, int high)  
{  
    int pivot = data[high]; //last element as pivot
    int i = low; // Index of smaller element
    
    for (int j = low; j < high; j++)
    {
        // If current element is smaller than the pivot
        if (data[j] < pivot)
        {
            i++; // increment index of smaller element
            swap(&data[i-1], &data[j]);
        }
    }
    swap(&data[i], &data[high]);
    return i;
}

void quickSort(int* data, int start, int end)
{
	if(start >= end)
		return;
	
	//index means the pivot data index of the result for quickSplit 
	int index = quickSplit(data, start, end); 
	
	quickSort(data, start, index-1);
	quickSort(data, index+1, end);
	
}
int main()
{
	int list_q[] = {5,3,1,8,7,4,9,2};
	
	int len = sizeof(list_q) / sizeof(list_q[0]);
	cout  << len << endl;
		
	quickSort(list_q, 0, len-1);
	
	for(int i = 0; i < len; ++i)
		cout << list_q[i] << " ";
		
	return 0;
	
}

void swap(int* a, int* b)  
{  
    int temp = *a;  
    *a = *b;  
    *b = temp;  
}
```
