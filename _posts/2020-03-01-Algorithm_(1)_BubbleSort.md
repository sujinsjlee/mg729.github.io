---
layout: post
title: Algorithm - Bubble Sort
description: (1) Understanding of bubble sort
modified: 2020-03-01
tags: [Algorithm]
categories: [Algorithm]
---

## Bubble sort
> **Bubble sort**: repeatedly steps through the list, compares two adjacent datas and swaps them if they are in the wrong order  

<center>
	<a href="https://en.wikipedia.org/wiki/Bubble_sort">
		<img src="https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif"/>
	</a>
</center>

<!--
![](https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif)  
[wiki-Bubble_sort](https://en.wikipedia.org/wiki/Bubble_sort)
-->
## Code Design  
* **condition check** : Compare two datas  
* __turn__ : One rotation turn of condition check for all list    


1. two datas for bubble sort   
(3 2)  
(2 __3__)  
`condition check : 1`  
`turn : 1`  

2. tree datas for bubble sort  
(5 4 3)  
(4 3 __5__)  
(3 __4__ __5__)  
`condition check : 2`  
`turn : 2`  

3. four datas for bubble sort  
(5 4 3 2)  
(4 3 2 __5__)  
(3 2 __4__ __5__)  
(2 __3__ __4__ __5__)  
`condition check : 3`  
`turn : 3`  


## Algorithm - Pseudocode
[![carbon_code_highlighter](/images/carbonBubbleSort.png)](https://carbon.now.sh/)

* **length of the entire data - i -1**
* The reason for **- i**   
	* the bubble sort will be executed only on unsorted data  
	* last index of the list will be sorted every each turn  
	* therfore, reduce the number of repetitions (*reduce the count of the loop*)    

1. <u>for num in range(len(data_list))</u> : repeat  
2. `swap = false` (make a flag to check swap was executed)  
3. Inside the second roop, <u>for index in range(len(data_list) - i - 1)</u> : repeat  
4. If data_list[index] > data_list[index + 1]   
	* Swapping two datas     
	* `swap = true`  
5. If swap == false :  break, because the list is already sorted  
 
## Time Complexity
> two <u>for loops</u> : **O(n^2)**  

If entire lists are already sorted, the time complexity is *O(n)*  

## C++ code implementation  
```cpp
#include<iostream>
using namespace std;

void bubbleSort(int * data, int size)
{
	for(int i = 0; i < size-1 ; ++i)
	{
		bool swaps = false;
		for(int index = 0; index < size - i - 1; ++index)
		{
			if(data[index] > data[index+1])
			{
				int temp = data[index];
				data[index] = data[index+1];
				data[index+1] = temp;
			}
			swaps = true;
		}
		if(!swaps)
			break;
	}
}
int main()
{
	int list_b[] = {5,4,3,2,1};
	
	int len = sizeof(list_b) / sizeof(list_b[0]);
	cout  << len << endl;
	
	for(int i = 0; i < len; ++i)
		cout << list_b[i] << endl;
		
	bubbleSort(list_b, len);
	
	for(int i = 0; i < len; ++i)
		cout << list_b[i] << endl;
		
		
	return 0;
	
}
```
