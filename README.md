# LRU-Cache

Introduction
Welcome to the documentation for the LRU Cache solution on LeetCode! In this document, I will explain the implementation of a Least Recently Used (LRU) cache, a popular data structure used to efficiently manage limited resources while maintaining quick access to recently used items.

Problem Statement
The LRU cache is designed to handle the following operations:

Get the value of a key from the cache if it exists. If the key is not present, return -1.
Put a key-value pair into the cache. If the cache is already at its capacity, I must remove the least recently used item before inserting the new key-value pair.
Approach Overview
To efficiently implement the LRU cache, I will combine two data structures: a hashmap and a doubly linked list. The hashmap will be used to store key-value pairs for fast retrieval and insertion. The doubly linked list will maintain the order of item usage, where the front of the list represents the most recently used item, and the end represents the least recently used item.

Detailed Explanation
Data Structures:

Hashmap: I use a hashmap to store key-value pairs. The keys are unique and serve as the lookup for fast access. Each key points to its corresponding node in the doubly linked list.

Doubly Linked List: This is the heart of our LRU cache. It will hold the key-value pairs and maintain the order of usage. Each node in the list contains the key, value, and pointers to the previous and next nodes in the list.

Initialization:

I initialize the cache with a maximum capacity, provided as input, to determine the maximum number of items the cache can hold.
Get Operation:

When I want to get the value of a key from the cache:
I first check if the key exists in the hashmap. If it does not, I return -1 to indicate that the key is not present in the cache.
If the key is present, I retrieve its corresponding node from the hashmap and move the node to the front of the doubly linked list. This action signifies that the item has been recently used. As a result, the most recently used items will always be at the front of the list.
Put Operation:

When I want to put a key-value pair into the cache:
I first check if the key already exists in the hashmap.
If the key is not present, I check if the cache is at its maximum capacity.
If the cache is full, I need to remove the least recently used item from the end of the doubly linked list and the corresponding key-value pair from the hashmap.
After removing the least recently used item (if necessary), I create a new node with the key-value pair and insert it at the front of the doubly linked list. Additionally, I add the key and the new node to the hashmap for quick future access.
Complexity Analysis
The LRU cache solution provides efficient performance for both get and put operations. The time complexity for both operations is O(1) since all operations involve manipulating the hashmap and the doubly linked list, both of which offer constant time complexity for access and modification.

However, it's important to note that the space complexity of the LRU cache solution is O(capacity).
