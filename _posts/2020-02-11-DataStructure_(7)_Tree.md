---
layout: post
title: Data Structure - (7) 트리
description: (7) Understanding of Tree
modified: 2020-02-11
tags: [Data Structure, Tree]
categories: [DataStructure]
published:false
---

<!--트리는 면접에서 가장 자주 물어보는 자료구조-->

## 트리 구조  
> **트리** : Node 와 Edge (branch) 를 이용해서, 사이클을 이루지 않도록 구성한 데이터 구조   
> tree는 **계층적 자료구조**(hierarchical structure)  
> stack, queue, list 의 자료구조는 *선형자료구조*(Linear data structure)  


* 주요 용도  
    * 트리 중 이진 트리 형태의 구조로, 탐색(검색)알고리즘 구현을 위해 많이 사용됨  

## Term  
* **Node** : 트리에서 데이터를 저장하는 기본 요소(데이터와 다른 연결된 노드에 대한 edge 정보 포함)  
* **Edge (branch) - 간선** : 노드들 간의 연결 선  
* **Root Node** : 트리 맨 위에 있는 노드  
* **Parent node** : 노드의 상위레벨에 연결된 노드  
* **Child node** : 노드의 다음 레벨에 연결된 노드  
* **Terminal node (Leaf node)** : Child node가 하나도 없는 노드  
* **Sibling** : 동일한 Parent node를 가진 노드  
* **Level** : 트리에서 각 층의 번호를 매기는 것 - 루트의 레벨은 1, 한 층씩 내려갈 수록 1씩 증가    
* **Depth** : 트리에서 node가 가질 수 있는 최대 level  
* **Degree - 차수** : 노드가 가지고 있는 자식노드의 개수  
<!--https://www.mathwarehouse.com/programming/gifs/binary-search-tree.php-->


## 이진트리와 이진 탐색트리
> **이진트리 (Binary Tree)** : 노드의 최대 edge 가 2인 트리  
  
> **이진 탐색 트리 ( Binary Search Tree) - BST** : 이진 트리에 다음과 같은 추가 조건이 있는 트리  
> *왼쪽 노드는 해당 노드보다 작은 값, 오른쪽노드는 해당 노드보다 큰 값을 가지고 있음*  
  

* 이진 탐색 트리의 **<u>장점</u>**  
    * 탐색 속도를 개선할 수 있음  
	* 빠른 검색이 가능  
		* 배열 탐색시간 - O(n)  
		* 트리 탐색시간 - O(log n)  

* 이진 탐색 트리의 **<u>주요 용도</u>**  
    * 데이터 검색(탐색)  
	
* 이진 탐색 트리의 **<u>시간 복잡도 </u>**  
	* **O(log n)**  
		* 빅오 표기법에서 log n 의 밑은 10이 아니라 2  
		* 한 번 실행시마다, 50%의 실행할 수도 있는 탐색경우의 수를 제거한다는 의미  
		* 50%의 실행시간을 단축  

	log n의 시간 복잡도에 대한 증명
	1. n 의 크기를 반씩 줄이는 걸 가정
	n 이 반씩 줄다보면 k 단계에서 최종적으로 1이 된다 가정하자.
	2. 단계별로 n -> n/2 -> n/4 -> n/2의k 승 진행
	3. n = 2 의 k 승
	4. 양쪽에 로그 붙이면 logN = k 가 됨.  
	{: .notice--success}

*  이진 탐색 트리의 **<u>단점</u>**  
	* 평균 시간 복잡도는 O(log n)이지만, 이는 트리가 균형이 잡혀있을 때의 평균시간 복잡도  
	* 최악의 경우는 링크드 리스트와 동일한 성능을 보여줌 O(n)  
	![https://www.quora.com/What-is-the-worse-case-time-complexity-for-a-binary-search-tree-for-searching](https://qph.fs.quoracdn.net/main-qimg-eccb472654af69385afe691e9958a713.webp)
	[quora.com - worst case time complexity](https://www.quora.com/What-is-the-worse-case-time-complexity-for-a-binary-search-tree-for-searching)  
	
## C++ code
> [노드 클래스 만들기 - 링크드 리트스 활용](#tree_code)  
> [이진 탐색 트리 - Insert Data](#insert_data_in_tree)  
> [이진 탐색 트리 - Search](#search_tree)  
> [이진 탐색 트리 - Delete](#delete_data_in_tree)  

* 트리에서 데이터와 브랜치(edge) 값을 관리하기 위해서는 트리 자료구조를 구현할때 **링크드 리스트**를 활용하는 것을 권장
## tree_code

## insert_data_in_tree  

## search_tree  

## delete_data_in_tree  
 
## 이진 탐색 트리 삭제

### Case 1. Leaf Node 삭제
삭제할 node의 parent node가 삭제할 node를 가리키지 않도록함  
parent node의 edge에 nullptr 대입  

### Case 2. Child Node가 하나인 Node 삭제
삭제할 노드의 parent node가 삭제할 노드의 child node를 가리키도록 함  

### Case 3. Child Node가 두 개인 Node 삭제 
**option1. 삭제할 Node의 오른쪽 자식 중, 가장 작은 값을 삭제할 Node의 Parent Node가 가리키도록 함**  
option2. 삭제할 Node의 왼쪽 자식 중, 가장 큰 값을 삭제할 Node의 Parent Node가 가리키도록 함  

#### Case 3-1. 삭제할 Node가 Parent Node의 왼쪽에 있을 때  

#### Case 3-2. 삭제할 Node가 Parent Node의 오른쪽에 있을 때  

## C++ 전체 코드
```cpp
```