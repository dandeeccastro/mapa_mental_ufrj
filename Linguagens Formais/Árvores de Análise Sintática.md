# Árvores de Análise Sintática
- Isso serve para, numa linguagem natural, analisarmos a sintaxe dela
	- Sujeito, objeto e verbo, qual ação está sendo performada e suas consequências
	- Exemplo: Pedro comeu batata
		- Nesse caso a raíz da árvore é o conceito de uma frase
		- Descendo, temos predicado e sujeito
			- Já sabemos que o sujeito é Pedro, então podemos definir que esse é o final da árvore
			- Em outras palavras, Pedro é a folha dessa árvore
		- O predicado é composto do verbo e do objeto, os dois nós abaixo
			- O verbo é "comeu"
			- O objeto é "batata"
		- Dá pra desenhar uma árvore com isso mas não vou linkar aqui
	- Se pararmos para pensar, fizemos uma série de processos de análise para, de um conceito abstrato como uma sentença, chegarmos uma frase como "Pedro comeu batata"
	- Podemos descrever esse processamento como o caminho descendo a árvore
		- \<sentença\> $\Rightarrow$ \<sujeito\>\<predicado\> $\Rightarrow$ \<sujeito\>\<verbo\>\<objeto direto\> $\Rightarrow$ Pedro \<verbo\>\<objeto direto\> $\Rightarrow$ Pedro comeu \<objeto direto\> $\Rightarrow$ Pedro comeu batata
	- Temos como dizer que tem uma relação entre árvores de análise sintática e gramáticas, esse é o objetivo dessa análise
	
## Mais a fundo sobre as árvores
- Quando estamos lidando com esses tipos de árvores, sempre consideraremos que 
	- Existe uma raíz e ela nunca é precedida por nenhum outro vértice
		- Por que? Existe árvore sem raíz? Ou que a raíz não é o topo dela?
	- Os nós da árvore são ordenados
- A nomenclatura de árvores em estruturas de dados se aplica também
	- Ascendentes são os acima do nó, descendentes são os abaixo
	- Pais são ascendentes diretos, filhos são descendentes diretos
	- Irmãos são descendentes do mesmo pai
	- Folhas são os nós finais dá árvore (sem descendentes)
	- Os que não são folhas são vértices interiores
- Baseando nas regras acima, se montarmos árvores ordenando os irmãos, todos os descendentes desses irmãos ordenados, quando montados, vão ser ordenados também
	- Isso é bem fácil de provar, mas não vou fazer aqui
	- A prova está na apostila de LF do Menasché
	
## Árvores Gramaticais / de Análise Sintática
- Se temos uma gramática livre de contexto $G$, com todos os elementos que tem direito, montaremos árvores com as seguintes características
	- Os rótulos dos nós fazem parte do conjunto $(T \cup V)$
	- Elas são geradas com base de um procedimento recursivo usando árvores básicas
		- Parecido com a geração de autômatos usando versões atômicas deles
- Árvores Básicas e o método de recursão
	- Se temos $\sigma \in T, X \in V$ e $X \to \epsilon$ é uma regra em $R$, então podemos dizer que as árvores abaixo são gramaticais
		- Uma árvore que a raíz tem rótulo $\sigma$
		- Uma árvore com raíz $X$ e folha $\epsilon$
	- Regra da combinação
		- Condição: eu tenho $T_1 \dots T_n$ árvores gramáticais de rótulos $\alpha_1 \dots \alpha_n$ e as regras $X \to \alpha_1 \dots \alpha_n$ pertencem à $R$
		- Consequência: A árvore com raíz $X$ e filhos $\alpha_1 \dots \alpha_n$ (com as árvores $T_1 \dots T_n$ embaixo) também é gramatical
	- Com isso conseguimos substituir árvores: se tivermos um vértice $v$ rotulado com $X$, podemos trocar ele por qualquer outra árvore gramatical que também tem raíz $X$
	- Também reparamos que só nas folhas temos vértices rotulados no conjunto $(T \cup \{\epsilon\})$
	- Nos vértices interiores só podemos ter uma variável ($v \in V$)
