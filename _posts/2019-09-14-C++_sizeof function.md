---
layout: post
title: C++ - sizeof() 와 size() 함수
description: "the difference between sizeof() and size() in C++"
modified: 2019-09-14
tags: [C++]
categories: [C++]
---

## 1. sizeof

>sizeof() 함수는 메모리 공간을 차지하는 byte수를 return 합니다.  
>the **sizeof() operator**  does not give you the number of elements in an array, gives you the number of bytes a thing occupies in memory.  

>sizeof() 함수로 포인터 변수의 크기를 구한다면 운영체제에 따른 byte 수가 return  
>**32-bit operating system : 4bytes**  
>**64-bit operating system : 8bytes**  
>배열의 이름은 배열의 시작주소를 의미합니다. sizeof(배열이름) 은 4bytes 혹은 8bytes가 return됩니다.  
>an array type will degenerate into a pointer type at every opportunity.  

<ol>
<li> sizeof() 함수는 메모리 공간을 차지하는 byte수를 return </li>
{% highlight c++ %}
#include <stdio.h>
int main()
{
  char s[] = { 1, 2, 3, 4, 5, 0 };
  int xs[] = { 1, 2, 3, 4, 5, 0 };

  printf( "sizeof( s ) = %d\n",  sizeof( s  ) );
  printf( "sizeof( xs ) = %d\n", sizeof( xs ) );

  return 0;
}
{% endhighlight %}
sizeof(s) = 6<br/>   
sizeof(xs) = 24   
<li> sizeof() 함수로 포인터 변수의 크기를 구한다면 운영체제에 따른 byte 수가 return </li>
{% highlight c++ %}
#include <stdio.h>
void f( const char s[] )
{
  printf( "The size of f()'s     (s) is %d\n", sizeof( s ) );  
}
  
int main()
{
  const char s[] = "Hello world!";
  printf( "s = \"%s\"\n", s );
  printf( "The size of main()'s  (s) is %d\n", sizeof( s ) );
  f( s );
  printf( "The size of main()'s (&s) is %d\n", sizeof( &s ) );
  return 0;
}
{% endhighlight %}
s = "Hello world!"<br/> 
The size of main()'s  (s) is 13<br/> 
The size of f()'s     (s) is 4<br/> 
The size of main()'s (&s) is 4<br/> 
</ol> 

## 2. std::size() 혹은 STL의 size()함수
>**std::size()**함수는 주어진 컨테이너 혹은 배열의 size를 return  
>Returns the size of the given container c or array array.  
>The new C++11 std::array class provides a lot of STL sequence container information about your array, including its **size()**.  


###### please refer to the below blog link for more deeper understanding of size of array and size of vector   
[size of array](http://www.cplusplus.com/faq/sequences/arrays/sizeof-array/).  
[size()](https://en.cppreference.com/w/cpp/iterator/size).  
[sizeof()](https://en.cppreference.com/w/cpp/language/sizeof).  