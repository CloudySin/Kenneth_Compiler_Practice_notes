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
- problems:
    - 1.difficult: BNF->EBNF;
    - 2.difficult: decide the proper nonterminal option;
        - First set;
    - 3.difficult: Nonterminal A -> ε
        - Folllow set of "A";
    - 4.early error detection;
        - First set;
        - Folllow set of "A";
### 4.2 LL(1) Parsing
#### 4.2.1 Basic Method of LL(1) Parsing
> LL(1) parsing uses an explicit stack ranther than recursive calls to perform a parse;
- Actions：
    - Generate: Replace a nonterminal A at the top of the stack: A -> α;
    - Match: Match a token on the top of the stack with a next token input;
#### 4.2.2 The LL(1) Parsing Table & Algorithm
- Parsing Method -> LL(1) Paring Table "M[N, T]" : Possible choices;
    - rules:
        - "A -> α" is a production choice