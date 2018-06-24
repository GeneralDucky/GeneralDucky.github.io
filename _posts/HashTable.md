##### Introduction
Hash Table is a data structure that is extremely efficient at storing and retrieving values.  
A hash table achieves O(1) time for retrieval of a value, in comaprison to O(N) for unsorted array.  

##### Hash Function
Hash Tables rely on **hash functions**. Hash functions are mathematical functions that should display certain properties:   
1. If two objects, x and y, are considered to be equal, then hashFunction(x) must equal hashFunction(y)
2. If two objects, x and y, are not equal, then hashFunction(x) should not equal hashFunction(y). This condition is not absolutely necessary, but should be met as much as possible.  
3. Hash functions should have their outputs be randomly distributed around their range.
4. Hash functions should not be computationally expensive.

The value hashFunction(x) is x's **hash code**
Hash functions typically produce 32-bit integers as output.  
Because there are infinite objects that could potentially be created, in comparison to the hash function's limited range, it is inevitable that 2 distinct objects will have the same hash code.  

This is known as a **collision**.  

In addition, the hash code for an object may not be immediately usable. For example, hash tables use an internal array to store information. This means that negative values and values over the array's capacity are unusable.  
We use a compression function to compress the hash codes into the proper range. A very simple example is to use modulus. 

It is also possible that two different hash codes are compressed to the same number. This is also known as a collision.  
Compression functions should ideally minimize collisions for a set of hash codes.  

##### Collision Handling
Because collisions are guarenteed to occur, we need to be able to handle them.  
There are 2 main types of collision handling schemes.
1. Separate Chaining. 
