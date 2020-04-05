---
layout: post
published: false
title: Algorithm - Greedy algorithm (Concept, Coin Exchange Problem and C++)
description: (11) Understanding of Greedy algorithm
modified: 2020-04-04
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---

## ## 1. What is the greed algorithm?
> Problem solving method for uploadsed for getting a value close to the optimal solution  
> Whenever you need to decide between one of several cases, **select the case that you think is the best every moment** and get the final value  
> **Selecting the best case for each step when there are multiple cases**  


## 2. 탐욕 알고리즘의 한계
- 탐욕 알고리즘은 근사치 추정에 활용  
- 반드시 최적의 해를 구할 수 있는 것은 아니기 때문  
- 최적의 해에 가까운 값을 구하는 방법 중의 하나임  

<center>
	<a href="https://en.wikipedia.org/wiki/Greedy_algorithm">
		<img src="https://upload.wikimedia.org/wikipedia/commons/8/8c/Greedy-search-path-example.gif"/>
	</a>
</center>

- '시작' 노드에서 시작해서 가장 큰 값을 찾아 leaf node 까지 가는 경로를 찾을 시에
  - Greedy 알고리즘 적용시 7 -> 12 -> 6 를 선택하게 되므로 7 + 12 +6 = 25 가 됨 
  - 하지만 실제 가장 큰 값은 7 -> 3 -> 99 이며, 7 + 3 + 99 = 109 가 답



## 3. 탐욕 알고리즘 예  

### 동전 문제  
- 지불해야 하는 값이 4720원 일 때 1원 50원 100원, 500원 동전으로 동전의 수가 가장 적게 지불하시오.  
	- 가장 큰 동전부터 최대한 지불해야 하는 값을 채우는 방식으로 구현 가능  
	- 탐욕 알고리즘으로 매순간 최적이라고 생각되는 경우를 선택하면 됨  


#### C++

```cpp

```
