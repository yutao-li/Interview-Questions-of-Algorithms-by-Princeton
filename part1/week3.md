**Mergesort**  
1.Merging with smaller auxiliary array. Suppose that the subarray a[0] to a[n−1] is sorted and the subarray a[n] to a[2∗n−1] is sorted. How can you merge the two subarrays so that a[0] to a[2∗n−1] is sorted using an auxiliary array of length nn (instead of 2n)?

copy only the left half into the auxiliary array and then merge directly to the original array.

2.Counting inversions. An inversion in an array a[] is a pair of entries a[i] and a[j] such that i<j but a[i]>a[j]. Given an array, design a linearithmic algorithm to count the number of inversions.

mergesort,in merge phase,sum the position leap of each element of the right subarray whenever it is moved to the aux array before the left subarray index comes to end

3.Shuffling a linked list. Given a singly-linked list containing nn items, rearrange the items uniformly at random. Your algorithm should consume a logarithmic (or constant) amount of extra memory and run in time proportional to nlogn in the worst case.

similar to mergesort,but the key idea lies in how to merge two uniformly shuffled linked lists l1 and l2 of sizes n1 and n2 combined them into a uniformly shuffled linked lists of size n1 + n2. Actually, it's quite simple, just select the head of l1 with a probability of n1/(n1+n2), and select head of l2 with a probability of n2/(n1+n2), in this way, we can guarantee the uniform randomness. (The proof is not hard, omitted)

**Quicksort**  
1.Nuts and bolts. A disorganized carpenter has a mixed pile of nn nuts and nn bolts. The goal is to find the corresponding pairs of nuts and bolts. Each nut fits exactly one bolt and each bolt fits exactly one nut. By fitting a nut and a bolt together, the carpenter can see which one is bigger (but the carpenter cannot compare two nuts or two bolts directly). Design an algorithm for the problem that uses nlogn compares (probabilistically).

https://www.geeksforgeeks.org/nuts-bolts-problem-lock-key-problem/

2.Selection in two sorted arrays. Given two sorted arrays a[] and b[], of sizes n1 and n2, respectively, design an algorithm to find the kth largest key. The order of growth of the worst case running time of your algorithm should be logn, where n = n1 + n2.
<pre>
Version 1 : n1 = n2 and k = n/2
Version 2: k = n/2
Version 3: no restrictions
</pre>

general approach:
<pre>
while not found:
  let i=length of a/2,j=length of b/2
  if k>i+j,
    if b[j]<=a[i],
      k-=j
      b=b[j+1:]
    else,
      k-=i
      a=a[i+1:]
  else,
    if b[j]<=a[i],
      a=a[:i]
    else,
      b=b[:j]

Recur in a subproblem of roughly half the size.
</pre>
details might be tricky,omitted  
https://www.geeksforgeeks.org/k-th-element-two-sorted-arrays/

3.Decimal dominants. Given an array with nn keys, design an algorithm to find all values that occur more than n/10n/10 times. The expected running time of your algorithm should be linear.

https://www.cnblogs.com/evasean/p/7273857.html https://stackoverflow.com/questions/50558730/how-to-find-all-values-that-occur-more-than-n-k-times-in-an-array
