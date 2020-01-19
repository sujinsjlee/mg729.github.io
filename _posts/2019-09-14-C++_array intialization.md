---
layout: post
title: C++ - 배열 초기화, 0으로 배열 초기화하기
description: "array initialization and zero initialization in C++"
modified: 2019-09-14
tags: [C++, C++ Basic]
categories: [C++]
---

## 1. 배열 선언 및 초기화

<ol>
<li> 디폴트로, <strong>지역변수</strong>로 초기화 없이 선언만 된 배열은 초기화되지 않는다. </li>
 
<li> 일부 값만 초기화 된 경우 : 초기화되지 않은 인덱스들은 0으로 초기화 </li>
{% highlight c++ %}
int array1 [5] = { 10,20,30 };
{% endhighlight %}
10,20,30,0,0 의 값으로 초기화 됩니다.<br/><br/>

<li>  아무런 값이 없고 그냥 brace 만 선언된 경우 : 배열 값은 0으로 초기화 </li>
{% highlight c++ %}
int array2 [5] = { };
{% endhighlight %}

<li>  universal initialization(uniform initialization) </li>
{% highlight c++ %}
int foo[] = { 10, 20, 30 };
int foo[] { 10, 20, 30 };
{% endhighlight %}

</ol> 

## 2. 0으로 초기화 - ZERO initialization  
> 1. 전역변수로 고정된 값으로 배열선언만하고 value 지정 없을시 배열내의 모든 값은 0으로 초기화
> 2. 고정된 사이즈로 배열 선언과 동시에 한가지이상의값을 초기화하는 경우: 초기화하지않은 값은 모든 value는 0으로 초기화
> 3. 빈 brace {} 로 초기화 된 경우: 배열 내의 모든 값은 0으로 초기화

* 전역변수 zero initialization
{% highlight c++ %}
int a[100];
int b[100] = {}; 
int c[100] = {0,};
int d[100] = {0};
{% endhighlight %}

* 지역변수 zero initialization
{% highlight c++ %}
int z1[100] = {0}; 
int z2[100] = {0,}; 
int z3[100] = {};

//below case does not meet zero intialization
int z4[100];
z4[1]=1; //the other element of array z4 is still a garbage value
{% endhighlight %}

###### please refer to the below blog link for more deeper understanding of size of array and size of vector   
[array initialization](https://en.cppreference.com/w/c/language/array_initialization).  
[tutorial for ARRAY](http://www.cplusplus.com/doc/tutorial/arrays/).  
