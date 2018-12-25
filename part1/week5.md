## Balanced Search Trees
1.Red–black BST with no extra memory. Describe how to save the memory for storing the color information when implementing a red–black BST.

if it's an internal node, reverse the left and right child to mark it red, else, it's a leaf node, make its left and right child point to itself to mark it red,otherwise be null

2.Document search. Design an algorithm that takes a sequence of n document words and a sequence of m query words and find the shortest interval in which the m query words appear in the document in the order given. The length of an interval is the number of words in that interval.

for each occurrence of the first query word, determine the shortest interval beginning from that word using greedy algorithm, then find the min among all the occurrences.

3.Generalized queue. Design a generalized queue data type that supports all of the following operations in logarithmic time (or better) in the worst case.  
* Create an empty data structure.
* Append an item to the end of the queue.
* Remove an item from the front of the queue.
* Return the ith item in the queue.
* Remove the ith item from the queue.

create a red–black BST where the keys are integers and the values are the items such that the ith largest integer key in the red–black BST corresponds to the ith item in the queue.
