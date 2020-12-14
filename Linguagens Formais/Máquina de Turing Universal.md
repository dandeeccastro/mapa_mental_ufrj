# Máquina de Turing Universal

## Introdução

- Máquina de Turing: modelo computacional simples
- O que pode, e o que não pode, ser computado com um modelo computacional desses?
- Recapitulando: adicionando mais coisas à uma máquina de Turing, não aumentamos o poder
	- O que significa esse poder computacional?
	- Não dando pra resolver o problema com uma simples, adicionar coisas nela também não resolve o problema
	- Além do modelo de Turing, tem outros modelos feitos por pesquisadores
		- Lambda-cálculo (Alonzo Church), Funções sigma-Recursivas (Kleene)
		- Equivalentes ao de Turing, porque mesma classe de problemas que a de Turing resolve, essas resolvem também
		- Máquina de Turing: limite superior para o que podemos computar
		- Uma máquina de Turing que decide uma linguagem ou computa uma função como modelo teórico da noção de um algoritmo

## Tese de Church-Turing

- Problema de decisão de função são algoritmicamente computáveis se e somente se existe uma máquina de Turing que a decide ou computa
- É uma tese que não pode ser provada e pode futuramente ser refutada
	- Isso se alguém criar um modelo computacional melhor que o de Turing
	- Altamente improvável porque muitos tentaram e nenhum conseguiu
	- Nem a computação quântica supera a máquina de Turing
- Máquina de Turing Universal U
	- Uma máquina de Turing capaz de simular qualquer outra máquina de Turing
	- Entrada: o "programa" da máquina que está sendo simulada
		- Descrever os componentes de uma máquina de Turing a partir do alfabeto de U
		- Isso implica alfabeto, estados e transações
	- Se uma MT é um modelo de algoritmo, a MTU é um modelo de um computador programável
		- MTU executa MT se receber o conjunto de instruções dele

## Máquina de Turing Universal

- Tem vários jeitos de fazer isso, mas bora usar o alfabeto {0,1,\sigma,q,X,Y,Z,#,a,b}
- Alfabeto da fita é o alfabeto de entrada mais {triângulo, espaço em branco}

- Usamos o sistema unário para enumerar os símbolos e estados da MT
	- Sistema unário é quando representamos tudo com zero só
- Diferenciando estados de símbolos
	- Símbolos tem o prefixo \sigma e estados tem o prefixo q
	- Vamos considerar também as setas como símbolos 
- Vamos trabalhar com uma MT que tem n estados e m símbolos

- Para garantir que o espaço na fita para símbolos e estados seja o mesmo sempre, usamos um padrão
	- Reservamos m + 3 casas pra representar cada símbolo
		- Além dos símbolos tem as duas setas, então vai precisar no mínimo de m + 2 zeros
		- Sobra uma casinha para o prexifo \sigma
	- Reservamos n + 1 casas para os estados
		- Casa de folga é para o prefixo q
	- Espaço que sobrar é preenchido com 1's
- Primeiro símbolo: um 0. Segundo: dois 0, e assim vai...
- Convenção: Triângulo e setas sempre serão os três primeiros
	- Triângulo: \sigma01^m+1
	- Seta para Direita: \sigma001^m
	- Seta para Esquerda: \sigma0001^m-1

- Codificando as transições da MT no MTU
	- Botamos as transições entre X (X\<transição\>X)
	- Como as funções tem formato f(q,\sigma) => (q,\sigma), anotamos isso na sequência
		- Primeiro os dois símbolos de entrada, na mesma notação que a definida anteriormente
		- Depois os outros dois símbolos de saída/resultado, também na mesma notação
	- Y sinaliza o fim das transições
	- Depois do Y a gente coloca o Q, Q sendo o estado no qual a máquina se inicia
	- Depois dele vem Z, e depois dela vem a palavra w que a MT ia processar
		- NOTA: um símbolo na parte Z está marcado como #
		- Esse é o indicador para dizer qual símbolo era para a MT estar lendo naquele momento 
		- Meio que um indicador de cabeçote

- Categorizações importantes nesse processo 
	- Os símbolos à direita do triângulo e à esquerda do símbolo Z **codificam a máquina de Turing**
		- Podemos chamar ela de c(M), c sendo de codificação e o M da Máquina de Turing
	- Já a parte para a direita de Z é a **codificação da palavra**, que podemos chamar de c(w)

## MTU em Funcionamento 

- Primeiramente a MTU confere se está tudo certo com a fita dela
	- Isso significa ir do triângulo até o final, verificando se a ordem está sendo seguida
	- Símbolos primeiro, depois estados, depois transições com X, Y e o estado, Z e a palavra, etc 
	- Se algo não bate, ele fica processando infinitamente (erro)

- Depois simulamos o funcionamento da MT, com um processo de três etapas
	- Primeira Etapa:
		- A MTU varre as transições para encontrar o par de estado e símbolo que representa o estado atual
		- Isso significa o estado depois de Y e o símbolo com # depois de Z
		- Ele vai testando um por um, e a cada teste ele troca zeros por a e uns por b
		- Se achar o match dele, ele troca ainda sim zeros por a e uns por b
		- Isso é feito pra que o símbolo e estado mais a esquerda que ainda tenham zeros e uns seja identificado como o estado resultado da transição 
		- NOTA: se não tiver transição, MT chegou no estado final, e MTU também precisa parar aí
	- Segunda Etapa:
		- Copiamos o símbolo novo no lugar depois de Y
		- E vamos fazendo isso trocando o símbolo na fita entre X por as e bs, pra que a máquina saiba o que copiou e o que ainda falta
		- Depois temos que analizar a transição e o que ela faz
			- O símbolo codifica seta pra direita? Então escrevemos o # no próximo símbolo da palavra depois de Z
			- O símbolo é seta pra esquerda? Mesma coisa só que para a esquerda do # antigo
			- Se for um símbolo para ser escrito, copia-se o símbolo no espaço depois do # pelo novo símbolo
	- Terceira Etapa:
		- Voltamos para o triângulo inicial, trocando as e bs por zeros e uns, resetando o estado
