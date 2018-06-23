---
layout: post
title: Eularian Path
---
#### Intro
An **Eulerian Path**, named after mathematician Leonhard Euler, is a traveral of a graph that visits each edge exactly once.  
The famous 7 Bridges of Konigsberg problem, first solved by Euler, gave rise to the idea of an Eulerian Path, and was the foundation of modern graph theory.  
The city of Konigsberg contained 7 bridges. Citizens would attempt to walk around the city while traversing the bridges only once.  
Below is a simplified version of Koningsberg  

![](/images/Pic5.PNG)

In order to solve the the 7 Bridges of Konigsberg problem, we'll need to make a few observations.  
Let's examine the following picture:  

![](/images/Pic5.1.PNG)

Suppose we've started our walk on a different node than the one shown in Picture 2.  
If we want to traverse every edge, then we will have to use 1 edge to reach Node 1, 1 edge to leave Node 1, and 1 edge to come back to Node 1 again.  
However, we are now stuck at Node 1; we don't have any other edges to use so we can leave again.  

We have a few ways we can correct this problem.  
1. We could start our traversal at Node 1. An Eularian path does not have to start and end at the same node. This means that we could potentially leave Node 1 one more time than we revisit it, so the fact that Node 1 has an odd degree is not a problem. Similarly, we could also end our traversal at Node 1. 
2. We could also add or take away edges from Node 1 until Node 1 has an even degree. An even degree allows each incoming edge to have a corresponding outgoing edge so that we don't get stuck at Node 1.  
  
Using these observations, we can now identify what conditions are necessary for an Eularian path to exist.  
Since we can only have 1 starting node and 1 ending node, we can have at most 2 nodes with an odd degree.  
All other nodes must have an even degree.  
Finally, we need to make sure the entire graph is connected. Otherwise, we may not be able to reach some edges, even if the above conditions are met.

Now, we can identify whether the 7 Bridges of Koningsberg has a solution.  
We note that all nodes in the graph representation of Konigsberg has a degree of 3. Thus, the 7 Bridges of Koningsberg has no solution

#### Fleury's Algorithm
Our ideas above tell us if there exists an Eulerian path, but it doesn't tell us what the path actually is. Fleury's Algorithm is a method that identifies 1 possible path.  
First, we check to see if there are any nodes with odd degree.  
If there are exactly 2 nodes with odd degree, we choose one of them as the starting node for the Eularian path.  
Otherwise, if there are 0 nodes with odd degree, we can pick any node as the starting point.  
At each step, we pick an arbitrary edge of the current node and traverse to the other endpoint, then delete the edge. However, we need to be careful not to traverse any **bridges**. A bridge is an edge that, if removed, causes the graph to become disconnected. We can identify bridges with Tarjan's Algorithm for Bridges.  
We should only traverse bridges if we don't have a choice (i.e. the only edge left is a bridge). Otherwise, we should always traverse non-bridge edges.  





