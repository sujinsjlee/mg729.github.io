---
layout: post
title: C++ - std::string::npos (npos의 의미)
description: "C++ - 문자열 string::npos"
modified: 2019-11-03
tags: [C++]
categories: [C++]
---

## npos

> npos : size_type 으로 정의된 특수값    
> -1 값으로 정의  
   
{% highlight c++ %}
static const size_type npos = -1;  
{% endhighlight %}

string :: npos는 -1 값을 가지는 상수  
find() 함수에 의해서 found 되지 못하는 경우 npos값이 리턴  

- find() 함수 return value  
Position of the first character of the found substring or **npos** if no such substring is found.  