---
layout: post
title: Algorithm - Greedy algorithm (Fractional Knapsack Problem and C++)
description: (12) Understanding of Fractional Knapsack Problem
modified: 2020-04-04
tags: [Algorithm]
categories: [Algorithm]
---

## Fractional Knapsack Problem
- The problem of putting things in a backpack with a weight limit of k for maximum value  
	- Each object can be expressed as weight (w) and value (v)  
	- Since the object can be split, a part of the object can be put in a backpack, so it is called **Fractional** Knapsack Problem  
		- In contrast to the Fractional Knapsack Problem, there is also a backpack problem in which objects cannot be split into pieces (called 0/1 Knapsack Problem)  

## C++

```c++
#include<iostream>
#include<algorithm>
#include<vector>
using namespace std;

vector<pair<int, int>> data_list {{10,10}, {15,12}, {20,10}, {25,8},{30,5}};

bool compare(pair<int, int> a, pair<int, int> b)
{
	return (a.second/a.first) > (b.second/b.first); 
}

int main()
{
	float data_weight;
	cin >> data_weight;
	
	sort(data_list.begin(), data_list.end(), compare);
	
	float total_value = 0;
	float fraction = 0;
	for(auto it = data_list.begin(); it != data_list.end(); ++it)
	{
		if(data_weight - it->first >=0 )
		{
			data_weight -= it->first;
			total_value += it->second;
		}
		else
		{
			fraction = data_weight / it->first;
			total_value += (it->second * fraction);
			break;
		}
		
	}
	
	cout << total_value <<endl;
	cout << fraction <<endl;
	
	
	return 0;
}
```