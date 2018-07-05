---
layout: post
title: Dijkstra's Algorithm
---
#### Algorithm description
Dijkstra's Algorithm, invented by famous computer scientist E.W. Dijkstra, is an algorithm used to find the shortest path between 2 points on a **weighted graph**. A weighted graph is a graph in which the each edge is associated with a numerical value. Depending on the context, that value can represent the cost of traversing the edge, the length of the edge, etc. Dijkstra's Algorithm only works when edge lengths are nonnegative. 

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
//This implentation runs in O(ElogV)
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
          v.dist = Math.min (v.dist , n.dist + E(n,v));  //Here, we will represent the edge length between n and v as E(n,v). 
          heap.add(v);
       }
    }
  }
}
//If target is reachable from start, target.dist should now contain the length of the shortest path from start to target.
```

![Graph1](/images/Pic7.PNG)  

#### Proof of Correctness
Dijkstra's Algorithm actually computes the shortest path length between the starting node and every other node. This is known as Single-Source Shortest Path (SSSP) problem. We will prove that Dijkstra's Algorithm solves SSSP.  

Notice that at the end of the while loop, all reachable nodes have been marked. Supposing that DIST[n] represents the actual shortest distance between node *n* and the starting node, we will prove that all marked nodes have the following property at every iteration of the while loop: DIST[n] = dist[n].

We will use the process of [induction](https://en.wikipedia.org/wiki/Mathematical_induction) in our proof.  
Our base case is when only the starting node is marked. Since dist[start] = 0, and DIST[start] = 0, we're good to go.

For the inductive step, the unmarked node with the smallest dist[] value is marked. Let's call this node *n*. We'll need to prove that dist[n] = DIST[n].

We'll prove this using contradiction. Let's suppose that dist[n] is the smallest dist[] value, but it could still be decreased. This means that there exists a node *v* such that dist[v] + E(v,n) < dist[n]. However, *v* must also be an unmarked node. This is because if *v* was marked, then the edge between *v* and *n* would have already been relaxed and dist[n] decreased. 

However, the statement dist[v] + E(v,n) < dist[n] cannot be true! Since all edge lengths are nonnegative, the previous statement would imply that dist[v] < dist[n]. However, our original assumption was that dist[n] was the smallest dist[] value among the unmarked nodes. Thus, it is impossible for dist[n] to be decreased further. We can conclude that dist[n] = DIST[n].

Since we mark the node with the smallest dist[] value at each iteration, all marked nodes have the property that dist[] = DIST[]. 
Thus, at the end, all nodes have a dist[] value that represents the shortest path length from the starting node. This completes our proof.




