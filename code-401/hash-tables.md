# Implementation: Hash Tables

To turn in your reading “Reply” to this discussion by teaching something that you learned from the readings listed below.

Some ideas for how you might want to teach:

-   Use an analogy
-   Explain a detail in depth
-   Use WHY, WHAT, HOW structure
-   Tutorial / walk through an example
-   Write a quiz
-   Create a vocabulary/definition list
-   Write a cheat sheet
-   Create a diagram / visualization / cartoon of a topic
-   Anthropomorphize the concepts, and write a conversation between them
-   Build a map of the information
-   Construct a fill-in-the-blank worksheet for the topic

## Resources

-   Read [Intro to Hash Tables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)

Terminology: 
* Hash: a hash is the result of an algorithm takin an incoming string and converting it into a value that could be used for some purpose. In the case of a hastable it's used to determin the index of an array
* Buckets - a bucket is what is contained in each index of the array of the hashtable. each index is a bucket. an index could potentially contain multiple key/value pairs if a collision occurs
* Collisions - a collision is what happens when more than one key gets hashed to the same location of the hashtable

We use Hashtables to:
1. hold unique values
2. as dictionaries
3. as libraries

Internal Methods for Hashtables:
* Add() to add a new key/value pair
* Find() that takes in a vey and finds it's value
* Contains() to take in a key and return a boolean
* GetHash() that will take in a key and return the index


-   Watch [what is a hash table?](https://www.youtube.com/watch?v=MfhjkfocRR0)

Two main components: key and value! 
Hash table implements an associative array (like a dictionary!)
Hash(key) returns index to put the info into. 
If there's already a key/value in the index then that's a collision and that will cause a linked list to be created off the index, called chaining! 


-   Read [basics of hash tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)

A hash function is any function that can be used to map data, regardless of size, to a data set of a fixed size. The values returned by the hash function are called hash values, hash codes, hash sums, or just hashes.

Separate chaining is one of the most commonly used collision techniques. It's implemented by creating linked lists off the index where the collision happens. 

-   Skim [hash table wiki](https://en.wikipedia.org/wiki/Hash_table)