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
- Used [CYK algorithm]{https://en.wikipedia.org/wiki/CYK_algorithm} fro context free grammar to parse the sentences.
- Used Pyro PPL (Pytorch) to learn Probabilities associated to production rules.
