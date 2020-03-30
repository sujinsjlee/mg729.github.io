---
layout: post
title: Algorithm - BFS (Concept, BFS using queue and Time Complexity)
description: (8) Understanding of BFS
modified: 2020-03-26
tags: [Algorithm]
categories: [Algorithm]
use_math: true
---
## BFS (Breadth-First Search)   
> * Main graph **Search** algorithm  
> **BFS (Breadth First Search): Search for brother nodes at the same level of the vertex first**  
> DFS (Depth First Search): search for the children of vertex first  


<center>
	<a href="https://en.wikipedia.org/wiki/Breadth-first_search">
		<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/33/Breadth-first-tree.svg/450px-Breadth-first-tree.svg.png"/>
	</a>
</center>


## BFS Algorithm  
- Utilize *Queue*    
	- Create two queues: need_visit, visited    

## Time Complexity
- BFS Time Complexity  
	- Number of Vertexes: V  
	- Number of Edges: E  
	- Time Complexity: **O(V + E)**  

## C++ 
```cpp
#include<iostream>
#include<cstdio>
#include<vector> //to store data
#include<queue>

using namespace std;

int number = 7;
int visited[7]; 
vector<int> need_visit[8];
 
void bfs(int start)
{
	queue<int> q;
	q.push(start);
	
	visited[start] = true;
	while(!q.empty())
	{
		int x = q.front();
		q.pop();
		printf("%d ", x);
		
		for(int i = 0; i < need_visit[x].size(); ++i)
		{
			int y = need_visit[x][i];
			if(!visited[y])
			{
				q.push(y);
				visited[y] = true;
			}
		}
	}
}
int main()
{
	need_visit[1].push_back(2);
	need_visit[2].push_back(1);
	
	need_visit[1].push_back(3);
	need_visit[3].push_back(1);
	
	need_visit[1].push_back(4);
	need_visit[4].push_back(1);
	
	need_visit[2].push_back(5);
	need_visit[5].push_back(2);

	need_visit[2].push_back(6);
	need_visit[6].push_back(2);
	
	need_visit[4].push_back(7);
	need_visit[7].push_back(4);
	
	need_visit[4].push_back(8);
	need_visit[8].push_back(4);
	
	need_visit[5].push_back(9);
	need_visit[9].push_back(5);

	need_visit[5].push_back(10);
	need_visit[10].push_back(5);	
		
	need_visit[7].push_back(11);
	need_visit[11].push_back(7);
	
	need_visit[7].push_back(12);
	need_visit[12].push_back(7);
	
	bfs(1);
	
	return 0;
}
```
* **int visited[7];**   
	* all elements are initialized with 0  
* <code><b>vector<int> need_visit[8];</b></code>   
	* index starts from *1*  

