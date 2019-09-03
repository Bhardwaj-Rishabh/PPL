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

```
From Start symbols, we can have only two non-terminals produced (or a terminal). We have to choose an ordered pair from infinite possible non-terminal symbols and finite number of terminals (if we know what these are, for english we can take all appearing 
words as terminals).

For implementation, we need to restrict maximum number of possible non-terminals. Let say nt_symbols=500.

Now sample from a Beta distribution nt_symbols (500) number of times.
Let suppose samples are p1,p2,p3,p4..p500, 0<=pi=<1.

Now Stick breaking,
P1 = p1,             p1 fractiom of the stick occupied by symbol 1)
P2 = (1-P1)*p2,      from the remaining stick, p2 fraction is occupied by nt symbol 2)
P3 = (1-(P1+P2))*p3  and so on...
...
