---
layout: post
title: Binary Search
---
Binary Search is an efficient method of searching in an ordered list.  
If we have an unordered list and are told to search for a particular element, we have no choice but to search the entire list.  
This is because when we examine an element in the list, we don't get any information about the rest of the elements in the list.  
  
However, when we examine an element in an ordered list, we do get information about other elements.  
{-5,-2,0,2,4,6,8,9,10}  
Let's suppose we're searching for 9. We begin by examining the 4th element (length of the list/2 = 4). There are three cases that could arise.  
1. The 4th element is equal to 9.
2. The 4th element is less than 9.
3. The 4th element is greater than 9.  
  
It's obvious that 2 (the 4th element of the list) is not 9. However, we can get some more information from our observation.  
Since the list is in ascending order, we know that elements 0 - 3 are less than 2. This means that they are also less than 9, so we don't need to investigate these elements.  
In addition, we also know that 9 has to be in the upper half of the list, namely, elements 5 - 9.  
  
Now, we are effectively searching along this list:  
{6,8,9,10}  
We compute the halfway point of this list ((5+9)/2=7).  
  
The 7th element is 8, so our list is once again reduced to the following:  
{9,10}.  
Computing the halfway point again (element 8), we see that the 8th element is indeed 9, so we are done.  
  
Binary Search is known as Decrease and Conquer algorithm because it reduces the size of the problem that we are solving.  
Notice how at every iteration, we cut the size of the array we are searching on by half. This behavior gives Binary Search an excellent runtime of O(logn).  
  
We'll implement Binary Search recursively for simplicity:  
```java
//This algorithm returns the index of the target if found. Otherwise, returns -1. 
public int binSearch(int low, int high, int[] array, int target){ 
  if(high >= low){                           //low represents the left endpoint of the interval we are searching on
      int halfway = (low+high)/2;            //high represents the right endpoint of the interval we are searching on
      if(array[halfway] == target) {
        return halfway;                            //Case 1: We've found the target, so return
      }
      else if(array[halfway] < target) {                      //Case 2: The halfway element is too low.
        return binSearch(halfway + 1, high, array, target);   //So we search the upper half of the curreint interval
      }
       else {                                                  //Case 3: The halfway element is too high
        return binSearch(low, halfway - 1, array, target);     //So we search the lower half of the current interval
       }
  }
  return -1;                                  //At this point, we know that the target is not in the array.
                                              //We've narrowed down the possible location of the target to be a single number.
                                              //And that location wasn't the target.
}
```
We can actually improve this algorithm by a small amount. Note that integer overflow could occurr by doing (low+high)/2, even though the end result is actually lower than Integer.MAX_VALUE. We can change this to low + (high-low)/2 to avoid this problem.
