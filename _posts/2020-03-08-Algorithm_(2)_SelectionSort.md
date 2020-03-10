---
layout: post
title: Algorithm - Selection Sort (Concept,Pseudocode and C++ code)
description: (2) Understanding of Selection sort
modified: 2020-03-08
tags: [Algorithm]
categories: [Algorithm]
---

## Selection Sort  

> Selection sort: __select__ the minimum value!  


* Selection sort Algorithm  
	* Finds minimum value in given data  
	* Replace this minimum with the value at the beginning of the data  
	* Repeat the rest of the data in the same way except for the first one  

<center>
	<a href="https://en.wikipedia.org/wiki/Selection_sort">
		<img src="https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif"/>
	</a>
</center>

## Code Design   
> **sorted from the begining of the data**  
> Every each time the for loop executes, sort after the first index value from the previous loop  
> __turn__ : One rotation turn of condition check for all list   


1. two datas for selection sort   
(3 2)  
(**2** 3)  
`turn : 1`  
`standard : 0`  

2. tree datas for selection sort  
(3 4 2)  
(**2** 4 3)  
(**2** **3** 4)  
`turn : 2`  
`standard : 1`  
3. four datas for selection sort  
(4 5 3 2)  
(**2** 5 3 4)  
(**2 3** 5 4)  
(**2 3 4** 5)  
`turn : 3`  
`standard : 2`  

## Pseudocode  
[![carbon_code_highlighter](/images/carbonSelectionSort.png)](https://carbon.now.sh/)

1. for(int standard = 0; standard < len(data_list) - 1 ; ++standard) : repeat for loop  
2. lowest = standard  
3. for(int num = 0; num < len(data_list); ++num) : repeat after __standard__   
	* if( data_list[lowest] > data_list[num] )
		* lowest = num
4. swapping two data  
	* data_list[num] <=> data_list[lowest]   


## Time Complexity
> two <u>for loops</u> : **$O(n^2)$**  

## C++ code implementation  
```cpp
#include<iostream>
using namespace std;

void selectionSort(int * data, int size)
{
	for(int standard = 0; standard < size-1 ; ++standard)  //turn 
	{
		int lowest = standard;
		for(int index = standard+1; index < size; ++index)
		{
			if(data[lowest] > data[index])
				lowest = index;
		}
		int temp = data[lowest];
		data[lowest] = data[standard];
		data[standard] = temp;
	}
}
int main()
{
	int list_s[] = {4,5,3,2,1};
	
	int len = sizeof(list_s) / sizeof(list_s[0]);
	cout  << len << endl;
	
	for(int i = 0; i < len; ++i)
		cout << list_s[i] << endl;
		
	selectionSort(list_s, len);
	
	for(int i = 0; i < len; ++i)
		cout << list_s[i] << endl;
		
		
	return 0;
	
}
```