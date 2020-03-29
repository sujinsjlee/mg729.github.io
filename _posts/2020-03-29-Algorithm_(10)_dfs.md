---
layout: post
published: false
title: Algorithm - DFS (Concept, Time Complexity and C++)
description: (8) Understanding of DFS
modified: 2020-03-29
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---
## DFS (Depth First Search)   
> * Main graph **Search** algorithm  
> BFS (Breadth First Search): Search for brother nodes at the same level of the vertex first  
> **DFS (Depth First Search): search for the children of vertex first**  


<center>
	<a href="https://en.wikipedia.org/wiki/Breadth-first_search">
		<img src="https://upload.wikimedia.org/wikipedia/commons/4/46/Animated_BFS.gif"/>
	</a>
</center>


## DFS Algorithm  
- Utilize *Queue* and *Stack*    
	- Create two queues: need_visit, visited  
		- need_visit is implemented with **stack**  
		- visited is implemented with **queue**  
​
> Note that the BFS data structure uses two queues, while **DFS uses a stack and a queue.**  


## Time Complexity
- DFS Time Complexity  
	- Number of Vertexes: V  
	- Number of Edges: E  
	- Time Complexity: **O(V + E)**  

## C++ 
```cpp

```

