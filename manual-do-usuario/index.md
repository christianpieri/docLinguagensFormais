---
layout: default
---

# Bem-vindo(a) ao manual do usuário!

Aqui serão detalhados todas as funcionalidades do sistema e como utilizá-las.


## 1. Conhecendo o sistema e suas funcionalidades

**1.** No sistema é possível representar uma linguagem regular de três formas:

- Autômatos finitos;
- Gramáticas regulares;
- Expressões regulares.

**2.** As operações podem ser realizadas em cima dessas estruturas. São elas:

- Minimização de autômatos finitos determinísticos;
- Determinização de autômatos finitos não determinísticos;
- União de autômatos finitos;
- Intersecção de autômatos finitos;
- Conversão:
	- De autômato finito para gramática regular;
	- De gramática regular para autômato finito;
	- De expressão regular para autômato finito.

**3.** Para rodar o sistema é necessário possuir uma instalação do *Java runtime* na versão **10** ou superior.

## 2. Inserindo as estruturas no sistema

**1.** Um autômato finito deve ser inserido em um arquivo *.txt* no seguinte formato:

		a	b
	>q0	q1	q0
	*q1	q1	q0


- As colunas devem ser delimitadas por tabulação;
- A primeira linha representa os símbolos das funções de transição;
- A primeira coluna representa o estado de origem da transição:

	- Para indicar o estado inicial, é necessário incluir o símbolo **>** antes do nome do estado;  
	- Para indicar estados finais, é necessário incluir o símbolo <b> * </b> antes do nome do estado.

**2.** Uma gramática regular deve ser inserida em um arquivo *.txt* no seguinte formato:

	 S -> aA | b | bC | &
	 A -> aB | bA
	 B -> a | aC | bB
	 C -> aA | bC | b 

*Gramática regular que representa a linguagem {a,b}\* onde o número de a's é divisível por 3*

- O símbolo *epsilon* deve ser representado pelo símbolo **&**.

- O sistema aceita apenas **gramáticas regulares**. Gramáticas de outros tipos não serão inseridas no sistema.

**3.** Uma expressão regular deve ser inserida em um arquivo *.txt* no seguinte formato:

	 (a+b)*abb

- A operação de "Or" deve ser representada pelo símbolo **+**.

**4.** A indicação de qual é o arquivo de entrada pode ser feita das seguintes formas:

> **-i** <nome\_do\_arquivo>

> **\--in** <nome\_do\_arquivo>

## 3. Arquivo de saída

**1.** O arquivo de saída irá apresentar as estruturas de acordo com a sessão **2**, em um arquivo **.txt**.

**2.** O arquivo será criado com o nome especificado na chamada e criado no diretório atual.

**3.** A indicação de qual será o nome do arquivo de saída pode ser feita das seguintes formas:

> **-o** <nome\_do\_arquivo>

> **-\-out** <nome\_do\_arquivo>

## 4. Utilizando as operações na linha de comando

**1.** Todas as operações devem utilizar o prefixo **java -jar trabalho.jar**.

**2.** Os comandos de cada operação são os seguintes:

| Operação | Comandos |
| -------- | -------- |
| Determinização | **-d** ou **-\-determinizar** |
| Minimização | **-m** ou **-\-minimizar** |
| Converter de AFD para GR | **-a2g** ou **-\-gr2af** |
| Converter GR para AFND | **-g2a** ou **-\-gr2af** |
| Converter ER para AFD | **-e2a** ou **\--er2af** | 
| União entre AFs | **-aua** ou **\--union** |
| Intersecção entre AFs | **-aia** ou **\--intersection** | 


**3.** A expressão geral para realizar uma operação com um arquivo de entrada e um arquivo de saída é:

> java -jar *trabalho.jar* <comando\_da\_operação> **-i** <nome\_do\_arquivo\_entrada> **-o** <nome\_do\_arquivo\_saída>

**4.** A expressão geral para realizar uma operação com dois arquivos de entrada e um arquivo de saída é:

> java -jar *trabalho.jar* <comando\_da\_operação> **-i** <nome\_do\_arquivo_entrada\_1> <nome\_do\_arquivo_entrada\_2> **-o** <nome\_do\_arquivo\_saída>

**5.** Para obter ajuda, utilizar os comandos **-h** ou **\--help**. 

<br>
[Voltar](../)
