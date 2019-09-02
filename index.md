### Learning PCFG step-by-step
```
Updates
```

## Task 1--If Probabilistic Programming Languages can infere probability distributions
**Given**
- Production rules (Grammar w/o probabilities)
- Sentences from English Language

**Infer**
-Production Probabilities

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
These are the plots I obtained on Dataset of 10K (in blue) and 100K sentences (in black):

```
The attached figure shows the inferred probabilities for "VP", true production probabilities of which are as follows:
**VP** production---
From To Probability 
VP NP VP 0
VP DT NN 0
VP 'The' 0
VP 'A' 0
VP 'woman' 0
VP 'human' 0
VP 'man' 0
VP 'animal' 0
VP 'walks' 0.4
VP 'runs' 0.2
VP 'sleeps' 0.1
VP 'reads' 0.15
VP 'climbs' 0.15
```
![Learning Probabilities](https://github.com/rishabhbhardwaj15/PPL/blob/master/result_1.png)
