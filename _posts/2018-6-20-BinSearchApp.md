---
layout: post
title: USACO Gold 1 February 2005
keywords: 
  - USACO
  - Gold 1 2005
  - Binary Search
---
Let’s examine the [angry cow problem](https://www.spoj.com/problems/AGGRCOW/) from USACO Gold, February 2005 competition.

The input is quite large (100k), and in a competitive coding environment, this calls for a O(nlogn) solution. 

Let's make some observations that can help us solve this problem.

Suppose that we want to test a certain distance. The easiest way is to simply start at the leftmost stall, then place the next cow as far left as we can without violating the stall distance. We continue placing cows as far left as we can with respect to the rightmost placed cow. If we run out of cows before we run out of stalls, then we know that this distance works!

An intuitive explanation for the above approach is that we are always limited by the number of stalls. Using an extreme case, if we had a huge number of stalls relative to the number of cows, then distance wouldn’t really be a problem; we could probably find enough stalls that are spread out enough to fit all the cows. However, we don’t have a huge number of stalls. Thus, we need to utilize as many cow stalls as possible, suggesting the above approach. 

Another observation that we make is that the largest distance is bounded between 0 and 1 billion, and that it must be an integer. This means that there are a finite number of distances.

Finally, we note that if we test a distance of x, and find that it doesn’t work, we automatically know that any distance greater than x won’t work either. Remember that we are basically looking for enough stalls that are all at least a certain distance apart. Thus, if x doesn’t work, then x+1, x+2 … won’t work either since they are even more demanding than x.

With these observations, we can start to approach this problem.  We can actually apply the principle of binary search to this question. Here are the 3 cases, supposing that we have bounded the optimal solution in the interval {low, high}
Low and high are the same. Thus we have found the minimum.
The current distance works. Since the question asked for the largest minimum distance, we need to find a more optimal solution. We examine the interval of {(low+high)/2, high}.
The current distance fails. We now know that every distance higher than the current distance fails. We examine the interval of {low, (low+high)/2}.
