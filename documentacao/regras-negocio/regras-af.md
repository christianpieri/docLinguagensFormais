---
layout: default
---

### 1. Autômato finito

Um autômato finito é uma máquina de estados que pode ser representado formalmente por uma quíntupla (**Q**,**Σ**,**δ**,**q0**,**F**), onde:

- **Q** é um conjunto finito de estados;
- **Σ** é o alfabeto do autômato, que é representado por um conjunto finito de símbolos;
- **δ** é um conjunto de funções de transição da forma **Q** x **Σ** → **Q**;
- **q0** é o estado inicial do autômato, onde é iniciada a computação antes de nenhum símbolo do alfabeto ter sido computado;
- **F** é o conjunto de estados finais do autômato, também conhecidos como estados de aceitação.

Um autômato finito pode reconhecer uma **linguagem regular**. A linguagem que um autômato reconhece é o conjunto de todas as palavras que quando computadas terminam em um estado de aceitação. 

#### 1.2 Autômato finito determinístico

Um autômato finito determinístico é um autômato finito que gera um único ramo de computação para cada palavra de entrada. Ou seja, cada estado possui no máximo uma transição por cada símbolo, não é possível ler um símbolo da entrada e transitar para mais de um estado.

#### 1.3 Autômato finito não determinístico

Um autômato finito não determinístico é um autômato finito que pode gerar vários ramos de computação para uma palavra de entrada. A palavra faz parte da linguagem reconhecida pelo autômato se algum dos ramos resultar em um estado de aceitação no final da computação.

### 2. Estruturas de dados utilizadas

**1.** Apenas uma classe foi utilizada para implementar os autômatos finitos determinísticos e não determinísticos. A diferenciação não foi necessária pois ambos são autômatos finitos, logo possuem a mesma estrutura. 

- Para diferenciar AFDs de AFNDs, verificamos a existência do símbolo **&** e, em caso negativo, verificamos cada conjunto imagem das funções de transição de cada estado. Na existência de um conjunto não unitário é caracterizado o não determinismo.

### 3. Regras

**1.** 


<br>
[Voltar](./)