- Fatos sobre árvores gramaticais
	- Temos um vértice $v$ de uma árvore que tem rótulo $X$, filhos $\alpha_1 \dots \alpha_n \in T \cup V$
	- $X \to \alpha_1 \dots \alpha_n$ tem que ser uma regra da gramática $G$
		- Essa é a regra associada à $v$
	- Se $v$ for raíz, chamamos a árvore de $X$-árvore
	- Se $v$ for uma raíz e folha com rótulo $\sigma \in T$, chamamos a árvore de $\sigma$-árvore
	
	## Colheita 
	- A operação de colheita, definida como $c(T)$ (T nesse conceito sendo uma árvore e não os terminais) forma palavras dado uma árvore
	- Usando as árvores básicas, definimos a colheita como:
		- Colheita da árvore com folha $\sigma$ = $\sigma$
		- Colheita da árvore com raíz $X$ e folha $\epsilon$ = $epsilon$
	- Usando a regra da combinação e considerando $T_1 \dots T_n$ árvores, definimos a colheita $c(T) = c(T_1).c(T_2).\dots.c(T_n)$
	- Árvore de Derivação
		- Se temos uma gramática G que pode derivar $w$ e tem símbolo inicial $S$, a árvore de derivação é uma $S$-árvore que o valor da colheita é $w$
		- O nome de árvore de derivação é reservado pra esse caso específico
	- Lidando com Florestas / Relacionando derivações e colheitas
		- Se temos uma palavra $w = \alpha_1 \dots \alpha_n \in (T \cup V)^*$, podemos definir uma $w$-floresta como uma sequência ordenada de árvores $T_1 \dots T_n$
		- A sequência tem os rótulos $\alpha_1 \dots \alpha_n$, e são $\alpha_j$-árvores 
		- A colheita da floresta é a concatenação das colheitas das árvores dela
	- Algoritmo que imprime uma derivação de uma X-árvore
		- Damos uma X-árvore para o algoritmo 
		- O loop é o seguinte:
			- Se a floresta $F$ for uma $w$-floresta, imprimo $w$ e paro se todas as árvores de $F$ são rotuladas por terminais
			- Acho a raíz $v$ da árvore mais à esquerda da floresta $F$ e removo ele. O que sobra são as novas árvores, que são a nova floresta $F$
	- Observações:
		- Tem uma demonstração que prova que isso funciona, mas eu não vou copiar porque hoje (19/10/2020) eu tô sem tempo
		- Remoção do vértice de uma árvore é denotado matematicamente pela operação $F / v$ onde $F$ é a floresta e $v$ é o vértice
		
## Equivalência das Árvores e Gramáticas
- Objetivo: provar que, dada uma gramática livre de contexto G, toda a palavra que tem derivação em G é colheita de alguma árvore de derivação de G
- Algoritmo que prove isso não é trivial, então vamo na fé com indução
	- Base da indução
		- Temos uma gramática com palavra $w$ e variável $X$ de forma que $X \Rightarrow^* w$ com apenas um passo
		- Pra isso rolar, tem que ter uma regra em $R$ que seja do formato $X \to t_1 \dots t_n$, sendo $t_1 \dots t_n \in T$
		- Logo, $w$ é uma colheita de uma $X$-árvore com raíz rotulada por $X$ e folhas por $t_1 \dots t_n$
	- Hipótese
		- Se $Y \in V$ e $Y \Rightarrow^* u \in T^*$ em $p$ passos, então $u$ é colheita de uma $Y$-árvore de $G$
		- E vamos de $w \in T^*$, que pode ser derivado a partir de $X \in V$ em $p+1$ passos
		- Primeiro passo é $X \Rightarrow v_1\dots v_n$, onde $v_1 \dots v_n \in T \cup V$ e $X \to v_1v_2\dots v_n$ está em $R$
		- Isso continua com cada $v_i$ derivando para um $u_i$, 
		- Como cada derivação tem comprimento menor ou igual a $p$ agora, então a hipótese de infução nos leva a crer que temos $v_i$-árvores com colheita $u_i$
		- Isso é uma floresta, e a primeira regra é que $X \to v_1 \dots v_n$
		- Logo a junção dessa floresta numa raíz com rótulo $X$ gera uma $X$-árvore com colheita igual a $c(T_1)\dots c(T_n)=u_1\dots u_n=w$
		- Isso prova o passo de indução
- Sendo assim, podemos montar o teorema que associa os dois itens
	- Seja $G$ uma gramática livre de contexto e $w \in L(G)$. Então:
		- Existe uma árvore de derivação cuja colheita é $w$
		- A cada árvore de derivação com colheita $w$, temos uma única derivação mais à esquerda de $w$
		- A cada árvore de derivação com colheita $w$, temos uma única derivação mais à direita de $w$

## Ambiguidade
- Sabe quando tu fala uma frase que tem um duplo sentido? Significa que você usou uma gramática ambígua
- Gramáticas com ambiguidade são as que conseguem gerar duas árvores de derivação para a mesma palavra
	- Por que isso importa? Porque para um compilador, ter dois jeitos de interpretar um comando é problemático
- Podemos tentar remover ambiguidade forçando precedência de operações adicionando mais variáveis
- Não existe algoritmo que detecte se uma gramática é ambígua ou não, é impossível para um computador verificar isso
- Gramáticas livres de contexto ambíguas geram linguagens ambíguas
- Existem linguagens livres de contexto que não podem ser geradas por nenhuma gramática livre de contexto
	- São as linguagens inerentemente ambíguas
	- Ambiguidade é problema de gramática, mas ambiguidade inerente é problema de linguagem
- Gramáticas regulares podem ser ambíguas também, mas não existe linguagens regulares inerentemente ambíguas (por que?)
	- Existe um algoritmo que recebe uma gramática regular e retorna uma linguagem regular sem ambiguidade
	- Isso rola porque o processo de criação é feito de certa forma que é impossível ter ambiguidade
		- Determinístico = Um resultado único de cada computação 
		- Cada palavra de $L(G) = L(M)$ só tem uma derivação possível (sendo G a gramática e M o AFD)
	- Procedimento do algoritmo
		1. Determinamos um AFND $M$ de forma que $L(M) = L(G)$
		2. Determinamos um AFD $M'$ a partir de $M$, de forma que $L(M) = L(M')$
		3. Determinamos uma gramática $G''$ obtida a partir de $M'$, que não pode ser ambígua e gera $L(M')$