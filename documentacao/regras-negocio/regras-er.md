---
layout: default
---

### 1. Expressão regular

Uma expressão regular é uma representação dos padrões que as palavras de uma determinada linguagem obedecem. Ela é formada por um alfabeto e um conjunto de operações. São elas:

- União;
- Concatenação;
- Fecho.

A expressão regular admite o uso de parênteses. O operador de fechamento tem maior precedência, seguido da concatenação e união.

### 2. Implementação

**1.** Uma expressão regular possui os seguintes atributos básicos:

- **regex**: é do tipo *String* e representa a expressão regular em si.
- **operators**: é um conjunto de caracteres que representam os operadores de uma expressão regular, que são ".", "+", "\*", "(" e ")".

#### 2.1 Conversão de expressão regular para autômato finito

**1.** Para realizar o algoritmo de conversão de expressão regular para autômato finito, precisamos construir primeiramente a árvore sintática extendida. Ela possui como nodo um objeto do tipo **Node**, que possui os seguintes atributos:

- **id**: um valor do tipo *int* para identificação do nodo;
- **parent**: é do tipo *Node* e representa o nodo pai;
- **left**: é do tipo *Node* e representa o nodo vizinho a esquerda;
- **right**: é do tipo *Node* e representa o nodo vizinho a direita;
- **value**: é um caracter que representa o valor do nodo.

Para a construção da árvore utilizamos a operação **convertToPostFix**, que Transforma a string da expressão regular para a notação posfixa, tornando fácil a execução das operações utilizando pilhas para armazenar os operadores e operandos.

**2.** A partir desta árvore, são necessárias quatro operações nos nodos para a obtenção do autômato: 

- **nullable**: é a verificação se um determinado nó é anulável, e por consequência a sua subárvore também será. Ele será utilizado depois na produção dos *firstPos* e *lastPos* da ávore.

- **firstPos**: é o cálculo das primeiras posições da árvore. Ele só é calculado quando há necessidade. O *firstpos* da raíz da árvore será utilizado, no final do algoritmo, como estado inicial do autômato resultante. Os *firstPos* também são utilizados na função de *followPos*.

- **lastPos**: é a função que verifica as ultimas posições possíveis de cada nó. É calculado recursivamente e conforme a necessidade. Ele é utilizado nos calculos do *followPos*.

- o **followPos**: é o calculo das possíveis posições seguintes representadas por cada nodo folha i da árvore. A partir dele conseguimos montar o conjunto "DStates", dizer quais são os estados do AFD resultanteS e suas respectivas transições.

**2.** Os resultados destas operações são salvos como atributos de uma expressão regular:

- **nullable**: é formado por um mapa que possui como chave um nodo e como valor um *boolean*, indicando se o nodo é anulável ou não;
- **firstPos**: é formado por um mapa que possui como chave um nodo e como valor um conjunto de nodos;
- **lastPos**: é formado por um mapa que possui como chave um nodo e como valor um conjunto de nodos;
- o **followPos**: é formado por um mapa que possui como chave um inteiro e como valor um conjunto de nodos.

**3.** A operação que converte a expressão regular para autômato finito é a **toFiniteAutomata**. Ela chama as operações:

- **computeNullable**;
- **computeFirstPos**;
- **computeLastPos**;
- **computeFollowPos**.

Após realizá-las, é chamada a operação **buildFiniteAutomata**, que monta o autômato finito de acordo com as operações realizadas.