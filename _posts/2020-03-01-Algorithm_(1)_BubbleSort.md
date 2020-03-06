---
layout: post
title:  - (1) Bubble Sort
description: (1) Understanding of bubble sort
modified: 2020-03-01
tags: [Algorithm]
categories: [Algorithm]
---

## Bubble sort
> **Bubble sort**: repeatedly steps through the list, compares two adjacent datas and swaps them if they are in the wrong order  

![Bubble sort](https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif)  
[wiki-Bubble_sort](https://en.wikipedia.org/wiki/Bubble_sort)

## Code Design  
* **condition check** : Compare two datas  
* __turn__ : One rotation turn of condition check for all list    


1. two datas for bubble sort   
(3 2)  
(2 __3__)  
{: .notice--info}
`condition check : 1`  
`turn : 1`  

2. tree datas for bubble sort  
(5 4 3)  
(4 3 __5__)  
(3 __4__ __5__)  
{: .notice--info}
`condition check : 2`  
`turn : 2`  

3. four datas for bubble sort  
(5 4 3 2)  
(4 3 2 __5__)  
(3 2 __4__ __5__)
(2 __3__ __4__ __5__) 
{: .notice--info}
`condition check : 3`  
`turn : 3`  


## Algorithm - Pseudocode
```cpp
for(int n = 0; n < length of the entire data -1; n++)
	for(int index = 0; index < length of the entire data - n -1 ; index++)
		if( data1 > data2)
			swap
```	
{: .notice--success}
`length of the entire data - n -1`
* The reason for **-n** is to do condition check only on unsorted data  
* because the data of the back is sorted after every each turn.     

1. for num in range(len(data_list)) - repeat  
2. `swap = 0` (make a variable to check swap was executed)  
3. Inside the second roop, for index in range(len(data_list) - num - 1) : n - 1 repeat  
4. If data_list[index] > data_list[index + 1]   
	* Swap : data_list[index], data_list[index + 1] = data_list[index + 1], data_list[index]  
	* `swap += 1`  
	* if swap == 0 :  break, because the list is already sorted  
 
## Time Complexity
> two <u>for loops</u> : **O(n^2)**  

If entire lists are already sorted, the time complexity is *O(n)*  


<!--
## C++ code implementation  
https://www.tutorialspoint.com/cplusplus-program-to-implement-bubble-sort
```cpp
#include<iostream>
using namespace std;
void swapping(int &a, int &b) {      //swap the content of a and b
   int temp;
   temp = a;
   a = b;
   b = temp;
}
void display(int *array, int size) {
   for(int i = 0; i<size; i++)
      cout << array[i] << " ";
   cout << endl;
}
void bubbleSort(int *array, int size) {
   for(int i = 0; i<size; i++) {
      int swaps = 0;         //flag to detect any swap is there or not
      for(int j = 0; j<size-i-1; j++) {
         if(array[j] > array[j+1]) {       //when the current item is bigger than next
            swapping(array[j], array[j+1]);
            swaps = 1;    //set swap flag
         }
      }
      if(!swaps)
         break;       // No swap in this pass, so array is sorted
   }
}
int main() {
   int n;
   cout << "Enter the number of elements: ";
   cin >> n;
   int arr[n];     //create an array with given number of elements
   cout << "Enter elements:" << endl;
   for(int i = 0; i<n; i++) {
      cin >> arr[i];
   }
   cout << "Array before Sorting: ";
   display(arr, n);
   bubbleSort(arr, n);
   cout << "Array after Sorting: ";
   display(arr, n);
}
```

-->
