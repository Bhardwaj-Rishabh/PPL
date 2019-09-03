# Infinite PCFG

Task considered: Learninng PCFGs-To learn the number of non-terminal symbols, production rules, and associated probabilities.

 ## Using HDP
 
 ```
- Non-parametric bayes, where, the number of parameters are not fixed beforehand and grows with data.
- Hyracrhical Dirichlet Process
```

## Algorithm
<img src="https://github.com/rishabhbhardwaj15/PPL/blob/master/hdp.png" width="500">

*Simplified Implementation*
```
Considering Chomsky-Normal Form of a Context-Free Grammar.
- A -> B C or
- A -> a   or
- S -> epsilon (null production)

A, B, and C are non-terminals while a is terminal symbol. In CN-Form, a non-terminal can produce two non-terminals 
or a terminal symbol. S is start symbol. Null production will appear only when epsilon is in the language (L(G)) 
produced by Grammar (G).
```

