---
layout: default
---

## Bem-vindo(a) ao manual do usuário!

Aqui serão detalhados todas as funcionalidades do sistema e como utilizá-las.


#### [Conhecendo o sistema e suas funcionalidades](./conhecendo-sistema)

**1.** No sistema é possível representar uma linguagem regular de três formas:

- Autômatos finitos;
- Gramáticas regulares;
- Expressões regulares.

**2.** As operações podem ser realizadas em cima dessas estruturas. São elas:

- Minimização de autômatos finitos determinísticos;
- Determinização de autômatos finitos não determinísticos;
- Conversão:
	- De autômato finito para gramática regular;
	- De gramática regular para autômato finito;
	- De expressão regular para autômato finito.

#### Inserindo as estruturas no sistema

**1.** Um autômato finito deve ser inserido em um arquivo *.txt* no seguinte formato:
`
    a   b
>q0  q1  q0
*q1 q1  q0

`
- As colunas devem ser delimitadas por tabulação;
- A primeira linha representa os símbolos das funções de transição;
- A primeira coluna representa o estado de origem da transição:

	- Para indicar o estado inicial, é necessário incluir o símbolo **>** antes do nome do estado;  
	- Para indicar estados finais, é necessário incluir o símbolo <b> * </b> antes do nome do estado.

**2.** Uma gramática regular deve ser inserida em um arquivo *.txt* no seguinte formato:

`
S -> aA | b | bC | &
A -> aB | bA
B -> a | aC | bB
C -> aA | bC | b 
`
*Gramática regular que representa a linguagem {a,b}\* onde o número de a's é divisível por 3*


**3.** Uma expressão regular deve ser inserida em um arquivo *.txt* no seguinte formato:

`(a+b)*abb`

- A operação de "Or" é representada pelo símbolo **+**.

#### Utilizando as operações na linha de comando

<br>
[Voltar](../)
