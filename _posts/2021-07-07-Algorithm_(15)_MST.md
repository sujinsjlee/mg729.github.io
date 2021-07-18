---
title: "Algorithm - Handling MST"
categories:
  - Algorithm
tags:
  - Algorithm
---

> **MST** *Minimun Spanning Tree*

    
## Kruskal
    
- **Kruskal's Algorithm**
     - Creating the least cost tree from the graph
     - Kruskal's algorithm is used to connect all vertices in the graph with the lowest cost, and finds a situation where the sum of weights is the minimum when a connecting line with no cycles is drawn including all vertices in the graph. Use Kruskal's Algorithm

     - SOLUTION : UnionFind
         - *Point* : First, based on the weight of the edges, sort the vertices in ascending order, and include vertices only if the vertices satisfy each other's subset.
## Prim

- **Prim Algorithm** : method of adding vertices
     - To construct the MST minimum cost spanning tree, we do not select an edge, but select a random vertex.
     - From there, continue to add vertices one by one while watching the connection relationship of the graph.
     - Expand the tree while adding vertices
     When number of vertices are completed as N, the tree is completed.

     - SOLUTION : priority_queue - UseMinimum heap


- **prim & kruskal difference**
     - Prim's algorithm selects a vertex and selects the lowest cost **vertex associated with it**
     - Kruskal's algorithm lists all costs sequentially and selects the lowest cost **edges (kidneys)**