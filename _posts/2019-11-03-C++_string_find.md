---
layout: post
title: C++ - std::string::find (C++11)
description: "C++ - 문자열 std::string::find (C++11)"
modified: 2019-11-03
tags: [C++, C++11]
categories: [C++]
---

## 1. find() 함수

> 주어진 문자열 순서와 동일한 **첫 번째** 부분 문자열을 찾는 함수  
> Finds the **first substring** equal to the given character sequence.    

## 2. find() return value
> 찾은 부분 문자열의 **첫 문자 위치** 또는 해당 부분 문자열이없는 경우 **npos**를 return  
>  **Position of the first character** of the found substring or **npos** if no such substring is found.    

{% highlight c++ %}
std::string str = "Hello String_World!";

std::string::size_type found;
found = str.find("S"); 
printf("%d\n", found); //6
found = str.find("World"); 
printf("%d\n", found); //13


std::string::size_type not_found;
not_found = str.find("bye");
if(not_found == std::string::npos)
{
	printf("not found\n"); //not found
}
{% endhighlight %}

Output:  
6  
13  
not found  
