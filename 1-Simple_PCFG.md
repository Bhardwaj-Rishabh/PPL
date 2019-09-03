### Learning PCFG step-by-step
```
Updates
```

## Task 1: If Probabilistic Programming Languages can infere probability distributions
**Given**
- Production rules (Grammar w/o probabilities)
- Sentences from English Language

**Infer**
- Production Probabilities

**Experiment**
- Dataset: Generated the sentences from a simple unambiguous grammar. 
```
S -> NP VP
NP -> DT NN
VP -> 'sleeps'|'runs'|'walks'|'climbs'|'reads'
DT -> 'The'|'A'
NN -> 'man'|'woman'|'human'|'animal'
```

- Used [CYK algorithm]{https://en.wikipedia.org/wiki/CYK_algorithm} fro context free grammar to parse the sentences.
- Used Pyro PPL (Pytorch) to learn Probabilities associated to production rules.

**Results**

Taking VP productions-

*Actual Probabilities*
```
VP -> NP VP|DT NN|'The'|'A'|'woman'|'human'|'man'|'animal' - Probability 0
VP -> 'walks' (0.4)| 'runs' (0.2) | 'sleeps' (0.1)| 'reads' (0.15)| 'climbs' (0.15)
```

*Inferred Probabilites*

These are the plots I obtained on Dataset: 10K (in blue) and 100K (in black). The actual probabily is also mentioned below each plot.

![Learning Probabilities](https://github.com/rishabhbhardwaj15/PPL/blob/master/result_1.png)

