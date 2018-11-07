## foreword:
- parsing -> "syntax analysis"
- syntax tree( parse tree) <- syntax  <- "grammar rules" <- [context-free grammar] -> "recursive"
- parsing methods:
    1. top-down
    2. bottom-up
### 3.1 The Parsing Process
- sequence of tokens -(parser)> syntax tree
- tree -> "dynamic data structure" -> node
    - node's field -> "attributes" for further compiliation
    - node's fields' structure -> "dynamic data structure"
- meeting error -> **error repair**
    - actions
        - reporting vital messages
        - resumption of the parsing
    - property
        - depend on particular algos.
### 3.2 Context-Free Grammars
- definition: syntactic structure of a programming language;
- Similarity: lexical structure of an RE language
    - differs: CFG have recursive rules.
#### 3.2.1 Comparasion to RE Notations
- basic RE rules:
    - choice--"|"
    - oncatenation--(none)
    - repetition--"*"
    - definition--"="
- Grammar rules:
    - No repetition(no "*")
    - definition--"->"
    - use RE as components
    - is called in "Backus-Naur form(BNF)"
#### 3.2.2 Specification of CFG rules
- Alphabet:
    - RE -> chars
    - CFG -> tokens of strings of chars
- rule:
    - a string of symbols
        - first->name of structure
        - second->"->" +
            - symbol from ABC
            - name for a structure
            - "|"
#### 3.2.3 Derivations & Language defined by Grammar
- Grammar -(rules)> legal strings of token symbols
- rules -(derivation)> legal strings of token symbols
- derivation -> replacements of structure names by rules
    - begin -> single structure name
    - end -> a string of token symbols
>rules->define

>derivation->construct

- token symbols:
    - nonterminals
        - left recursive -> immediate left recursion
        - rght recursive
    - terminals -> "base case"
    - empty -> "epsilon production"
### 3.3 Parse Trees & Abstract Syntax Trees
#### 3.3.1 Parse Trees
> **Derivations of strings are NOT unique.**
- parse tree:
    - labeled tree -> nodes
        - interior nodes -> nonterminals
        - leaf nodes -> terminals
        - children of internal nodes -> replacement of associated nonterminals
            - preorder numbering -> leftmost derivation
            - postorder numbering -> rightmost derivation
### 3.3.2 Abstract Syntax Trees
- syntax tree( checked only by parser)
    - leaves -> tokens
    - internal nodes -> steps in a derivation
    - additional attributes -> actual value
        >principle of syntax-directed translation
- "abstract syntax"
    - given by a data type declaration
- binding **sequential** statements together with just one node
    - left-most children & right-sibling
        >issue: distinguish this from child links
### 3.4 Ambiguity
#### 3.4.1 Ambiguous Grammars
- ambiguous grammar: that generates two distinct parse trees;
    > syntactic structure is NOT specified precisely( should be avoided of course!)
- two methods for dealing with ambiguities:
    - Disambiguating rule
        >eg.    
            -> "fully parenthesized expressions"    
            -> "precedences"   
            -> associativity
                > 1. "left-associative"   
                > 2. "nonassiciative"   
            
        - pros: corrects the ambiguity without changing the grammar;
        - cons: syntactic structure is influenced not only by grammar;
    - Change the Grammar to remove the ambiguity.
#### 3.4.2 Precedence & Associativity
- operator
    - groups of equal precedence;
    - different rules;
    > "precedence cascade"
#### 3.4.3 The Dangling Else Problem
