## Stacks and Queues
1.Queue with two stacks. Implement a queue with two stacks so that each queue operations takes a constant amortized number of stack operations.

enqueue: push to one stack
dequeue: pop all and push to the other stack, except the bottom one,which is to return

2.Stack with max. Create a data structure that efficiently supports the stack operations (push and pop) and also a return-the-maximum operation. Assume the elements are reals numbers so that you can compare them.

use two stacks, one stores the data, another stores the max from the bottom to each storey

3.Java generics. Explain why Java prohibits generic array creation.

https://www.quora.com/Why-does-Java-prohibit-generic-array-creation

## Elementary Sorts
1.Intersection of two sets. Given two arrays a[] and b[], each containing n distinct 2D points in the plane, design a subquadratic algorithm to count the number of points that are contained both in array a[] and array b[].

first sort and then count

2.Permutation. Given two integer arrays of size nn, design a subquadratic algorithm to determine whether one is a permutation of the other. That is, do they contain exactly the same entries but, possibly, in a different order.

sort both arrays

3.Dutch national flag. Given an array of nn buckets, each containing a red, white, or blue pebble, sort them by color. The allowed operations are:
<pre>
swap(i,j): swap the pebble in bucket i with the pebble in bucket j.
color(i): determine the color of the pebble in bucket i.
</pre>
The performance requirements are as follows:
<pre>
At most n calls to color().
At most n calls to swap().
Constant extra space.
</pre>

3-way partitioning,but need not to swap the first item with pivot because we already know that there are only 3 colors.
