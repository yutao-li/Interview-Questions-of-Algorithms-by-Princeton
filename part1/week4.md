**Priority Queues**  
1.Dynamic median. Design a data type that supports insert in logarithmic time, find-the-median in constant time, and remove-the-median in logarithmic time.

maintain two binary heaps, one that is max-oriented and one that is min-oriented.  
https://stackoverflow.com/questions/15319561/how-to-implement-a-median-heap

2.Randomized priority queue. Describe how to add the methods sample() and delRandom() to our binary heap implementation. The two methods return a key that is chosen uniformly at random among the remaining keys, with the latter method also removing that key. The sample() method should take constant time; the delRandom() method should take logarithmic time. Do not worry about resizing the underlying array.

sample():sample from the underlying array  
delRandom():swap with the last element, and then swim up or sink down, delete the last item(after swap)

3.Taxicab numbers. A taxicab number is an integer that can be expressed as the sum of two cubes of positive integers in two different ways: a^3 + b^3 = c^3 + d^3. For example, 1729 is the smallest taxicab number: 9^3 + 10^3 = 1^3 + 12^39 . Design an algorithm to find all taxicab numbers less than n.
<pre>
Version 1: Use time proportional to n^2logn and space proportional to n^2.
Version 2:Use time proportional to n^2logn and space proportional to n.
</pre>

I think the question does not state the task correctly. Actually, we should design an algorithm to find all taxicab numbers with a, b, c, and d less than n.  
generate the sum of two cubes for all possibilities from 1,8,27,...,(n-1)^3  
1.quicksort all the sums and traverse from the beginning  
2. https://stackoverflow.com/a/23658420/7801448 very brilliant!

**Elementary Symbol Tables**
1.Java autoboxing and equals(). Consider two double values a and b and their corresponding <tt>Double</tt> values x and y.
<pre>
Find values such that (a==b) is true but x.equals(y) is false.
Find values such that (a==b) is false but x.equals(y) is true.
</pre>

https://stackoverflow.com/a/12559675/7801448
<pre>
double x1 = 0.0, y1 = -0.0;
Double a1 = x1, b1 = y1;
StdOut.println(x1 == y1);
StdOut.println(a1.equals(b1));

double x2 = 0.0/0.0, y2 = 0.0/0.0;
Double a2 = x2, b2 = y2;
StdOut.println(x2 != y2);
StdOut.println(!a2.equals(b2));
</pre>

2.Check if a binary tree is a BST. Given a binary tree where each Node contains a key, determine whether it is a binary search tree. Use extra space proportional to the height of the tree.

Hint: design a recursive function isBST(Nodex,Keymin,Keymax) that determines whether x is the root of a binary search tree with all keys between min and max.

3.Inorder traversal with constant extra space. Design an algorithm to perform an inorder traversal of a binary search tree using only a constant amount of extra space.

https://www.geeksforgeeks.org/inorder-tree-traversal-without-recursion-and-without-stack/  
https://www.scss.tcd.ie/disciplines/software_systems/fmg/fmg_web/IFMSIG/winter2000/HughGibbonsSlides.pdf

4.Web tracking. Suppose that you are tracking nn web sites and mm users and you want to support the following API:
<pre>
User visits a website.
How many times has a given user visited a given site?
</pre>
What data structure or data structures would you use?

Hint: maintain a symbol table of symbol tables.
