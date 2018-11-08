## Chap 4. Top-Down Parsing
foreword:
    > ~ algorithm: an algorithm that parses an input string of tokens;
- two kind of parsers:
    - backtracking parsers; 
        - making backups;
        - try different possibilities;
        - exponential time( much slower than predictive one;
    - predictive parsers;
        - "lookahead tokens -> predict next construction";
- two kind of parsing algorithms:
    - recursive-decendent algorithms;
        - versatile -> suitable for handwritten parser;
    - LL(1) parsing;
        - L(1): left to right;
        - L(2): trace out a leftmost derivation;
        - 1: use 1 symbol to predict the direction of the parse;
- lookahead sets:
    - First;
    - Follow;
### 4.1 Top-Down Parsing by Recursive-Decendent
#### 4.1.1 Basic Method of Recursive-Decendent
- Grammar rule of nonterminal A: definition for a procedure that will recognizae an A;
#### 4.1.2 Repetition & Choice: Using EBNF
 - grammar rules -> EBNF -> code;
    - pitfalls:
        - match of the operations must be before calls;
#### 4.1.3 Further Decision Problems
