### Learning PCFG step-by-step
```
Updates
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/rishabhbhardwaj15/PPL/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

### Learning PCFG

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

