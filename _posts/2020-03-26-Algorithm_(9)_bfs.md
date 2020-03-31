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
#include<vector> //to store data
#include<queue>

using namespace std;


int visited[13];
vector<int> graph[13];
 
void bfs(int start)
{
	queue<int> need_visit;
	
	need_visit.push(start);
	visited[start] = true;
	
	while(!need_visit.empty())
	{
		int x = need_visit.front();
		cout << x << " ";
		need_visit.pop();
		
		for(int i = 0; i < graph[x].size() ; ++i)
		{
			int y = graph[x][i];
			if(!visited[y])
			{
				need_visit.push(y);
				visited[y] = true;
			}
		}
	}
}
int main()
{
	graph[1].push_back(2);
	graph[2].push_back(1);
	
	graph[1].push_back(3);
	graph[3].push_back(1);
	
	graph[1].push_back(4);
	graph[4].push_back(1);
	
	graph[2].push_back(5);
	graph[5].push_back(2);

	graph[2].push_back(6);
	graph[6].push_back(2);
	
	graph[4].push_back(7);
	graph[7].push_back(4);
	
	graph[4].push_back(8);
	graph[8].push_back(4);
	
	graph[5].push_back(9);
	graph[9].push_back(5);

	graph[5].push_back(10);
	graph[10].push_back(5);	
		
	graph[7].push_back(11);
	graph[11].push_back(7);
	
	graph[7].push_back(12);
	graph[12].push_back(7);	
	
	bfs(1);
	
	return 0;
}
```
`int visited[13];`   
	- all elements are initialized with 0  
`vector<int> graph[13];`  
	- index starts from *1*  

