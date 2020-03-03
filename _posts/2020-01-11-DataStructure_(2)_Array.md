---
layout: post
title: Data Structure - (2) Array
description: (2) Understanding of Array
modified: 2020-01-11
tags: [Data Structure, Array]
categories: [DataStructure]
---

##  Array  
>**Array stores a fixed-size sequential collection of elements of same type**  
> each data is correspond to an index  
> By index, direct access to data is possible    
> Sequentially process the same type of data  

## Advantages of Arrays
* Quick access using index  

## Disadvantages of Arrays
* It is _not easy to add or delete data_ if data is variable.  
	* Since the fixed amount of memory space is declared, it is difficult to add new data unless you know the maximum length of the array.  
	* After deleting the data, there is a problem to pull the data that was existing behind   
* When declaring data of array type, size of maximum length must be declared in advance  


## Example (C++)  
Count frequency of how many **'M'** has been appeared inside the dataset  

{% highlight c++ %}
#include<stdio.h>

int main()
{
	char dataset[][70] = {"Jennifer Anniston, Ms. Jen",
		"Courtney Cox, Ms. Cox",
		"Lisa Kudrow, Ms. Kudrow",
		"Matthew Perry, Mr. Perry (Metthew)",
		"David Schwimmer, Mr. Schwimmer",
		"Matt LeBlanc, Mr. LeBlanc (Matt)"};
    int m = 0;
    
  	for(char* data : dataset)
    {
    	for(int i = 0; data[i] != '\0' ; i++)
    	{
			if( data[i] =='M')
			{
				m++;   		
			}
		}
	} 
	printf("%d\n", m); //10

	return 0;
}
{% endhighlight %}


* [Two dimension array and Pointer array](http://www.parkjonghyuk.net/lecture/programming1/lecturenote/chap06-6.pdf).