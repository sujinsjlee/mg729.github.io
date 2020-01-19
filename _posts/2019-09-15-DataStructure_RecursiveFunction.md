---
layout: post
title: Data Structure - Recursion(재귀, 순환)에 대한 이해
description: Understanding of Recursive Function
modified: 2019-09-15
tags: [Data Structure]
categories: [Data Structure]
---

## 1. 재귀( 순환 )
Recursion 이란 어떤 알고리즘이나 함수가 자기 자신을 호출하여 문제를 해결하는 프로그래밍 기법

## 2. 재귀 함수의 원리
주어진 문제를 더 작은 동일한 문제들로 분해하여 해결하는 방법 **분할 정복(divide and conqure)**

## 3. 반복 vs. 재귀 (순환)
팩토리얼 코드를 통해서 반복알고리즘과 순환 알고리즘 성능 비교

* 반복 알고리즘
{% highlight c++ %}
int factorial_iter(int n)
{
	int k, v = 1;
	for(k = n; k >= 0; k--)
	{
		v *= k;
	}
	return v;
}
{% endhighlight %}
for 반복문을 사용하여 n번 반복하므로 시간 복잡도는 O(n) 이다.  

* 순환 알고리즘
{% highlight c++ %}
int factorial(int n)
{
	if(n == 0 || n ==1)
	    return 1;
	return n * factorial(n-1);
}
{% endhighlight %}
한번 순환 호출 할 때마다 1번의 곱셈이 수행되고 순환호출이 n번 일어나므로 역시 시간복잡도는 O(n)이다.  

반복 알고리즘과 순환알고리즘의 시간 복잡도는 같지만 순환 호출의 경우 여분의 기억공간이 더 필요하다. (함수를 호출하기 위해서 함수의 파라미터들을 스택에 저장)  
따라서 <u>실행 시간도 더 걸린다.</u> 결론적으로 순환 알고리즘은 수행 시간과 기억공간의 사용에 있어서는 비효율적인 경우가 많다.  
*순환 호출 시에는 호출이 일어날때마다 호출하는 함수의 상태가 기억되어야하므로 여분의 기억장소가 필요하게 된다.*

## 4. Recursion 알고리즘이 반복 알고리즘보다 실행시간이 빠른 경우
숫자 x의 n-거듭제곱 값을 구하는 함수
 
* 반복 알고리즘
{% highlight c++ %}
double power_iter(double x, int n)
{
    int i;
	double r = 1.0;
	for(i = 0; i <n; i++)
	    r *= x;
    return r;
}
{% endhighlight %}
for 반복문을 사용하여 n번 반복하므로 시간 복잡도는 O(n) 이다.  

* 순환 알고리즘
{% highlight c++ %}
double power(double x, int n)
{
    if(n == 0) return 1;
	else if((n%2) == 0) 
	    return power(x*x, n/2);
    else 
	    return x*power(x*x, (n-1)/2);
}
{% endhighlight %}
Recursion 알고리즘 사용하면 한번의 순환이호출될 때마다 약 1번의 곱셈과 1번의 나눗셈이 일어나므로 시간 복잡도는 O(logN) 이다.  

* x의 거듭제곱 - 순환 알고리즘 시간복잡도  
  T(n)  
  = T(n/2) + c1 ``if n is even``  
  = T(n-1) + c2 ``if n is odd``  
  = T(0) = 1    ``if n is 0``  
 
  T(n)  
  = T(3n-2/2) + c1 + c2  
  = T(n/2) + k  
  = T(n/4) + 2k  
  = T(n/8) + 3k  
  = T(n/2^k) + ck  
    
  T(1)  
  = T(0) + c2  
  = 1 + k  
  
  1/2^k + ck = 1+ k  
  1/2^k = c  
  2^k = n  
  k = log2n   
           	   
**O(log n)**  
  
* 결론적으로, Recursion 알고리즘은 문제의 정의가 순환적으로 되어있는 경우에 유리한방법  
즉, 문제의 크기가 순환이 진행될 수록 작아지는 경우에 순환 알고리즘을 쓰는 것이 자연스럽다.