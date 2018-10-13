---
layout: default
---

### 1. Gramática regular

Uma gramática regular é um sistema gerador de linguagens regulares. É formado por uma quádrupla (**N**, **T**, **P**, **S**), onde:

- **N** conjunto de símbolos não terminais;
- **T** conjunto de símbolos terminais;
- **P** conjunto finito de produções;
- **S** símbolo inicial.

Uma produção de uma gramática regular possui a seguinte forma:

> **P** = {A → aX \| A ∈ **N**, a ∈ **T** ∧ X ∈ **N**} 

Um símbolo não terminal pode derivar em zero ou mais passos um conjunto de símbolos terminais e não terminais.
Um símbolo terminal, como o próprio nome indica, não irá mais derivar outro símbolo.


### 2. Implementação

**1.** Uma regra de produção de uma gramática é representada pela classe **ProductionRule**, que possui os atributos:

- **terminal**: é do tipo *Symbol* e representa um símbolo terminal;
- **variable**: é do tipo *Symbol* e representa um símbolo não terminal. 

**2.** Uma gramática regular possui o atributo:

- **productions**: representa as produções da gramática. É composto por um mapa que possui uma chave do tipo *Symbol* representando o não terminal do lado esquerdo da produção e um valor que é um conjunto de objetos do tipo *ProductionRule*, representando o lado direito da produção.

**3.** Se um símbolo não terminal possui várias derivações, cada uma delas é representada por uma entrada em **productions**.

**4.** Uma gramática regular pode realizar a seguinte operação:

- **toFiniteAutomata**: converte a gramática regular em um autômato finito.