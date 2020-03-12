---
layout: post
title: Algorithm - Insertion Sort (Concept,Pseudocode and C++ code)
description: (3) Understanding of Insertion sort
modified: 2020-03-08
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---

## Insertion Sort  

> Insertion sorting is an algorithm that completes a sort by finding and inserting its position by comparing all elements of the data array with the parts of the array that are already sorted, in order from the beginning.  


* Insertion sort starts from the **second index**  
* Compare two value :  <u>data value (**A**)</u> and <u>the data of the prior index of the corresponding data (**key value**)</u>  
* If the key value is smaller
	* the A value is copied to the later index
* This is repeated until the key value encounters larger data  
	* Insert key value right after location where big data is met  

<center>
	<a href="https://en.wikipedia.org/wiki/Insertion_sort">
		<img src="https://upload.wikimedia.org/wikipedia/commons/9/9c/Insertion-sort-example.gif"/>
	</a>
</center>

## Code Design   
> `index`  
> value  


* example of four datas in the list   
   ### 1. (5 3 2 4)  
    `1 0`  
    3 5  
    (**3 5** 2 4)  

    | base data index  | compared data index |
    | :---: | :---: |
    | 1     | 0     |

  ### 2. (<u>3 5</u> 2 4)  
    `2 1`   
    2 5  
    (3 **2 5** 4)  
    `1 0`  
    2 3  
    (**2 3** 5 4)  

    | base data index  | compared data index |
    | :---: | :---: |
    | 2     | 1     |

  ### 3. (<u>2 3 5</u> 4)  
    `3 2`   
    4 5  
    (2 3 **4 5**)  
    `2 1`   
    4 3  
    ~~`1 0`~~    

    | base data index  | compared data index |
    | :---: | :---: |
    | 3     | 2     |

  ### 4. (<u>2 3 4 5</u>)      


## Pseudocode  
[![carbon_code_highlighter](/images/carboninsertionsort.png)](https://carbon.now.sh/)
<!--```
for(int i = 0; i < 데이터 길이 -1 ; ++i)
  for(int base = i+1; base != 0 ; ++i)
  {
      if(data[base] < data[base-1])
        swapping two datas
      else
        break;
  }
```
-->

## Time Complexity
> two <u>for loops</u> : **$O(n^2)$**  

## C++ code implementation  
```cpp
#include<iostream>
using namespace std;

void insertionSort(int * data, int size)
{
	for(int i = 0; i < size-1 ; ++i )
	{
		for(int base = i+1 ; base != 0 ; --base)
		{
			if(data[base] < data[base-1])
			{
				int temp = data[base];
				data[base] = data[base-1];
				data[base-1] = temp;
			}
			else
				break;
		}
	}	
}
int main()
{
	int data_i[] = {4,5,3,2,1};

	int len = sizeof(data_i) / sizeof(data_i[0]);
	cout  << len << endl;

	for(int i = 0; i < len; ++i)
		cout << data_i[i] << endl;

	insertionSort(data_i, len);
	
	for(int i = 0; i < len; ++i)
		cout << data_i[i] << endl;
		
	return 0;
	
}
```
