---
layout: post
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
	<a href="https://en.wikipedia.org/wiki/Depth-first_search">
		<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1f/Depth-first-tree.svg/450px-Depth-first-tree.svg.png"/>
	</a>
</center>


## DFS Algorithm  
- Utilize *Queue* and *Stack*    
	- Create two queues: need_visit, visited  
		- need_visit is implemented with **stack**  
		- visited is implemented with **queue**  
​
- Note that the BFS data structure uses two queues, while **DFS uses a stack and a queue.**  


## Time Complexity
- DFS Time Complexity  
	- Number of Vertexes: V  
	- Number of Edges: E  
	- Time Complexity: **O(V + E)**  

## C++ 
```cpp
#include <iostream>
#include <cstdio> 
#include <vector>

using namespace std;

int number = 7;
int visited[8];
vector<int> need_visit[8];
 
void dfs(int start)
{
	if(visited[start])
		return;
	visited[start] = true;
	cout << start << " ";
	
	for(int i = 0; i < need_visit[start].size(); ++i)
	{
		int next_index = need_visit[start][i];
		dfs(next_index);
	}
}

int main()
{
	need_visit[1].push_back(2);
	need_visit[2].push_back(1);
	
	need_visit[2].push_back(3);
	need_visit[3].push_back(2);
	
	need_visit[3].push_back(4);
	need_visit[4].push_back(3);
	
	need_visit[3].push_back(5);
	need_visit[5].push_back(3);

	need_visit[2].push_back(6);
	need_visit[6].push_back(2);
	
	need_visit[1].push_back(7);
	need_visit[7].push_back(1);
	
	need_visit[1].push_back(8);
	need_visit[8].push_back(1);
	
	need_visit[8].push_back(9);
	need_visit[9].push_back(8);

	need_visit[9].push_back(10);
	need_visit[10].push_back(9);	
		
	need_visit[9].push_back(11);
	need_visit[11].push_back(9);
	
	need_visit[8].push_back(12);
	need_visit[12].push_back(8);
	
	dfs(1);
	
	return 0;
}
```

* **Recursive call works as <u>Stack</u>**  

