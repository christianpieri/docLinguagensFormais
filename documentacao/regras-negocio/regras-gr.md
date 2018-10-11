---
layout: default
---

### 1. Gramática regular

Uma gramática regular é um sistema gerador de linguagens regulares. É formado por uma quádrupla (**N**, **T**, **P**, **S**), onde:

- **N** conjunto de símbolos não terminais;
- **T** conjunto de símbolos terminais;
- **P** conjunto finito de produções da forma (**P** ⊆ **N** ∪ **T**)⁺ → (**N** ∪ **T**)⋆;
- **S** símbolo inicial.

Um símbolo não terminal pode derivar em zero ou mais passos um conjunto de símbolos terminais e não terminais.
Um símbolo terminal, como o próprio nome indica, não irá mais derivar outro símbolo.

### 2. Implementação

**1.** Uma regra de produção de uma gramática é representada pela classe **ProductionRule**, que possui os atributos:

- **terminal**: é do tipo *Symbol* e representa um símbolo terminal;
- **variable**: é do tipo *Symbol* e representa um símbolo não terminal. 

**2.** Uma gramática regular possui o atributo:

- **productions**