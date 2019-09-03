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

A, B, and C are non-terminals while a is terminal symbol. In CN-Form, a non-terminal can produce two 
non-terminals or a terminal symbol. S is start symbol. Null production will appear only when epsilon is 
in the language (L(G)) produced by Grammar (G).
```

```
The start symbol S can emit a Terminal symbol or Transition occurs producing a non-temrminal pair of symbols. 

To choose from emission ot transition,

Consider f ~ Beta(0.5)
T ~ Binomial(f)
f is the probabilty of terminal symbol.

if node Emits:
 D ~ Dirichlet(C), C is concentration parameter prior of dimention of possible terminal symbols.
 t_sym ~ Categorical(D), sampling from a distribution of terminal symbols.
 
if node Transits:
 We have to choose an ordered pair from infinite possible non-terminal symbols.
 For implementation, we need to restrict maximum number of possible non-terminals. Let say nt_sym=500.

 Now sample from a Beta distribution nt_sym (500) number of times.
 Let suppose samples are p1,p2,p3,p4..p500, 0<=pi=<1.

 Now Stick breaking,
 P1 = p1,             p1 fractiom of the stick occupied by symbol 1)
 P2 = (1-P1)*p2,      from the remaining stick, p2 fraction is occupied by nt symbol 2)
 P3 = (1-(P1+P2))*p3  and so on
 
 Now, create pair-wise multiplication matrix M of dimensions nt_sym x nt_sym, reshape it to make it a vector.
 Hence, S -> symi symj ,where ordered pair (symi,symj) ~ Categorical(M)
```

*Essence*
```
Starting from the top node, infer Binomial distribution parameter weather the node will emit a terminal or 
transmit (a non-terminal pair). If emit, infer categorical distribution over the possible terminal symbols. 
If transmit, learn Categorical ditribution over infinite number of non-terminal symbol pair.
```
