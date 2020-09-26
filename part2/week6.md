### Reductions
1. Longest path and longest cycle. Consider the following two problems
   * LongestPath: Given an undirected graph G and two distinct vertices s and t, find a simple path (no repeated vertices) between s and t with the most edges.
   * LongestCycle: Given an undirected graph G′, find a simple cycle (no repeated vertices or edges except the first and last vertex) with the most edges.  
   Show that LongestPath linear-time reduces to LongestCycle.
   
   add a new path (with new vertices) between s and t. 
   
2. 3Sum and 4Sum. Consider the following two problems:
  * 3Sum: Given an integer array a, are there three distinct indices i, j, and k such that a_i + a_j + a_k = 0=0?  
  * 4Sum: Given an integer array b, are there four distinct integers i, j, k, and l such that b_i + b_j + b_k + b_l = 0?  
  Show that 3Sum linear-time reduces to 4Sum. 
  
    add M= max_i|ai| + 1 to every element and append -3*M,compute 4 sum
  
3. 3Sum and 3Linear. Consider the following two problems:
  * 3Linear: Given an integer array aa, are there three indices (not necessarily distinct) i, j, and k such that a_i + a_j = 8*a_k?
  * 3Sum: Given an integer array bb, are there three indices (not necessarily distinct) ii, jj, and kk such that b_i + b_j + b_k = 0?  
  Show that 3Linear linear-time reduces to 3Sum.  
  
    let M= max_i|ai| + 1, for each element x in array,append -8*x-8*M to array , for each original element in array, add 4*M inplace
  
### Linear Programming
too hard, skipped

### Intractability

1. Graph 3-colorability. An undirected graph is 3-colorable if the vertices can be colored red, green, or blue in such a way that no edge connects two vertices with the same color. Prove that 3COLOR is NP-complete.

    reduce to sat, for each edge, s represented by x1+x2, t represented by y1+y2, or all the possible "and assignment" together equals true (possible sum:0,1,2) or (!0 and !0 and !0 and 1) or (1 and !0 and !0 and !0) or ...=true
  
2. Decision problems. Traditionally, the complexity classes P and NP are defined in terms of decision problems (where the answer is either yes or no) instead of search problems (where the answer is the solution itself). Prove that the search problem version of SAT (find a binary solution to a given system of boolean equations?) polynomial-time reduces to the decision version of SAT (does there exists a binary solution to a given system of boolean equations?).

    to determine whether to set x_1 to true, set it to true; simplify the resulting system of boolean equations; and check whether there exists a solution to the simplified system.  

3. Optimization problems. Given an undirected graph with positive edge weights, the traveling salesperson problem is to find a simple cycle that visits every vertex and has minimum total weight. The search problem version of the problem is, given a parameter LL, find a tour of length at most LL. Prove that the optimization version of the problem polynomial-time reduces to the search version of the problem.  
    Remark: for many problems such as this one, the optimization version of the problem (which is not known to be in NP) is solvable in polynomial time if and only if the search version of the problem (which is easily seen to be in NP) is.
  
    binary search
