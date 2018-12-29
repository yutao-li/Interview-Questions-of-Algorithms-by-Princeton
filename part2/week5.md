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
