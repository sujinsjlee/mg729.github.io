---
layout: post
title: Data Structure - Stack (Concept and STL, C++ code)
description: (4) Understanding of Stack
modified: 2020-01-13
tags: [Data Structure, Stack]
categories: [DataStructure]
---

##  Stack
> **Last In First Out**  
> Stack is a linear data structure which follows a LIFO order  
> stack is implemented with  <u>array or linked list</u>  

<ul>
 <li> push() : Push data into the stack </li>
 <li> pop() :  Removes the most recently added element from the stack </li>
</ul>

##  Stack's advantage and disadvantage
> Assuming that the stack is implemented with **array**  
1. Advantage of Stack  
* Simple structure, easy to implement  
* Fast data storage and reading  

2. Disadvantage of stack  
* The maximum number of data should be determined in advance.  
* Storage space may be wasted (if the maximum number is fixed but not all of the space is used)  

##  Common point - Stack and Queue 
> Structure that has restriction to access to the data  
> Structure that can only insert or subtract data at one end  

##  stack - C++ Container library  
[c++ stack](https://en.cppreference.com/w/cpp/container/stack).  
```c++
#include <iostream>
#include <stack>
using namespace std;

int main()
{
    stack<int> s1; 
	
    s1.push(10);
    s1.push(20);
    s1.push(30);
    
    cout << s1.top() << endl; //30
    
    s1.pop();
    
    cout << s1.top() << endl; //20
    
}
```


```cpp
#include <iostream>
#include <stack>

using namespace std;

int main()
{
	stack <int> s;
	s.push(1);
	s.push(2);
	s.push(3);
	
	s.pop();
	s.push(4);
	s.pop();
	while(!s.empty())
	{
		cout << s.top() << " ";
		s.pop();
	}
	
	//2 1
	return 0;
}
```

##  Usage or Stack   
* How the function works in the process   
	* stack is used when a  **function calls** works   
* The stack structure is the basis of the **process execution**  
