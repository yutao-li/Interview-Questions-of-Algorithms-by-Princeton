## Tries 
1. Prefix free codes. In data compression, a set of binary strings is if no string is a prefix of another. For example, {01,10,0010,1111} is prefix free, but {01,10,0010,10100} is not because 10 is a prefix of 10100. Design an efficient algorithm to determine if a set of binary strings is prefix-free. The running time of your algorithm should be proportional the number of bits in all of the binary stings.

   insert the binary strings into a 2-way trie
   
2. Boggle. Boggle is a word game played on an 44-by-44 grid of tiles, where each tile contains one letter in the alphabet. The goal is to find all words in the dictionary that can be made by following a path of adjacent tiles (with no tile repeated), where two tiles are adjacent if they are horizontal, vertical, or diagonal neighbors.

   create a trie containing all of the words in the dictionary,starting from each grid, using dfs to trace down all the possible paths if it is not null in the trie
   
3. Suffix trees. Learn about and implement , the ultimate string searching data structure.

   lectures ahead talked about this.
   
## Substring Search
1. Cyclic rotation of a string. A string s is a cyclic rotation of a string t if s and t have the same length and s consists of a suffix of t followed by a prefix of t. For example, "winterbreak" is a cyclic rotation of "breakwinter" (and vice versa). Design a linear-time algorithm to determine whether one string is a cyclic rotation of another.

   hash a string s as sum of hashcode for all possible cyclic rotations of s, compare the hash code(can use horner's method to speed up,see lectures), or use kmp
   
2. Tandem repeat. A tandem repeat of a base string b within a string s is a substring of s consisting of at least one consecutive copy of the base string b. Given b and s, design an algorithm to find a tandem repeat of b within s of maximum length. Your algorithm should run in time proportional to M+N, where M is length of b and N is the length s.  
   For example, if s is "abcabcababcaba" and b is "abcab", then "abcababcab" is the tandem substring of maximum length (2 copies). 
   
   boyer-moore or kmp
   
3. Longest palindromic substring. Given a string s, find the longest substring that is a palindrome in expected linearithmic time.  
   Signing bonus: Do it in linear time in the worst case.   
   
   given a parameter L, find all palindromic substrings of length exactly L in linear time using a Karp-Rabin strategy, how to judge? compute the hash of characters 0 to L/2-1 from left to right, and compute the hash of characters L-1 to L/2 from right to left, check if they are equal, thereby, we can use Karp-Rabin method to update both hashes(update methods of the two hash differ) and check the equality successively. And then use binary search to find the largest L.
   
   
