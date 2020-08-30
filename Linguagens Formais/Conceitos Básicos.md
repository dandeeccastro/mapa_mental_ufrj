# Conceitos Básicos
## Alfabetos
Alfabetos são um conjunto finito e não-vazio de símbolos. Podemos representar alfabetos em notação matemática da seguinte forma: 


$$ \sum = \{a_1,a_2,a_3,...,a_n \}  $$

## Palavras

Palavras (também chamadas de _cadeias_ ou _strings_ ) são uma junção finita de símbolos seguidos, que podem ter de _1 a n_ símbolos nelas (A **única palavra** que tem zero símbolos é a que possui o _símbolo vazio_). Palavras são representadas da seguinte forma:

$$ w = w_1w_2w_3...w_n$$

Quando lidamos com palavras, temos que pensar no tamanho delas, o que chamamos de _comprimento_. Esse comprimento não depende dos símbolos se repetirem ou não, mas sim da quantidade de símbolos em uma dada palavra. Logo:
$$ w = w_1...w_n \to |w| = n$$

A **palavra vazia** é denotada pelo símbolo $\epsilon$, e é a única palavra em todo o alfabeto que possui comprimento zero.

$$ | \epsilon | = 0 $$

Quando lidamos com um conjunto de palavras, $\sum*$ define o conjunto de palavras formado pela permutação de todos os símbolos que temos no conjunto e suas combinações subsequentes. É como se criassemos da base novas palavras, adicionassemos elas à base e continuassemos o processo ad infinitum.

$$ \sum = \{a,b\} \to \sum* = \{a,b,aa,ab,bb,aaa,abb ...\}$$

## Linguagens Formais
Uma linguagem formal é um subconjunto de palavras do $\sum*$, obviamente finito. Nesse caso, podemos definir uma linguagem L como $L  \subseteq \sum*$

Linguagens diferentes pertencem a $\sum*$, mas elas por si só podem diferir uma da outra, ou conter uma a outra.

## Operações em Linguagens
Lidar com linguagens, já que são conjuntos de palavras, também significa fazer muitas operações análogas a operações em conjuntos. Muitas coisas serão semelhantes.

Para demonstrar as operações, usarei as linguagens abaixo:

$$ L_1 = \{salve, oi, hey\}, L_2 = \{yo,hi,hey\}$$
- **União**
	- Descrição: Quando juntamos os dois conjuntos, adicionando um ao outro.
	- Notação\: $A \cup B$ 
	- Exemplo\: $L_1 \cup L_2 = \{ salve, oi, hey, yo, hi\}$
- **Interseção**
	- Descrição: A linguagem gerada é o _ponto em comum_ entre as duas linguagens anteriores
	- Notação\: $A \cap B$
	- Exemplo\: $L_1 \cap L_2 = \{ hey\}$
- **Diferença**
	- Descrição: Removemos a palavra comum de uma linguagem da outra, resultando no que sobtou
		- Importante que a ordem importa! A linguagem que começa na operação é a que tem as palavras sobrando
	- Notação\: $A - B$
	- Exemplos
		- $L_1 - L_2 = \{salve, oi\}$
		- $L_2 - L_1 = \{yo,hi\}$
- **Complemento**
	- Descrição: É tudo que está em $\sum*$ mas não está na linguagem em questão.
	- Notação\: $\bar{A}$
	- Propriedades:
		- $A \cup \bar{A} = \sum* \to \bar{A} = \sum* - A$
		- $A - B = A \cap \bar{B}$
- **Concatenação**
	- Descrição: Pegamos as palavras no primeiro conjunto e concatenamos elas em todas as palavras do segundo conjunto, como se fosse um foreach para concatenação de palavras
		- Assim como a operação de diferença, a ordem importa!
	- Notação\: $A.B$
	- Exemplos
		-  $L_1.L_2 = \{yosalve, hisalve, heysalve, yooi, hioi, heyoi, yohey, hihey, heyhey\}$
		-  $L_2.L_1 = \{salveyo,oiyo,heyyo,salvehi,oihi,heyhi,salvehey,oihey,heyhey\}$
	- Propriedades:
		- Se $L_1$ e $L_2$ são conjuntos finitos, $|L_1.L_2| \leq |L_1| *| L_2|$
		- $A.\{\epsilon\}  =\{\epsilon\}.A = A$ 
		- $A.\{\emptyset\}  =\{\emptyset\}.A = \emptyset$ 
- **Estrela de Kleene**
	- Descrição: Concatenações ad infinitum feat palavra vazia
	- Notação: $L* = \{\epsilon\}\cup L \cup L.L \cup L.L.L \dots$ 
	- Propriedades
		- $\emptyset* = \{\epsilon\}$
		- $\{\epsilon\}*  =\{\epsilon\}$