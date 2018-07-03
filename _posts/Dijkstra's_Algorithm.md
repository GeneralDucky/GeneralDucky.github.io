---
layout: post
title: Dijkstra's Algorithm
---

Dijkstra's Algorithm, invented by famous computer scientist E.W. Dijkstra, is an algorithm used to find the shortest path between 2 points on a **weighted graph**.  
A weighted graph is a graph in which the each edge is associated with a numerical value. Depending on the context, that value can represent the cost of traversing the edge, the length of the edge, etc.  

We'll suppose that our starting node is Node *s* and the target node is Node *t*. For every node *n*, dist[n] will represent the length of the shortest known path from *s* to *n*.

Before we have done anything, dist[*s*] should be set to 0, since the distance from *s* to *s* will always be 0. Because we do not know anything about the other nodes, they should have a dist[] value of positive infinity.

