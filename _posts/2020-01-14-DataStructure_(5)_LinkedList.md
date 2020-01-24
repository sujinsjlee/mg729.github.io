---
layout: post
title: Data Structure - (5) 연결 리스트
description: (5) Understanding of Linked List
modified: 2020-01-14
tags: [Data Structure, Linked List]
categories: [Data Structure]
---

##  Linked List (연결리스트의 구조)
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

```c++

```