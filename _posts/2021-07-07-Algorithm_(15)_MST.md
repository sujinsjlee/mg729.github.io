---
title: "Algorithm - Handling MST"
categories:
  - Algorithm
tags:
  - Algorithm
public: false
---

> **MST** *Minimun Spanning Tree*


    
## Kruskal

- **Kruskal's Algorithm 크루스칼 알고리즘** 
    - 그래프에서 최소비용 트리 만드는 것
    - 크루스칼 알고리즘이란, 그래프 내의 모든 정점들을 가장 적은 비용으로 연결하기 위해 사용, 그래프 내의 모든 정점을 포함하고 **사이클이 없는 연결 선**을 그렸을 때, 가중치의 합이 최소가 되는 상황을 구하고 싶을 때 크루스칼 알고리즘을 사용

    - SOLUTION : UnionFind 
        - *Point* : 우선 간선의 가중치를 기준으로 작은순으로 오름차순 정렬해서 정점이 서로소집합을 만족하는 경우에만 정점을 포함
    
## Prim

- **Prim Algorithm** : 정점을 추가하는 방식
    - MST 최소비용신장트리를 만드는데 간선을 선택하는 것이 아니라 임의의 정점을 하나 선택
    - 거기서부터 계속 그래프의 연결관계를 보면서 정점을 하나씩추가
    - 정점을 추가하면서 트리를 확장
    - 정점이 N개가 완성되면 트리가 완성되는 것

    - SOLUTION : priority_queue - 최소힙활용 
- **prim & kruskal 차이**
    - 프림 알고리즘은 꼭지점(정점)을 선택하고 그것과 연결된 가장 적은 비용의 **정점을 선택**
    - 크루스칼 알고리즘은 모든 비용을 순차적으로 나열하여 가장 적은 비용이 드는 **간선(신장)들을 선택**
