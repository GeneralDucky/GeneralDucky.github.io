---
layout: post
title: Dijkstra's Algorithm
---

Dijkstra's Algorithm, invented by famous computer scientist E.W. Dijkstra, is an algorithm used to find the shortest path between 2 points on a **weighted graph**. A weighted graph is a graph in which the each edge is associated with a numerical value. Depending on the context, that value can represent the cost of traversing the edge, the length of the edge, etc.  

Dijkstra did not present an implentation in his original paper. We will present a common implentation of Dijkstra's Algorithm using a priority queue.  

We'll suppose that our starting node is Node *s* and the target node is Node *t*. For every node *n*, dist[n] will represent the length of the shortest known path from *s* to *n*.

Before we have done anything, dist[*s*] should be set to 0, since the distance from *s* to *s* will always be 0. Because we do not know anything about the other nodes, they should have a dist[] value of positive infinity. 

We then create a priority queue with only *s* inside. While the priority queue is not empty, we do the following procedure: 

While the priority queue is not empty, we remove the node with the smallest dist[] from the queue. Suppose this node is called *n*.

We mark *n* so that we know it has been visited. 
For each unmarked neighbor *v* of *n*, we do the following:
If dist[n] + E(n,v) < dist[v], then set dist[v] = dist[n] + E(n,v). Note that E(n,v) represents the length of the edge connecting *n* and *v*.  
This process is known as edge relaxation. When dist[v] is modified, we have essentially found a new shortest path to node *v*.

The Java implementation is below:
```java
//the array nodes[] will contain all nodes in the graph
public int dijkstra(Node start, Node target){         
  for(Node n : nodes[]){
    n.dist = Integer.MAX_VALUE;
  }
  start.dist = 0; 
  PriorityQueue<Node> heap = new PriorityQueue<Node>();
  heap.add(start);
  while(!heap.isEmpty()){
    Node n = heap.poll();
    n.marked = true;
    for(Node v : n.neighbors){
      if(v.marked == false){
          v.dist = Math.min (v.dist , n.dist + E(n,v));  //Here, we will use 
       }
    }
  }
}
