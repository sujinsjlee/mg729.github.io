---
layout: post
title: Algorithm - Recursive call (Concept and C++ examples)
description: (3) Understanding of Recursive algorithm
modified: 2020-03-14
tags: [Algorithm]
categories: [Algorithm]
---

## Recursive Call 
> ** The same function is called in the function **  
> Functions are managed internally as ** stack **  

# Practice by C++ code  

## Palindrome 
> **A palindrome** is a word, sentence, verse, or even number that reads the same backward or forward.  
> Determine that the input number is the same data even if you read the order backwards  
> ex) level, mom  



```cpp
#include <iostream>
#include <cstdio>
/*
l e v e l
0 1 2 3 4  len 5 size 2

m o m o
0 1 2 3  len 4 size 2 
*/
using namespace std;


bool isPalindrome(char * str_s, int s, int e)
{
	if(s == e) //one charactor
		return true;
		
	if(str_s[s] != str_s[e]) // not palindrome
		return false;
	
	if(e - s > 1) // in case of len is even
	//if( end - begin > 1 )
		return isPalindrome(str_s, s+1, e-1);
	
	return true;
}

int main()
{
	char str[100];
	scanf("%s", str);
	int len = 0;
	for(int i = 0; str[i] ; ++i)
	{
		++len;
	}
	
	printf("%d\n", len);
	
	if(isPalindrome(str, 0, len-1)) //since array index starts from 0, the -1 is essential
		cout << "the input string is palindrome" << endl;
	else
		cout << "the input string is not palindrome" <<endl;
	
	
	
	return 0;
}
```


## ACM-ICPC > Regionals > Asia > Korea > Asia Regional - Taejon 2001  

There are 7 ways to express the integer 4 as a combination of 1, 2, and 3 as follows:  
1+1+1+1  
1+1+2  
1+2+1  
2+1+1  
2+2  
1+3  
3+1  
**Given an integer n as input, find the number of ways that "n" can be represented as the sum of 1, 2, 3**  


> **f(n): A function that returns the number of cases where an integer n can be created**  
> f(n) = f(n-1) + f(n-2) + f(n-3)  


```cpp
#include<cstdio>
#include<iostream>

using namespace std;

int test(int data)
{
	if(data == 1)
		return 1;
	else if(data == 2)
		return 2;
	else if(data ==3)
		return 4;
	
	return test(data-3) + test(data-2) + test(data-1);
}

int main()
{
	int n;
	cin >> n;
	int count = test(n);
	
	cout << count << endl;
}
```

