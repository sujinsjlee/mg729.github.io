---
layout: post
title: Data Structure - Queue (Concept and C++ STL, Priority queue)
description: (3) Understanding of Queue
modified: 2020-01-12
tags: [Data Structure, Queue]
categories: [DataStructure]
---

##  Queue
>**First In First Out(FIFO)**

Linear Data Structure that can take out the data in order of FIFO  
Take out data method is opposite to the stack  
<ul>
 <li> Enqueue : load data into the queue </li>
 <li> Dequeue : substract data in the queue </li>
</ul>

##  queue - C++ STL Container  
[c++ queue](https://en.cppreference.com/w/cpp/container/queue).  
```c++
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> q1;

    q1.push(10); // call push_back
    q1.push(20);
    q1.push(30);
    
    cout << q1.front() <<endl; //10
    cout << q1.back() <<endl;  //30 
    
    q1.pop();
	
    cout << q1.front() <<endl; //20  
    
}
```


```cpp
#include <iostream>
#include <queue>

using namespace std;

int main()
{
	queue<int> q;
	q.push(1);
	q.push(2);
	q.push(3);
	
	q.pop();
	q.push(4);
	q.pop();
			
	while(!q.empty())
	{
		cout << q.front()<< " ";
		q.pop();
	}
	//3 4
	return 0;
}
```


##  Priority Queue  
[c++ priority queue](https://en.cppreference.com/w/cpp/container/priority_queue).  

* When each data is inserted, the priority number of the data is put together   
* The structure in which the order of extracting data differs according to the priority given when inserting data  
{% highlight c++ %}
#include <iostream>
#include <queue>
using namespace std;


int main()
{
    priority_queue<int> pq;

    pq.push(10);      
    pq.push(20);
    pq.push(15);
    pq.push(12);

    cout << pq.top() << endl; // 20    
    pq.pop();
    cout << pq.top() << endl; // 15   
}
{% endhighlight %}

##  큐의 활용  
* Queue is used for multitasking in the operating system  
* Like buffer, queue coordinates the interaction between two process scheduling running at different speeds  
