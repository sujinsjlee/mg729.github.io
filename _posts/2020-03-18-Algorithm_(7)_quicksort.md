---
layout: post
title: Algorithm - quick sort (Concept,Pseudocode and C++ code)
description: (7) Understanding of quick sort algorithm
modified: 2020-03-18
tags: [Algorithm]
categories: [Algorithm]
use_math: true
published: false
---


## 퀵 정렬 (Quick sort)  
> ** Quick! Sort ** Algorithm is fast - low time complexity  
> Set **pivot** among the data, and divide data smaller than the pivot to the left and data larger than the pivot to the right  
> For each left and right, repeat the above operation by calling the same function again using **recursive call**  
> Function returns left + pivot + right


[![quick_sort](https://upload.wikimedia.org/wikipedia/commons/thumb/a/af/Quicksort-diagram.svg/800px-Quicksort-diagram.svg.png)](https://en.wikipedia.org/wiki/Quicksort)


* Main Point : There is a **pivot** and divides data to the left and right based on the pivot  
* And recursively do the above  

* The pivot is set according to the rule. Usually, the first data or the last data is set as the pivot.

## Pseudocode
1. Select pivot     
2. divide data  
	* smaller than pivot, **pivot**, larger than pivot  
3. recursively call **2** step until the length of the data_list becomes 1   
4. merge  
{: .notice--info}

## 시간 복잡도
**$O(nlogn)$**  

## C++ code implementation  
```cpp

```
