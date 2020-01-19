---
layout: post
title: C++ - Range based for loop 범위 기반 for 루프 (since C++11)
description: "Range based for loop(since C++11)"
modified: 2019-09-12
tags: [C++, C++11]
categories: [C++]
---

## 1. C++ Range based for loop
c++11 에서 새롭게 소개된 for문.

>범위 지정이 없는 for 루프 (Executes a for loop over a range.)  
>컨테이너 기반의 for 루프 (Used as a more readable equivalent to the traditional for loop operating over a range of values, such as all elements in a container.)

<ol> 
<li>range based for loop를 사용하면 전통적인 for 문과 달리 크기를 지정할 필요가 없습니다.</li>
   <ol>
   <li> c++98 - 기존의 for 문 </li>
   {% highlight c++ %}
   int main()
   {
      int x[5] = {1,2,3,4,5};
	
      for(int i = 0; i<5; i++)
	      cout << x[i] << "\n";
   }
   {% endhighlight %}
   <li> since C++11 - range based for 루프 </li>
   {% highlight c++ %}
   int main()
   {
      int x[5] = {1,2,3,4,5};
	  
      for(auto n : x)
  	    cout << n << "\n";
   }
   {% endhighlight %}
   c언어에서 사용하던 for문은 배열(또는 컨테이너)의 크기가 변경될 경우 for문의 코드가 변경되어야합니다. 하지만 range based for loop에서는 크기를 지정할 필요가 없습니다.
   </ol>
<li> range based for loop의 원리</li>
  - 컴파일러가 생성하는 코드
 {% highlight c++ %}
 int main()
 {
   int x[5] = {1,2,3,4,5};
	 
   for(auto p = begin(x); p != end(x); ++p)
   {
	    auto n = *p;
	 
	    cout << n << "\n";
   }
 }  
 {% endhighlight %}
</ol>  
###### please refer to the below blog link for more deeper understanding of releated topic  
[range based for loop](https://blockdmask.tistory.com/319).  