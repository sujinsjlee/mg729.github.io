---
layout: post
title: Data Structure - (5) 연결 리스트
description: (5) Understanding of Linked List
modified: 2020-01-14
tags: [Data Structure, Linked List]
categories: [Data Structure]
---

##  Linked List (연결리스트의 구조)
![Singly Linked List 단순 연결 리스트](https://en.wikipedia.org/wiki/Linked_list#/media/File:Singly-linked-list.svg?sanitize=true)

> **동적으로 크기가 변할 수 있고 삭제나 삽입 시에 데이터를 이동할 필요가 없는 구조**  
<ul>
<li>배열의 단점을 해결하는 자료구조</li>
<ul>  
<li>배열은 연결된 저장공간으로 미리 크기가<u>고정</u>된 데이터 구조</li>  
<li>이에 반해서 Linked List 는 미리 크기를 고정하지 않고 필요할때마다 <u>동적으로</u> 추가,삭제가 가능한 데이터구조</li> 
</ul> 
</ul>

<ul>
 <li> <b>노드(node)</b> : 데이터 저장단위 (데이터, 포인터로 구성) </li>
 <li> <b>포인터(pointer)</b> : 노드 안에서 노드의 다음 데이터에 대한 연결 정보(주소값)를 가지고 있는 공간 </li>
</ul>

<ul>
<li>Linked List 의 마지막 노드의 포인터는 <b>nullptr</b>로 설정</li>  
<ul><li>더이상 연결된 노드가 없다는 것을 의미</li></ul>
</ul>  

##  Linked List 의 장단점
1. 장점  
   * 미리 데이터 공간을 할당하지 않아도 됨  
2. 단점  
   * 저장 효율이 높지 않음 (데이터 뿐만아니라 연결을 위한 포인터 주소공간도 필요하므로)  
   * 연결정보를 찾는 시간이 필요하므로 접근 속도가 느림  
   * 중단 데이터 삭제시, 앞뒤 데이터의 연결을 재구성해야함  



## Node 구현
1. Struct를 이용하여 Node만들기    

```c++  
#incldue <iostream>
using namespace std;

struct node
{
    int data;
    node *next;
}
```  

2. Class를 이용하여 linked_list 만들기  
* linked list에서 first node는 반드시 알고 있어야합니다.      
    * first node를 통해서 전체 list에 접근하므로    
    * first node를 **head**라고 함   

```c++  
#include <iostream>
using namespace std;

struct node
{
    int data;
    node *next;
}; //expected ';' after struct definition 

class LinkedList
{
    private:
        node *head, *tail;
    public:
        LinkedList()
        {
            head = nullptr;
            tail = nullptr;
        }
}; //expected ';' after class definition 

int main()
{
    LinkedList l;
    return 0;
}
```    

## Linked List - 데이터 **추가**하기
```c++
#include <iostream>
using namespace std;

struct node
{
    int data;
    node *next;
};

class LinkedList
{
private:
    node *head, *tail;
public:
    LinkedList()
    {
        head = nullptr;
        tail = nullptr;
    }
    void add_node(int n)
    {
    	node *temp = new node; //By new operator, allocate the space for the node
    	                       //Now, 'temp' points to a node
    	temp->data = n;        //input the value 'n' to the 'data' of 'temp'
    	temp->next = nullptr;  //represent that node is the last node --> pointer address will be nullptr 
    	
    	if(head == nullptr)  //no linked list yet, so current node will be the 'head' and 'tail' both.
    	                     // as it is the last element right now
    	{
    		head = temp;
    		tail = temp;
		}
		else  //already have a linked list and we have to add the node at the end of the linked list.
		{
			tail->next = temp;  //new node(temp) will go after 'tail'
			tail = tail->next; //new node is the new 'tail'
		}
	}
};

int main()
{
    LinkedList l;
    l.add_node(10);
    l.add_node(20);
    return 0;
}
```  
`node *temp = new node;` :  By new operator, allocate the space for the node  


## Linked List - 데이터 **출력**하기
```c++
#include <iostream>
using namespace std;

struct node
{
	int data;
	node* next; 	
};

class LinkedList
{
private:
	node *head, *tail;
public:
	LinkedList()
	{
		head = nullptr;
		tail = nullptr;
	}
	void add_node(int n)
	{
//		node *temp; 
//		note *temp = new node;
/*
node *temp; -> node *타입의 temp변수선언
node *temp = new node; -> node 객체 생성 : 메모리할당 + 생성자 호출 
*/
		node *temp = new node; 
		temp->data = n;
		temp->next = nullptr;
		
		if(head == nullptr)
		{
			head = temp;
			tail = temp;
		}
		else
		{
			tail->next = temp;
			tail = tail->next;
		}		
	}
	void distplay()
	{
		node *temp;
		temp = head;  //temp = this->head;
		while(temp != nullptr)
		{
			cout << temp->data << endl;
			temp = temp->next;
		}
	}	
};

int main()
{
    LinkedList l;
    l.add_node(10);
    l.add_node(20);
    l.distplay();
    return 0;
}
``` 

## Node 와 Node **연결**하기
```c++
/*
Concatenating or joining two linked lists 

1. Traverse over the linked list ‘a’ until the element next to the node is not NULL.
2. If the element next to the current element is NULL (a->next == NULL) then change the element next to it to ‘b’ (a->next = b).

*** static 멤버 함수
http://soen.kr/lecture/ccpp/cpp3/27-3-3.htm 

*/
#include <iostream>
using namespace std;

struct node
{
	int data;
	node* next; 	
};

class LinkedList
{
private:
	node *head, *tail;
public:
	LinkedList()
	{
		head = nullptr;
		tail = nullptr;
	}
	void add_node(int n)
	{
//		node *temp; 
//		note *temp = new node;
/*
node *temp; -> node *타입의 temp변수선언
node *temp = new node; -> node 객체 생성 : 메모리할당 + 생성자 호출 
*/
		node *temp = new node; 
		temp->data = n;
		temp->next = nullptr;
		
		if(head == nullptr)
		{
			head = temp;
			tail = temp;
		}
		else
		{
			tail->next = temp;
			tail = tail->next;
		}		
	}
	
	node *gethead()
	{
		return head;
	}
	
	void distplay()
	{
		node *temp = head;
		while(temp != nullptr)
		{
			cout <<temp->data <<endl;
			temp = temp->next;
		}
	}
	
	static void concatenate(node* a, node* b)
	{
		if( a!= nullptr && b != nullptr)
		{
			if(a->next == nullptr)
			{
				a->next = b;
			}
			else
			{
				concatenate(a->next, b);
			}
		}
		else
		{
			cout << "Both nodes are nullptr" <<endl;	
		}	
	}	
};

int main()
{
    LinkedList la;
    la.add_node(10);
    la.add_node(20);
    la.distplay();
    
    LinkedList lb;
    lb.add_node(30);
    lb.add_node(40);
    lb.distplay();
    
    LinkedList::concatenate(la.gethead(),lb.gethead());
    la.distplay();
    
    return 0;
}
``` 

## Linked List - 데이터 사이에 데이터 추가하기 
- 연결 재구성

```c++
/*
Concatenating or joining two linked lists 

1. Traverse over the linked list ‘a’ until the element next to the node is not NULL.
2. If the element next to the current element is NULL (a->next == NULL) then change the element next to it to ‘b’ (a->next = b).

*** static 멤버 함수
http://soen.kr/lecture/ccpp/cpp3/27-3-3.htm 

*/
#include <iostream>
using namespace std;

struct node
{
	int data;
	node* next; 	
};

class LinkedList
{
private:
	node *head, *tail;
public:
	LinkedList()
	{
		head = nullptr;
		tail = nullptr;
	}
	void add_node(int n)
	{
//		node *temp; 
//		note *temp = new node;
/*
node *temp; -> node *타입의 temp변수선언
node *temp = new node; -> node 객체 생성 : 메모리할당 + 생성자 호출 
*/
		node *temp = new node; 
		temp->data = n;
		temp->next = nullptr;
		
		if(head == nullptr)
		{
			head = temp;
			tail = temp;
		}
		else
		{
			tail->next = temp;
			tail = tail->next;
		}		
	}
	
	node *gethead()
	{
		return head;
	}
	
	void distplay()
	{
		node *temp = head;
		while(temp != nullptr)
		{
			cout <<temp->data <<endl;
			temp = temp->next;
		}
	}
	
	void concatenate(node* a, node* b)
	{
		if( a!= nullptr && b != nullptr)
		{
			if(a->next == nullptr)
			{
				a->next = b;
			}
			else
			{
				concatenate(a->next, b);
			}
		}
		else
		{
			cout << "Both nodes are nullptr" <<endl;	
		}	
	}	
	
	void front(int n)
	{
		node * temp = new node;
		temp->data = n;
		temp->next = head;
		head = temp;
	}
	
	void after(node *a, int value)
	{
		node * temp = new node;
		temp->data = value;
		temp->next = a->next;
		a->next = temp;
	}
};

int main()
{
    LinkedList la;
    la.add_node(10);
    la.add_node(20);
    
    la.front(30);
    
    la.distplay();
    
    return 0;
}
``` 


## Linked List - 데이터 **삭제**하기
```c++
/*
Concatenating or joining two linked lists 

1. Traverse over the linked list ‘a’ until the element next to the node is not NULL.
2. If the element next to the current element is NULL (a->next == NULL) then change the element next to it to ‘b’ (a->next = b).

*** static 멤버 함수
http://soen.kr/lecture/ccpp/cpp3/27-3-3.htm 

*/
#include <iostream>
using namespace std;

struct node
{
	int data;
	node* next; 	
};

class LinkedList
{
private:
	node *head, *tail;
public:
	LinkedList()
	{
		head = nullptr;
		tail = nullptr;
	}
	void add_node(int n)
	{
//		node *temp; 
//		note *temp = new node;
/*
node *temp; -> node *타입의 temp변수선언
node *temp = new node; -> node 객체 생성 : 메모리할당 + 생성자 호출 
*/
		node *temp = new node; 
		temp->data = n;
		temp->next = nullptr;
		
		if(head == nullptr)
		{
			head = temp;
			tail = temp;
		}
		else
		{
			tail->next = temp;
			tail = tail->next;
		}		
	}
	
	node *gethead()
	{
		return head;
	}
	
	void distplay()
	{
		node *temp = head;
		while(temp != nullptr)
		{
			cout <<temp->data <<endl;
			temp = temp->next;
		}
	}
	
	void concatenate(node* a, node* b)
	{
		if( a!= nullptr && b != nullptr)
		{
			if(a->next == nullptr)
			{
				a->next = b;
			}
			else
			{
				concatenate(a->next, b);
			}
		}
		else
		{
			cout << "Both nodes are nullptr" <<endl;	
		}	
	}	
	
	void front(int n)
	{
		node * temp = new node;
		temp->data = n;
		temp->next = head;
		head = temp;
	}
	
	void after(node *a, int value)
	{
		node * temp = new node;
		temp->data = value;
		temp->next = a->next;
		a->next = temp;
	}
	
	void deleteNode(node *beforeNode)
	{
		node* temp;
		temp = beforeNode->next;
		beforeNode->next = temp->next;
		delete temp; 
	}
};

int main()
{
    LinkedList la;
    la.add_node(10);
    la.add_node(20);
    
    la.front(30);
    
    la.add_node(40);
    la.add_node(50);
    
    la.after(la.gethead()->next->next->next, 10);
	la.deleteNode(la.gethead()->next);
	 
    la.distplay();
    
    return 0;
}
``` 

## Linked List - 데이터 검색 (search_Node) 
```c++

```

##  **Singly** Linked List - C++ Container library  
[c++ **forward_list**(*singly linked list*)](https://en.cppreference.com/w/cpp/container/forward_list).  

```c++

```

---
---
---

##  Doubly Linked List 이중 연결 리스트 
![Doubly Linked List 다중 연결 리스트](https://en.wikipedia.org/wiki/Linked_list#/media/File:Doubly-linked-list.svg?sanitize=true)

* 더블 링크드 리스트 (Doubly Linked list) 구조  
   * singly linked list는 데이터 탐색시 head 노드부터 tail까지 탐색을 해야함 -> 원하는 데이터가 뒤에 있다면?
     * <u>노드 탐색이 <b>양쪽</b>으로 가능한</u> *Double Linked list*    
   * 더블 링크드 리스트의 Node의 구조는 **이전데이터주소 , 데이터, 다음 데이터 주소** 로 이루어져있음     
  

##  **Doubly** Linked List - C++ Container library  
[c++ **list** (*doubly linked list*)](https://en.cppreference.com/w/cpp/container/list).  
```c++
#include <algorithm>
#include <iostream>
#include <list>
using namespace std;

int main()
{
    // Create a list containing integers
    list<int> l = { 7, 5, 16, 8 };
 
    // Add an integer to the front of the list
    l.push_front(25);
    // Add an integer to the back of the list
    l.push_back(13);
 
    // Insert an integer before 16 by searching
    auto it = find(l.begin(), l.end(), 16);
    if (it != l.end()) {
        l.insert(it, 42);
    }
 
    // Iterate and print values of the list
    for (int n : l) {
        cout << n << '\n';  //25, 7, 5, 42, 16, 8, 13
    }
    
    l.pop_front();
    for (int n : l) {
        cout << n << '\n';  //7, 5, 42, 16, 8, 13
    }
    
    l.pop_back();
    for (int n : l) {
        cout << n << '\n';  //7, 5, 42, 16, 8
    }
}
```

