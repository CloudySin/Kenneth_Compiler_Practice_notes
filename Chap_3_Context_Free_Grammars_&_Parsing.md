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
    - is called in "Backus-Naur form(**BNF**)"
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
Ways of solution:
1. one: require the precense of else-part;
2. another one: use a bracketing keyword for the if-statement ("end-if");
#### 3.4.4 Inessential Ambiguity
- Inessential ambiguity: same syntax structure from different recursive grammar rule. (eg.:"associative operations");
### 3.5 Extented Notations: EBNF & Syntax Diagrams
#### 3.5.1 EBNF Notation
- EBNF = (repetitive + optional) constructs + BNF
- repetition -> "{}"
- optional -> "()"
#### 3.5.2 Syntax Diagrams
> syntax diagrams: graphical representations for EBNF rules
- "round" graphics -> "terminals"
- "rectangle" graphics -> "nonterminals"
### 3.6 Formal Properties of Context-Free Languages
#### 3.6.1 A Formal Definition of Context-Free Languages
- Definition（Components）：
    - A set T of terminals;
    - A set N of nonterminals;
    - A set P of grammar rules (directional-links: "A -> α");
    - A start symbol S from the set N;
- Derived components:
    - derivation step;
        - set of symbols;
        - sentential form;
    - L(G): set of sentences derivable from S;
        - leftmost derivation;
        - rightmost derivation;
#### 3.6.2 Grammar Rules as Equations
- least-fixed-point semantics "E":
    - 1. f(E) = (E+E) ∪ N;
    - 2. E = f(E);
#### 3.6.3 The Chomsky Hierarchy & Limits of Syntax as Context-Free Rules
- Chomskey Hierarchy: language classes constructed by four grammars;
    - regular grammar: to express sth. only;(type 3)
    - context free rules: "->";(type 2)
        - context: a pair of strings;
    - context-sensitive grammar rule;(type 1)
        - eg. use of names: C's declaration before use;
            - with BNF
                - 1. include names in grammar rules;
                - 2. for each name: write a rule -> establish itsdeclaration prior to a potential use;
            - static semantics: rules that beyond the parser but still in compiler;
                - "type checking";
    - unrestricted grammars: no restrictions on α & β in "α -> β";(type 0)
        - corresponding equivalent machine； pushdown automaton;
### 3.7 Syntax of the TINY Language
#### 3.7.1 A context-free grammar for TINY;

