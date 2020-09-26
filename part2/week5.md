## Regular Expressions
1. Challenging REs. Construct a regular expression for each of the following languages over the binary alphabet or prove that no such regular expression is possible:
   <pre>
    All strings except 11 or 111.
    Strings with 1 in every odd-number bit position.
    Strings with an equal number of 0s and 1s.
    Strings with at least two 0s and at most one 1.
    Strings that when interpreted as a binary integer are a multiple of 3.
    Strings with no two consecutive 1s.
    Strings that are palindromes (same forwards and backwards).
    Strings with an equal number of substrings of the form 01 and 10.

    1|10(0|1)*|110(0|1)*|111(0|1)+|0(0|1)*
    (1(0|1)+)*1*
    impossible, proof: https://stackoverflow.com/questions/12497514/regular-expression-for-equal-number-of-0-and-1
    00+|100+|010+|0010*|00+10*
    https://stackoverflow.com/questions/7974655/regex-for-binary-multiple-of-3
    0*(10|0)*
    impossible, proof: https://stackoverflow.com/questions/233243/how-to-check-that-a-string-is-a-palindrome-using-regular-expressions
    https://cs.stackexchange.com/questions/57342/write-a-regular-expression-contains-an-equal-number-of-01-and-10-subtrings
   </pre>  

   general idea:https://cs.stackexchange.com/questions/45570/how-do-i-find-a-regular-expression-for-a-particular-language
   
2. Exponential-size DFA. Design a regular expressions of length n such that any DFA that recognizes the same language has an exponential number of states   

   https://cs.stackexchange.com/questions/6063/how-to-prove-that-dfas-from-nfas-can-have-exponential-number-of-states
   
3. Extensions to NFA. Add to NFA.java the ability to handle multiway or, wildcard, and the + closure operator.

   omitted.
   
### Data Compression
1. Ternary Huffman codes. Generalize the Huffman algorithm to codewords over the ternary alphabet (0, 1, and 2) instead of the binary alphabet. That is, given a bytestream, find a prefix-free ternary code that uses as few trits (0s, 1s, and 2s) as possible. Prove that it yields optimal prefix-free ternary code.

   if it's not optimal, there exist some code that could be shorter, yet shorter code representations has been occupied by words with higher frequency, so it has to replace, then it cannot use fewer trits

2. * Identify an optimal uniquely-decodable code that is neither prefix free nor suffix tree.
   * Identify two optimal prefix-free codes for the same input that have a different distribution of codeword lengths.
   
   { 0011, 011, 11, 1110 } or { 01, 10, 011, 110 }.  
   when building trees, if two subtrees are equally frequent, one tree chooses the lower one, the other choose the higher one
   
3. Move-to-front coding. Design an algorithm to implement move-to-front encoding so that each operation takes logarithmic time in the worst case. That is, maintain alphabet of symbols in a list. A symbol is encoded as the number of symbols that precede it in the list. After encoding a symbol, move it to the front of the list.

   use segment tree to maintain prefix sum. idea similar to: https://leetcode.com/problems/minimum-possible-integer-after-at-most-k-adjacent-swaps-on-digits/discuss/720548/O(n-logn)-or-Detailed-Explanation
