***union-find***  
1.Social network connectivity. Given a social network containing n members and a log file containing m timestamps at which times pairs of members formed friendships, design an algorithm to determine the earliest time at which all members are connected (i.e., every member is a friend of a friend of a friend ... of a friend). Assume that the log file is sorted by timestamp and that friendship is an equivalence relation. The running time of your algorithm should be mlogn or better and use extra space proportional to n.

use weighted quick union until size of root reaches n

2.Union-find with specific canonical element. Add a method find() to the union-find data type so that find(i) returns the largest element in the connected component containing i. The operations, union(), connected(), and find() should all take logarithmic time or better.
For example, if one of the connected components is {1,2,6,9}, then the find() method should return 99 for each of the four elements in the connected components.

as shown in the hint,maintain an extra array to the weighted quick-union data structure that stores for each root i the large element in the connected component containing i.

3.Successor with delete. Given a set of n integers S={0,1,...,n−1} and a sequence of requests of the following form:  
<pre>
  Remove x from S
  Find the successor of x: the smallest y in S such that y≥x.  
</pre>
design a data type so that all operations (except construction) take logarithmic time or better in the worst case.

construct an array of n integers in order, link each element with the preceding one and the subsequent one, when remove x from, make the backward link of the element that x links forward to, denoted as f, point to what x links backward to, denoted as b, and make the forward link of b point to f.

***Analysis of Algorithms***  
1.3-SUM in quadratic time. Design an algorithm for the 3-SUM problem that takes time proportional to n^2 in the worst case. You may assume that you can sort the n integers in time proportional to n^2 or better.

Here's a method which makes no use of external storage(like hash table).first sort the array, let the sum be S, for each element i in the array, let W=S-i, start from the begin index and end index of array, if sum of two elements > W, decrease end index by 1, else increase begin index by 1, stop when the sum =W

2.Search in a bitonic array. An array is bitonic if it is comprised of an increasing sequence of integers followed immediately by a decreasing sequence of integers. Write a program that, given a bitonic array of n distinct integer values, determines whether a given integer is in the array.
<pre>
  Standard version: Use ∼3lgn compares in the worst case.
  Signing bonus: Use ∼2lgn compares in the worst case (and prove that no algorithm can guarantee to perform fewer than ∼2lgn compares in the worst case).
</pre>

Standard version:one binary search to find the max, and two binary searches to search in two parts.
bonus: use a modified binary search, let i denote the element to find  
<pre>
if i < pivot, 
  if left bound of interval < i,
    search in left subarray
  if right bound of interval < i,
    search in right subarray
else if i > pivot,
  if pivot is in increasing trend,
    search in right subarray
  else,
    search in left subarray
</pre>
proof:determining whether a given integer is in the array is equivalent to finding the index of a given integer i or return -1, for an  input array of n integers, each integer can have n different indices (meaning situated in different positions), so the algorithm must have n * n different possible executions paths for all inputs, by resorting to the comparison-based decision tree, we know the algorithm should perform log(n*n) compares in the worst case.

3.Suppose that you have an n-story building (with floors 1 through n) and plenty of eggs. An egg breaks if it is dropped from floor T or higher and does not break otherwise. Your goal is to devise a strategy to determine the value of T given the following limitations on the number of eggs and tosses:
<pre>
Version 0: 1 egg, ≤T tosses.
Version 1: ∼1lgn eggs and ∼1lgn tosses.
Version 2: ∼lgT eggs and ∼2lgT tosses.
Version 3: 2 eggs and <a href="https://www.codecogs.com/eqnedit.php?latex=\sim&space;2\sqrt{n}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sim&space;2\sqrt{n}" title="\sim 2\sqrt{n}" /></a> tosses.
Version 4: 2 eggs and <a href="https://www.codecogs.com/eqnedit.php?latex=\leq&space;c\sqrt{T}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\leq&space;c\sqrt{T}" title="\leq c\sqrt{T}" /></a> tosses for some fixed constant c
</pre>

https://math.stackexchange.com/questions/835582/egg-drop-problem
