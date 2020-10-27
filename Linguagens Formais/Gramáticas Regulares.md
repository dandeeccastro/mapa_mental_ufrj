# Gramáticas Regulares
- Definimos o mínimo do mínimo de gramáticas na parte de [[Gramáticas]]
- Agora vamos tratar das gramáticas que se relacionam com [[AFD e Linguagens Regulares]], as Gramáticas Regulares
- Definição: Todas as regras de R tem que se encaixar nos formatos abaixo
	- $X \to aY$
	- $X \to a$
	- $X \to \epsilon$
	- Observação: $X,Y \in V$ e $a \in T$
	
	## Exemplificando
	- Usemos uma gramática $G$ onde $T = \{0,1\}$ , $V = \{X,Y,Z\}$, $S = X$ e as regras $R$ abaixo
		- $X \to 0X$
		- $X \to 1Y$
		- $Y \to 0$
		- $Y \to 1X$
		- $Y \to 1Z$
		- $Z \to \epsilon$
	- Se queremos conferir se uma palavra $w$ é uma palavra aceita na linguagem $L(G)$, temos que ver se conseguimos montar ela a partir do símbolo inicial usando as regras
	- Para exemplo, vamos com 0011
		- Poderíamos dizer que ela é inválida se ela não pertencesse à $T^*$, mas não é o caso. Temos só que testar com as regras
		- O teste em questão: $X \Rightarrow 0X \Rightarrow 00X\Rightarrow 001Y \Rightarrow 0011Z \Rightarrow 0011$
	- No caso de gramáticas regulares, é como se pudessemos montar uma árvore de decisões para montar a palavra
		- Considerando que fiz uma escolha entre duas possibilidades, a outra escolha muito bem poderia ter sido outro nó de uma árvore
	- Coisas legais de gramáticas regulares
		- Elas só tem uma variável e ela sempre está na direita (por isso também são chamadas de gramáticas lineares à direita)
		- Única exceção da regra? No final, quando montamos a palavra final e não há variáveis
		
	## De AFNDs para Gramáticas Regulares
	- Usaremos AFND porque eles são menos regrados, mais fáceis de manipular e podemos gerar AFDs com alguns AFNDs
	- Objetivo: Dado uma gramática $G = (T,V,S,R)$ e um AFND $A = (\Sigma,Q,q_0,F,\Delta)$, queremos mostrar que $L(A) = L(G)$
		- Primeiro vamos conectando os artefatos de cada uma
			- Como os terminais definem o resultado e a linguagem do AFND aceita palavras de $\Sigma^*$, para que os dois sejam equivalentes, temos que definir $T = \Sigma$
			- As variáveis são como os estados, e temos que adicionar mais um estado final no AFND, porque quando chegamos no final da computação na gramática, o resultado não possui variável
				- $Q = V \cup \{q_f\}$
				- $F = \{q_f\}$
				- $q_0 = S$
			- De regras para transições 
				- O formato $X \to aY$ leva o estado de X para Y
				- O formato $X \to a$ leva o estado X para o estado final
				- O formato $X \to \epsilon$ leva o estado X para o final via uma $\epsilon$ transição
	## De AFDs para Gramáticas Regulares
	