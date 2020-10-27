# Autômatos Finitos Não Determinísticos
- São autômatos finitos que, diferente dos [[AFD e Linguagens Regulares|AFD's]], não posuem a propriedade determinística, isso é, **não necessariamente dão uma resposta pra uma entrada**
- Assim como AFD, eles são representados por uma quintupla de itens, com uma diferença pequena no último item
	- $\Sigma$ é o alfabeto usado
	- $Q$ é o conjunto de estados usados
	- $q_0$ é o estado inicial
	- $F$ é o conjunto de estados finais
	- $\Delta$ é a função de transição _não determinística_

## Função de Transição $\Delta$
- Ela pode ser definida com a seguinte expressão:
$$\Delta : Q \times (\Sigma \cup \{\epsilon\}) \to P(Q)$$
- Traduzindo para português
	- Eu recebo um estado de $Q$ e um símbolo  do alfabeto $\Sigma$, mas o retorno é um **subconjunto de conjunto de partes de $Q$**
	- $P(Q)$ é um conjunto com as permutações de todos os simbolos de Q onde a ordem não importa. 
		- Ex: $Q = \{1,2\} \to P(Q) = \{\{\epsilon\},\{1\},\{2\},\{1,2\}\}$
- Qual a diferença de AFD pra AFND?? 
	- Determinismo
		- Uma computação de um AFD sempre dá um símbolo $x$ para uma entrada $y$
		- Uma computação de um AFND, se retornar um subconjunto de $P(Q)$ com mais de um estado, tem a **chance** de ir para um ou para outro
	- As $\epsilon$-transições
		- Uma computação de AFD, quando recebe a palavra vazia, fica no mesmo estado
		- Uma computação de AFND, quando recebe a palavra vazia, pode mudar de estado, o que é chamado de **$\epsilon$-transições**
	- 
	- Montando um AFND que é um AFD? Faça $\epsilon$-transições que vão de um estado para ele mesmo, e que sempre vá de um estado pra outro estado, nunca dois.
