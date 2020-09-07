# Autômatos Finitos Determinísticos
É o modelo formal de computação menos poderoso que pode ser montado usando o [[Conceitos Básicos|conceito de linguagens formais]], mais específicamente um tipo específico de linguagem, as _linguagens regulares_. 

## Definição
AFD's são quintuplas formados pelos símbolos $\delta ,\sum ,Q, q_0,F$. Esses símbolos representam os seguintes conceitos:
- $\sum$ é o alfabeto utilizado
- $Q$ é um conjunto finito não-vazio de **estados**
- $q_0$ é o estado inicial do AFD
- $F$ é o conjunto de estados finais do AFD
- $\delta$ é a função de transição de estados, que pode ser representada da forma abaixo

$$\delta : Q \times \sum \to Q$$

Em português, temos que a função recebe um estado de $Q$ e um símbolo do alfabeto $\sum$ para retornar outro estado de $Q$.

### Representações
Podemos representar visualmente um AFD tanto por uma **tabela** como por um **grafo direcionado**. 

Por exemplo, se temos $\sum = \{0,1\}$, $Q = \{q_1,q_2,q_3\}$, $q_0=q_1$ e $F = \{q_3\}$, podemos ter um $\delta$ da seguinte forma:

| $\delta$ | $0$ | $1$ | 
|---|---|---|
|$q_1$|$q_2$|$q_1$|
|$q_2$|$q_1$|$q_3$|
|$q_3$|$q_3$|$q_1$|

Dessa forma sabemos o resultado final de cada combinação individual de símbolo e estado para essa função $\delta$.

### Por que _determinístico_?
Esse autômato é chamado assim porque, para cada par de símbolo do alfabeto e estado do conjunto, ele retorna somente _um estado_. Em outras palavras, ele determina o estado no final da operação baseado no inicial. É o que chamamos de **função de transição completamente determinada**.

## Lidando com Palavras
Repare que até o momento, estávamos lidando com mudanças de um símbolo para outro. No entanto, e quando lidamos com palavras?

### Em termos leigos

Para palavras nós passamos por toda a máquina, mudando de estado conforme cada símbolo é jogado, até que cheguemos no final dela. Lemos palavras usando cada símbolo da **esquerda para a direita**.  Se no final do processamento chegamos em algum símbolo que pertence à $F$, a palavra foi **aceita** por nosso AFD. Caso contrário, ela é **rejeitada**.

Se temos uma linguagem formal $L$ que usa o alfabeto $\sum$, ao passarmos por nossa máquina AFD (que chamaremos de $A$), nós teremos uma **linguagem regular** caso $L = L(A)$, $L(A)$ sendo a linguagem gerada pelo processamento usando $A$.

É como um teste. Se todas as palavras de $L$ passam por $A$, temos uma **linguagem regular**

### Entrando em definições
A transição entre uma palavra para o próximo estado dela é chamado de **configuração**. Ela inicia com o par estado / palavra e termina com o novo estado / palavra reduzida. Pode ser representado como $C_x$ e demonstrado da seguinte forma:

$$C_0 \vdash C_1$$

Configurações transformam palavras assim:
$$(q,w) \vdash (q',w')$$
- $q$ era o estado anterior, $q'$ é o atual ($q' = \delta(q,w)$)
- $w = \sigma w$, onde $\sigma$ é o simbolo usado em $\delta$

Se temos várias configurações $C_0,\dots,C_n$ e uma relação tal que $C_0 \vdash \dots \vdash C_n$, podemos representar isso como $C_0 \vdash^* C_n$. 

Palavras aceitas podem ser representadas como $(q_0,w) \vdash^* (f,\epsilon)$, onde $f \in F$.

A linguagem aceita por $A$, $L(A)$, é o conjunto de todas as palavras $w \in \Sigma*$ que foram aceitas por $A$. Sendo assim, $L(A) \subseteq \Sigma*$.
