---
title: "Algorithm - Dijkstra"
categories:
  - Algorithm
tags:
  - Algorithm
public: false
---

- Dijkstra's algorithm is a representative shortest path search algorithm using dynamic programming.
    - **Dynamic programming**: When it is difficult to solve a large problem at once, it is a technique to divide it into several small problems
- Commonly used most often in satellite GPS software, etc.
- When finding one shortest distance, the shortest distance information obtained before is used as it is.

<!--- **다익스트라**
    - 출발노드를 설정
    - 출발노드를 기준으로 각 노드의 최소비용을 저장
    - 방문하지 않은 노드 중에서 가장 적은 비용의 노드를 선택
    - 해당노드를 거쳐서 특정한 노드로 가는 경우를 고려하여(이 때 이전까지 구했던 최단 거리정보를 활용하여) 최소 비용을 갱신-->
- **Dijkstra**
    - Set the starting node
    - Store the minimum cost of each node based on the starting node
    - Select the least expensive node among the unvisited nodes
    - In consideration of the case of going to a specific node through the corresponding node (at this time, using the shortest distance information obtained before), the minimum cost is updated
- EXAMPLE

```c++

#include<bits/stdc++.h>

using namespace std;

int n, m, a, b, e;

struct Graph{
	int vertex;
	int edge;
	Graph(int ve, int ed) {
		vertex = ve;
		edge = ed;
	}
	bool operator < (const Graph& cmpGraph) const {
		return edge > cmpGraph.edge;
	}
};

int main() {
	ios::sync_with_stdio(false);
	cin.tie(nullptr);
	
	freopen("input.txt", "rt", stdin);
	
	cin >> n >> m;
	vector<Graph> v[22];
	for(int i = 0; i < m; i++) {
		cin >> a >> b >> e;
		v[a].push_back({b,e});
	}

	vector<int> cost(22, 2147000000); // need to initialize all the data as 2147000000 by vector
	
	priority_queue<Graph> pq;
	pq.push({1, 0});
	cost[1] = 0;
	
	// below while code is Dijkstra algorithm
	while(!pq.empty()){
		int curNode = pq.top().vertex;
		int curCost = pq.top().edge;
		pq.pop();
		if(cost[curNode] < curCost) continue;
		for(int i = 0; i < v[curNode].size(); i++) {
			int nextNode = v[curNode][i].vertex;
			int nextCost = curCost + v[curNode][i].edge;
			if(nextCost < cost[nextNode]) {
				cost[nextNode] = nextCost;
				pq.push({nextNode, nextCost});
			}
		}
	}
	
	for(int i = 2 ; i <= n; i++) {
		if(cost[i] == 2147000000) cout <<"impossible";
		else cout << i << " : " << cost[i] << "\n";
	}

 	return 0;
}

```